                                               #include <iostream>
#include <stdlib.h>
#include<ncurses/ncurses.h>

using namespace std;

int main()
{
    int board[10][10] = {
        {0,0,0,0,0,0,0,0,0},
        {0,0,0,0,0,0,0,0,0},
        {0,0,0,0,0,0,0,0,0},
        {0,0,0,0,0,0,0,0,0},
        {0,0,0,0,0,0,0,0,0},
        {0,0,0,0,0,0,0,0,0},
        {0,0,0,0,0,0,0,0,0},
        {0,0,0,0,0,0,0,0,0},
        {0,0,0,0,0,0,0,0,0},
    };
    int gracz1;
int gracz2;
    char znak;
    initscr();
    noecho();
    int kol,rz;
    getmaxyx(stdscr,kol,rz);
    printw("Nacisnij odpowiedni przycisk....\n");
    printw("1.START\n");
    printw("2.demo gry\n");
    printw("3.Sterowanie\n");
    printw("4.Opusc gre\n");
    znak=getch();
    clear();
    switch(znak)
