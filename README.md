#define _CRT_SECURE_NO_WARNINGS

#include <iostream>
#include <stdio.h>


int main() {
	setlocale(LC_ALL, "RU");

	const int an = 10, am = 8;
	int a[an][am];
	int n, m;

	do {
		printf("Введите число строк n (максимально %d): ", an);
		scanf("%d", &n);
	} while (n <= 0 || n > an);

	do {
		printf("Введите число столбцов m (максимально %d): ", am);
		scanf("%d", &m);
	} while (m <= 0 || m > am);

	printf("Вводите элементы матрицы \n");
	for (int i = 0; i < n; i++) {
		for (int j = 0; j < m; j++) {
			printf("a[%d][%d] = ", i, j);
			scanf("%d", &a[i][j]);
		}
	}
	int l[an];
	for (int i = 0; i < n; i++) {
		l[i] = 0;
		for (int j = 1; j < m; j++) 
		{
			if (a[i][j] >a[i][ l[i] ])
			{
				l[i] = j;
			}
		}
	}

	printf("\n");
	// Вывод элементов матрицы
	for (int i = 0; i < n; i++) {
		for (int j = 0; j < m; j++) {
			printf("%6d ", a[i][j]);
		}
		printf("\n");
	}

	printf("\n");
	// Вывод элементов вектора
	for (int i = 0; i < n; i++) {
		printf("%3d\n", l[i]);
	}
	
	scanf("%d", &n);
	return 0;
}
