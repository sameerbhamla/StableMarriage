#include <iostream>
using namespace std;

/*
a. if the current man prefers the new woman to his partner and
b. if the new woman prefers the current man to her partner
  i. this is unstable, so return false
c. if the new man prefers the current woman to his partner and
d. if the current woman prefers the new man to her partner
  i. This is unstable, so return false
e. if there are no instabilities introduced with any of the existing (i.e. “current”)
couples, so we return true
*/


bool ok(int q[], int col, int mp[3][3], int wp[3][3]){

  for(int i = 0; i < col; i++){

    if( q[col]  == q[i] ){  // checking if new women has already been assigned to a man
      return false;

    }else if( ( mp[col][q[i]] < mp[col][q[col]] ) && // check condition a. above
              ( wp[q[i]][col] < wp[q[i]][i] )) {     //check condition b. above
      return false;

    }else if( ( wp[q[col]][i] < wp[q[col]][col]) && // checks condition c
              ( mp[i][q[col]] < mp[i][q[i]]) ){     //checks condition d
      return false;

    }else{
      return true; // condition e
    }

  }

  return true;

}

void print(int q[], int c){

  for(int i = 0; i < c; i++){
    cout << "Man " << i << " With women " << q[i] << endl;

  }  
}

void backtrack(int &col){
  col--;

  if(col == -1){

  exit(0);
  }
}


int main() {
  
  int q[3];
  q[0] = 0;
  int col = 3;
  int currentCol = 1;

  int mp[3][3] = { { 0 , 2 , 1}, //0
                   { 0 , 2 , 1}, //1
                   { 1 , 2 , 0}  //2
                  // 0   1   2
  };

    int wp[3][3] = { { 2 , 1 , 0}, //0
                     { 0 , 1 , 2}, //1
                     { 2 , 0 , 1}  //2
                    // 0   1   2
  };

  bool trackCol = false; // track in case we backtrack to -1 col


  while(true){
    while(currentCol < 3){ // checking across columns

      if(trackCol == false){
        q[currentCol] = -1;
      }

      trackCol = false; 

      while( q[ currentCol ] < 3){ //  we are checking the man preference
        q[ currentCol ]++;
      }

        while( q [ currentCol ] == 3){ // backtracking function
        
          backtrack(currentCol);
          q[currentCol]++;

        }
      
      if(ok (q, currentCol, mp, wp) ){ //check if the man and women are compatible 
        break;
        
      }
      currentCol++;

    }

    print(q,col); // print after the first solution

  }

}
