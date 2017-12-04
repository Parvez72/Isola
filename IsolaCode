import java.io.*;
import java.util.*;
public class TestClass {
	
		int x,y;
		public TestClass(int ax,int ay){
			x=ax;
			y=ay;
		}

	
	static boolean is_neighbour(int px,int py,int i,int j){
		if(px==i && py==j)
			return false;
		else if (Math.abs(px-i)<=1 && Math.abs(py-j)<=1){
			return true;
		}
		return false;
		
	}
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int[][] a=new int[7][7];
		int player_id,pl2;int i,j,px = 0,py=0,px2=0,py2=0;
		Scanner sc=new Scanner(System.in);
		for ( i = 0; i < 7; i++) {
			for ( j=0;j<7;j++){
				a[i][j]=sc.nextInt();
			}
		}
		player_id=sc.nextInt();
      if(player_id==1){
        pl2=2;
      }
      else{
        pl2=1;
      }
	
		for ( i = 0; i < 7; i++) {
			for ( j=0;j<7;j++){
				if(a[i][j]==player_id){
				px=i;
				py=j;
				}
              else if(a[i][j]==pl2){
                px2=i;
                py2=j;
              }
			}
		}

		//next position of player
		List <TestClass> moves=new ArrayList<TestClass>();
      	List <TestClass> moves2=new ArrayList<TestClass>();
		for(i=0;i<7;i++){
			for(j=0;j<7;j++){
				if(a[i][j]!=0)
					continue;
				if(is_neighbour(px,py,i,j)){
					if(i<px || (px==0 && i>0) || (py==0 && j>0) || (py==6 && j<6)){
					moves.add(new TestClass(i,j));
                    }
                  	else{
                      moves2.add(new TestClass(i,j));
                    }
				}
			}
		}
		int totMoves=moves.size();
      	int totMoves2=moves2.size();
        Collections.shuffle(moves);
        Collections.shuffle(moves2);
      //next position of player
		int next_px=0,next_py=0;
		if(totMoves==0 && totMoves2==0){
			System.exit(0);
		}
      	else if(totMoves>=1){
          next_px=moves.get(0).x;next_py=moves.get(0).y;
        }
		else{
          next_px=moves2.get(0).x;next_py=moves2.get(0).y;
        }

		
		System.out.println(next_px+" "+next_py);
		
		//moving player to next position
		a[px][py]=0;
		a[next_px][next_py]=player_id;
		
		//getting squares to remove
		moves.clear();
		for(i=0;i<7;i++){
			for(j=0;j<7;j++){
				if(a[i][j]==0){
                  if(is_neighbour(px2,py2,i,j)){
                    moves.add(new TestClass(i,j));
                  }
                  else{
					moves2.add(new TestClass(i,j));
                  }
				}
			}
		}
      	totMoves2=moves2.size();
		totMoves=moves.size();
      	Collections.shuffle(moves);
      	Collections.shuffle(moves2);
      	if(totMoves==1 && totMoves2>=1){
        System.out.println(moves.get(0).x+" "+moves.get(0).y);
	
        }
      else if(totMoves>1){
        System.out.println(moves.get(0).x+" "+moves.get(0).y);
		
      }
      else if(totMoves==0 && totMoves2>1){
        System.out.println(moves.get(0).x+" "+moves.get(0).y);
		
      }
      else if(totMoves==0 && totMoves2==0){
        System.exit(0);
      }
		

		
	}
}
