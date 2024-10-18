#include<stdlib.h>
#include<stdio.h>
#include<math.h>
#include<time.h>

// s - stone
// p - paper
// x - secissor
// p > s
// s > x
// x > p
/*

Game function will check only condition when a user can win
in case there is a condition where user cannot win the function with return 0
in case the input is same then it would be a draw and we can ask user to select again
*/

int game(char user, char comp){
    if(user == comp){
        return -1;
    }
    if(user == 's' && comp == 'x'){
        return 1;
    }
    if(user == 'p' && comp == 's'){
        return 1;
    }
    if(user == 'x' && comp == 'p'){
        return 1;
    }
    return 0;
}

int main(){
    int n, result;
    char user, comp;
    srand(time(NULL));
    n = rand()%100;
    if(n  < 33){
        comp = 's';
    }
    else if(n>33 && n < 66){
        comp = 'p';
    }
    else{
        comp = 'x';
    }

    printf("Hello Welcome to the Game of Stone Paper and Secissor: When asked Please enter your choice\n");
    printf("Enter:\nS->Stone\nP->Paper\nX-Scissor\n");
    scanf("%c", &user);

    result = game(user, comp);
    if(result == -1){
        printf("GAME DRAW\n");
    }
    else if(result == 1){
        printf("YOU HAVE WON\n");
    }
    else{
        printf("SYSTEM HAS WON\n");
    }

    printf("Computer Chose %c, Your Choice %c", comp, user);
}

