# TFB

#include <stdio.h>
#include <conio.h>
#include <time.h>
#include <stdlib.h>
#define MAX 15

int main() {

	srand(time(0));
	char players[100][15];
	int noOfPlayers = 0;
	
	
	while (1) {
		printf_s("\nPress 1 to add player or 2 to roll\n\n");
		while (!_kbhit()) {
		}
		int x = _getch();
		if (x == '1') {
			printf_s("type player name\n");

			fgets(players[noOfPlayers], MAX, stdin);

			printf_s("\nplayer added: %s\n\n", players[noOfPlayers]);
			
			noOfPlayers++;

			printf_s("Players are:\n\n");
			for (int i = 0; i < noOfPlayers; i++) {
				printf_s("%s", players[i]);
			}
		}




		else if (x == '2') {
			if (noOfPlayers < 1) {
				printf_s("add a player\n");
			}
			else {
				int amount = rand() % 3 + 1;
				int person = rand() % noOfPlayers;
				printf_s("\n%s ", players[person]);
				if (amount == 1) {
					printf_s("3\n");
				}
				if (amount == 2) {
					printf_s("5\n");
				}
				if (amount == 3) {
					printf_s("BUND\n");
				}
			}
		}

		else {
			printf_s("Wrong button\n");
		}

	}
