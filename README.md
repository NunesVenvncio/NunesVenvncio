#include <iostream>
#include <vector>
#include <algorithm>

// Função de busca binária
int buscaBinaria(const std::vector<int>& vetor, int alvo) {
    int esquerda = 0;
    int direita = vetor.size() - 1;

    while (esquerda <= direita) {
        int meio = esquerda + (direita - esquerda) / 2;

        // Verifica se o elemento alvo está presente no meio
        if (vetor[meio] == alvo) {
            return meio; // Elemento encontrado
        }
        // Se o alvo é maior, ignore a metade esquerda
        else if (vetor[meio] < alvo) {
            esquerda = meio + 1;
        }
        // Se o alvo é menor, ignore a metade direita
        else {
            direita = meio - 1;
        }
    }
    return -1; // Elemento não encontrado
}

int main() {
    std::vector<int> vetor = {1, 3, 5, 7, 9, 11, 13, 15, 17, 19}; // Vetor ordenado
    int alvo = 7;

    int resultado = buscaBinaria(vetor, alvo);

    if (resultado != -1) {
        std::cout << "Elemento encontrado no índice: " << resultado << std::endl;
    } else {
        std::cout << "Elemento não encontrado." << std::endl;
    }

    return 0;
}
