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
        if((board[x][y]==1&&board[x][y+1]==1&&board[x][y+2]==1&&board[x][y+3]==1&&board[x][y+4]==1)
                   ||( board[x][y]==1&&board[x][y-1]==1&&board[x][y-2]==1&&board[x][y-3]==1&&board[x][y-4]==1)
                   ||(board[x][y]==1&&board[x+1][y]==1&&board[x+2][y]==1&&board[x+3][y]==1&&board[x+4][y]==1)
                   ||(board[x][y]==1&&board[x-1][y]==1&&board[x-2][y]==1&&board[x-3][y]==1&&board[x-4][y]==1)
                   ||(board[x][y]==1&&board[x+1][y+1]==1&&board[x+2][y+2]==1&&board[x+3][y+3]==1&&board[x+4][y+4]==1)
                   ||(board[x][y]==1&&board[x-1][y-1]==1&&board[x-2][y-2]==1&&board[x-3][y-3]==1&&board[x-4][y-4]==1)
                   )
                {
                   attron (A_BOLD);

                    mvprintw(28,13,"5 (lub wiecej) znakow pod rzad ");
                    mvprintw(29,13,"Wybierz:");
                    mvprintw(30,13,"d- graj dalej, rozne znaki");
                    mvprintw(31,13,"s- wygrana gracza 1- Brawo ");
                    mvprintw(32,13,"f- wygrana gracza 2- Brawo");
                    attroff (A_BOLD);
                    char znak3;
                    znak3=getch();
                    switch(znak3)
                    {
                    case 'd':
                        mvprintw(33,13,"Graj dalej");
                        attron(A_BOLD|A_DIM);
                        mvprintw(34,13,"Podazaj za kursorem");
                        attroff(A_BOLD|A_DIM);

                        continue;
                    case 's':
                        return 0;
                        break;


                    case 'f':

                            return 0;
                            break;
                    }

                }

        }
    break;
    case '2':
            mvprintw(2,13,"   1   2   3   4   5   6   7   8   9   ");
            mvprintw(3,13,"  /-----------------------------------");
            mvprintw(4,13,"a|   | X | X | X | X | X |   |   |   |");
            mvprintw(5,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(6,13,"b|   |   |   |   |   |   |   |   |   |");
            mvprintw(7,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(8,13,"c|   |   |   |   |   | O |   |   |   |");
            mvprintw(9,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(10,13,"d|   |   |   |   |   | O |   |   |   |");
            mvprintw(11,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(12,13,"e|   | X |   |   |   | O |   |   |   |");
            mvprintw(13,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(14,13,"f|   |   | O |   |   | O |   |   |   |");
            mvprintw(15,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(16,13,"g|   |   |   | X |   | O |   |   |   |");
            mvprintw(17,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(18,13,"h|   |   |   |   | O |   |   |   |   | ");
            mvprintw(19,13," |---+---+---+---+---+---+---+---+---|");
            mvprintw(20,13,"i|   |   |   |   |   | X |   |   |   |");
            mvprintw(21,13,"  -----------------------------------/");
          refresh();
            mvprintw(23,13,"Tak wyglada plansza do gry");
            mvprintw(24,13,"Twoje zadanie to:");
            mvprintw(25,13,"1.Podanie pierwszej wspolrzednej (1-9) ");
            mvprintw(26,13,"2.Podanie drugiej wspolrzednej (a-i)");
            mvprintw(27,13,"Chcesz sprubowac??");
            mvprintw(28,13,"Wcisnij 1,aby przejsc do gry");
            mvprintw(29,13,"2.Wyjscie");
            char znak1;
            znak1=getch();
            clear();
            switch (znak1)
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
                 if((board[x][y]==1&&board[x][y+1]==1&&board[x][y+2]==1&&board[x][y+3]==1&&board[x][y+4]==1)
                   ||( board[x][y]==1&&board[x][y-1]==1&&board[x][y-2]==1&&board[x][y-3]==1&&board[x][y-4]==1)
                   ||(board[x][y]==1&&board[x+1][y]==1&&board[x+2][y]==1&&board[x+3][y]==1&&board[x+4][y]==1)
                   ||(board[x][y]==1&&board[x-1][y]==1&&board[x-2][y]==1&&board[x-3][y]==1&&board[x-4][y]==1)
                   ||(board[x][y]==1&&board[x+1][y+1]==1&&board[x+2][y+2]==1&&board[x+3][y+3]==1&&board[x+4][y+4]==1)
                   ||(board[x][y]==1&&board[x-1][y-1]==1&&board[x-2][y-2]==1&&board[x-3][y-3]==1&&board[x-4][y-4]==1)
                   )
                {
                   attron (A_BOLD);

                    mvprintw(28,13,"5 (lub wiecej) znakow pod rzad ");
                    mvprintw(29,13,"Wybierz:");
                    mvprintw(30,13,"d- graj dalej, rozne znaki");
                    mvprintw(31,13,"s- wygrana gracza 1- Brawo ");
                    mvprintw(32,13,"f- wygrana gracza 2- Brawo");
                    attroff (A_BOLD);
                    char znak3;
                    znak3=getch();
                    switch(znak3)
                    {
                    case 'd':
                        mvprintw(33,13,"Graj dalej");
                        attron(A_BOLD|A_DIM);
                        mvprintw(34,13,"Podazaj za kursorem");
                        attroff(A_BOLD|A_DIM);
                        continue;
                    case 's':
                    return 0;
                    break;
                    case 'f':
                    return 0;
                    break;
                    }

                }
        }
            break;
            case '2':
            exit(1);
            break;
        }
    break;
    case '3':
             start_color();
             init_pair(4,COLOR_BLACK,COLOR_GREEN);
             attron(COLOR_PAIR(4));
             mvprintw(6,15," Wybierz co chcesz sie dowiedziec:");
             mvprintw(10,15,"a- historia gry");
             mvprintw(14,15,"b- o co chodzi w GOMOKU?");
             mvprintw(18,15,"c- ciekawostki");
             attroff(COLOR_PAIR(4));
             char znak2;
             znak2=getch();
             clear ();
             switch (znak2)
             {
             case 'a':
             mvprintw(4,10,"1.Gra wymyslona w Japonii");
             mvprintw(8,4,"2.Jej historia siega VII wieku p.n.e");
             mvprintw(12,10,"3.W 1989 i 1991 odbyly sie Mistrzostwa Swiata w Gomoku Pro");
             mvprintw(16,4,"4.W 2009 roku zawody wznowiono, zmieniono odmiane gry z pro na swap2");
             mvprintw(20,10,"5.Polak Artur Tamiola w 2009 zostal mistrzem swiata gry GOMOKU");
             mvprintw(24,4,"6.Natomiast w 2016 w Tallinie Polacy zostali druzynowymi mistrzami swiata");
             break;
             case 'b':
             start_color();
             init_pair(5,COLOR_RED,COLOR_BLACK);
             attron(COLOR_PAIR(5));
             mvprintw(4,10,"1.Jest to gra strategiczno-logiczna");
             mvprintw(8,3,"2.Nazywana rowniez Kolko i krzyzyk do pieciu");
             mvprintw(12,10,"3.Przeznaczona dla 2 graczy");
             mvprintw(16,3,"4.Plansza do gry ma rozmiar 9x9");
             mvprintw(20,10,"5.Gomoku to gra dla doroslych i dzieci w wieku 5+ ");
             mvprintw(24,3,"6.Pozadane sa umiejetnosci myslenia logicznego, strategicznego i taktycznego");
             attroff(COLOR_PAIR(5));
             break;
             case 'c':
             start_color();
             init_pair(6,COLOR_BLUE,COLOR_BLACK);
             attron(COLOR_PAIR(6));
             mvprintw(4,10,"1.Najczesciej mistrzami swiata w Gomoku zostawali Wegrzy");
             mvprintw(8,4,"2.W Polsce dziala Polskie Stowarzyszenie Gomoku, Renju i Pente");
             mvprintw(12,10,"3.Mistrzami swiata zostawali tylko przedstawiciele 4 krajow");
             mvprintw(16,4,"4.Sa to Czesi, Wegrzy, Placy i Rosjanie");
             mvprintw(20,10,"5.gomokuworld.com to oficjalna strona poswiecona Gomoku");
             mvprintw(24,4,"6.W gre mozna zagrac online na wielu stronach internetowych");
             attroff(COLOR_PAIR(6));
             break;
             default:
             mvprintw(15,15,"Zle wybrales- wyjscie z gry");
             }

    break;
    case '4':
            exit(1);
    break;
    default:
            mvprintw(6,19,"Zly wybor menu ");
    }
    getch();
    endwin();
    return 0;
}





                 
