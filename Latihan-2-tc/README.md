## Daftar Isi

- [Practice 2 (ETS Preparation)](#Practice-2-(ETS Preparation))
    + [Question 2.1](#Question-2.1)
    + [Question 2.2](#Question-2.2)
    + [Question 2.3](#Question-2.3)
    + [Question 2.4](#Question-2.4)
    + [Question 2.5](#Question-2.5)

# Practice-2 (ETS Preparation)

## Question 2.1

Create a program to determine the number of n terms of the Fibonacci Number

**Format Input :**

n (integer)

**Format Output :**

fibonacci number (int)

**Constrain :**

0 < n < 100


Example Input :

```c
5
```

Example Output :

```c
0, 1, 1, 2, 3
```

## Question 2.2

Create a program to determine the factorial result of a number A, how many primes there are in that digit


**Format Input :**

n (integer)

**Format Output :**

factorial_result (int), total_prime (int)


**Constrain :**

0 < n < 100

2 < Prime in Digits < 10

Example Input 1 :

```c
5
```

Example Output 1 :

```c
120, 0
```

Example Input 2 :

```c
7
```

Example Output 2 :

```c
5040, 1
```

## Question 2.3

Create a program that can convert decimal numbers to hexadecimal numbers


**Format input :**

dec (int)

**Foramt Output :**

hex (int)


**Constrain :**

0 <= dec < 1024


Example Input :

```c
456
```

Example Output :

```c
1C8
```

## Question 2.4

Create a program that can calculate the equation of the following 3 variables using Crammer's Rule

A x1 + B x2 + C x3 = X

D x1 + E x2 + F x3 = Y

G x1 + H x2 + I x3 = Z


**Constrain :**

0 <= A, B, C, D, E, F, G, H, I, X, Y, Z < 100

Example Input :

```c
4 2 1
3 -5 -2
1 1 3
X = 17
Y = -3
Z = 8
```

Example Output :

```c
x1 = 3
x2 = 2
x1 = 1
```

## Question 2.5

Here is a program to play Tic-tac-toe in multiplayer, but because of some things the program still errors when running. Find the error and explain why the error occurred!

```c
#include <stdio.h>

void playerMove(int board) {
    int move = 0;
    int a,b;
    do {
        scanf("%d %d", &a, &b);
        printf("\n");
        move = (a*3)+b;
        if(board[move]!=0){
          printf("Invalid Move, please input another move : ");
          move=0;
          playerMove(board);
        }
        else {
          board[move] = -1;
        }
    } while (move >= 9 || move < 0 && board[move] == 0);
}

void playerMove2(int board) {
    int move = 0;
    int a,b;
    do {
        scanf("%d %d", &a, &b);
        printf("\n");
        move = (a*3)+b;
        if(board[move]!=0){
          printf("Invalid Move, please input another move : ");
          move=0;
          playerMove2(board);
        }
        else {
          board[move] = 1;
        }
    } while (move >= 9 || move < 0 && board[move] == 0);
}

int win(const int board) {
    unsigned wins[8][3] = {{0,1,2},{3,4,5},{6,7,8},{0,3,6},{1,4,7},{2,5,8},{0,4,8},{2,4,6}};
    int i;
    for(i = 0; i < 8; ++i) {
        if(board[wins[i][0]] != 0 &&
          board[wins[i][0]] == board[wins[i][1]] &&
          board[wins[i][0]] == board[wins[i][2]])
          {
            return board[wins[i][2]];
          }
    }
    return 0;
}

char gridChar(int i) {
    switch(i) {
        case -1:
            return 'X';
        case 0:
            return '.';
        case 1:
            return 'O';
    }
}

void draw(int b[9]) {
  int i,j,k=3,l=0;
  for(i=0; i<3; i++){
    for(j=l; j<k; j++){
      printf(" %c ", gridChar(b[j]));
    } 
    printf("\n");
    l=j;
    j+=3;
    k+=3;
  }
}

int main() {
    int board[9] = {0,0,0,0,0,0,0,0,0};
    int player=1;
    unsigned turn;

    for(turn = 0; turn < 9 && win(board) == 0; ++turn) {
        if((turn+player) % 2 == 0){
            draw(board);
            printf("\nPlayer2 your move: ");
            playerMove2(board);
        }
        else {
            draw(board);
            printf("\nPlayer1 your move: ");
            playerMove(board);
        }
      }

    switch(win(board)) {
          case 0:
              printf("\n");
              draw(board);
              printf("\nA draw.\n");
              break;
          case 1:
              printf("\n");
              draw(board);
              printf("\nPlayer2 Win\n");
              break;
          case -1:
              printf("\n");
              draw(board);
              printf("\nPlayer1 Win\n");
              break;
    }
}
```