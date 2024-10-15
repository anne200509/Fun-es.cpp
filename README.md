# Funções.cpp
#include <iostream>
using namespace std;

// Função que lê um número e verifica se é positivo
int leNumeroPositivo() {
    int num;
    do {
        cout << "Digite um numero inteiro positivo: ";
        cin >> num;
        if (num <= 0) {
            cout << "Numero invalido. Deve ser um inteiro positivo." << endl;
        }
    } while (num <= 0); // Repete até o número ser positivo
    return num;
}

// Função que calcula a soma dos divisores de um número, exceto ele mesmo
int somaDivisores(int num) {
    int soma = 0;
    // Itera de 1 até num - 1 (divisores)
    for (int i = 1; i < num; i++) {
        if (num % i == 0) { // Se i for divisor de num
            soma += i;
        }
    }
    return soma;
}

int main() {
    const int TOTAL_NUMEROS = 5; // Definimos que o usuário deve inserir 5 números
    int num, soma;

    // Ler 5 números inteiros positivos e calcular a soma dos divisores
    for (int i = 0; i < TOTAL_NUMEROS; i++) {
        num = leNumeroPositivo(); // Lê o número positivo
        soma = somaDivisores(num); // Calcula a soma dos divisores
        cout << "A soma dos divisores de " << num << " (exceto ele mesmo) é: " << soma << endl;
    }

    return 0;
}
