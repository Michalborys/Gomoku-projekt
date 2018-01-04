#include <iostream>
#include <stdlib.h>
#include<ncurses/ncurses.h>
using namespace std;
int main()
{
    int board[10][10] = 
  {
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
    char znak;
    initscr();
    noecho();
    start_color();
    init_pair(1,COLOR_BLACK,COLOR_RED);
    attron(COLOR_PAIR(1));
    attron(A_BOLD);
    mvprintw(2,8,"   ____      _____       ___ ___       _____                        ");
    mvprintw(3,8,"|*|        (|     |)   (|   |   |)   (|     |)  *|   **   *|      |*");
    mvprintw(4,8,"|*|        *|     |*   *|   |   |*   *|     |*  *|  **    *|      |*");
    mvprintw(5,8,"|*|  ___   *|     |*   *|   |   |*   *|     |*  *| **     *|      |*");
    mvprintw(6,8,"|*|    |*) *|     |*   *|   |   |*   *|     |*  *|**      *|      |*");
    mvprintw(7,8,"|*|    |*| *|     |*   *|   |   |*   *|     |*  *|  **    *|      |*");
    mvprintw(8,8,"(*|____|*) (|_____|)   *|   |   |*   (|_____|)  *|    **  (|______|)");
    mvprintw(9,8,"   ----      -----      -   -   -      -----     -     -    ------  ");
    attroff(A_BOLD);
    attroff(COLOR_PAIR(1));
    start_color();
    init_pair(2,COLOR_BLACK,COLOR_WHITE);
    attron(COLOR_PAIR(2));
    mvprintw(13,18,"Nacisnij odpowiedni przycisk....\n");
    mvprintw(16,18,"1.START\n");
    mvprintw(19,18,"2.demo gry\n");
    mvprintw(22,18,"3.Czym jest Gomoku?\n");
    mvprintw(25,18,"4.Opusc gre\n");
    attroff(COLOR_PAIR(2));
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
            for(int i=0;i<40;i++)
        {
            refresh();
            mvprintw(23,13,"Podaj wspolrzedne gdzie chcesz umiescic X/O (1-9):");
            refresh();
            int x=getch()-'1'+1;
            mvprintw(24,13,"Podaj wspolrzedne gdzie chcesz umiescic X/O (a-i):");
            refresh();
            int y=getch()-'a'+1;
            if (board[x][y] == 0)
                {
            mvprintw(25,13,"Podano: %d %d", x, y);
            refresh();
            if (gracz1==1)
                {
            attron(A_BOLD);
            mvprintw(2+1+2*(y-1)+1, 13+1+4*(x-1)+2, "O");
            attroff(A_BOLD);
                }
            else
                {
            start_color();
            init_pair(3,COLOR_RED,COLOR_WHITE);
            attron(COLOR_PAIR(3));
            mvprintw(2+1+2*(y-1)+1, 13+1+4*(x-1)+2, "X");
            attroff(COLOR_PAIR(3));
                }
            board[x][y] = 1;
            gracz1=(gracz1+1)%2;
                }
            else
                {
            mvprintw(25 ,13,"Pole zajete");
                }
        }
        break;
