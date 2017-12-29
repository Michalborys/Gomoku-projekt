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
    {
    case '1':



            printw("Witaj w grze Gomoku");
            mvprintw(2,13,"   1   2   3   4   5   6   7   8   9   ");
            mvprintw(3,13,"  /-----------------------------------");
            mvprintw(4,13,"a|   |   |   |   |   |   |   |   |   |");
            mvprintw(5,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(6,13,"b|   |   |   |   |   |   |   |   |   |");
            mvprintw(7,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(8,13,"c|   |   |   |   |   |   |   |   |   |");
            mvprintw(9,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(10,13,"d|   |   |   |   |   |   |   |   |   |");
            mvprintw(11,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(12,13,"e|   |   |   |   |   |   |   |   |   |");
            mvprintw(13,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(14,13,"f|   |   |   |   |   |   |   |   |   |");
            mvprintw(15,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(16,13,"g|   |   |   |   |   |   |   |   |   |");
            mvprintw(17,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(18,13,"h|   |   |   |   |   |   |   |   |   | ");
            mvprintw(19,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(20,13,"i|   |   |   |   |   |   |   |   |   |");
            mvprintw(21,13,"  -----------------------------------/");
            mvprintw(22,13," Gre rozpoczyna gracz nr 1- X ");
