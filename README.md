//System.out.println(Integer.MAX_VALUE);
//for N = 1000000000 ans> integer maximum value
import java.io.*;
class Coins {
	static long[] a = new long[10000];
	public static void main(String[] aa)throws IOException{
		for(int i=0;i<=11;i++){
			a[i] = i;
		}
		for(int i=12;i<10000;i++){
			a[i] = a[i/2] + a[i/3] + a[i/4];
		}
		BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
		Integer N;
		while(1>0){
		try{N = new Integer(br.readLine());}
		catch(Exception e){break;}
		if(N<10000){
			System.out.println(a[N]);
		}
		else{
			System.out.println(bos(N));
		}
		}
	}
	static long bos(int N){
		if(N<10000){
			return a[N];
		}
		return bos(N/2) + bos(N/3) + bos(N/4);
	}
}
