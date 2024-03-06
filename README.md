# Fun-o-linguagem-C

#include <stdio.h>
#include <stdlib.h>

int main() {
    // Crie um ponteiro que indique uma variável do tipo inteiro
    int *ptr;
    
    // Defina que esse ponteiro é igual à alocação de memória para guardar oito dados do tipo inteiro
    ptr = (int *)malloc(8 * sizeof(int));
    
    if (ptr == NULL) {
        printf("Erro ao alocar memória.\n");
        return 1;
    }
    
    // Efetue a realocação de memória para um tamanho que guarde doze dados inteiros
    int *temp = (int *)realloc(ptr, 12 * sizeof(int));
    if (temp != NULL) {
        ptr = temp;
    } else {
        printf("Erro ao realocar memória.\n");
        free(ptr);
        return 1;
    }
    
    // Libere o espaço alocado nas funções anteriores
    free(ptr);
    
    return 0;
}
