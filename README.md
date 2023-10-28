# code6
//KMP算法
int KMPIndex(SqString s,SqString t)  
{
	int next[MaxSize],i=0,j=0;
	GetNext(t,next);
	while (i<s.length && j<t.length) 
	{
		if (j==-1 || s.data[i]==t.data[j]) 
		{
			i++;j++;  			//i,j各增1
		}
		else j=next[j]; 		//i不变,j后退
    }
    if (j>=t.length)
		return(i-t.length);  	
    else  
		return(-1);        
}
