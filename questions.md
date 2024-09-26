## 01
O valor da variável soma é 91;

## 02
```#include <stdio.h>
int main(){
     int fibSum = 0, n = 832040;
     int vector[50];
    
    // declaração de casos bases
    vector[0] = 0;
    vector[1] = 1;
    vector[2] = 1;
    
    // tratamento de casos bases
    if(n < 0){
        printf("Esse número não faz parte da sequência de Fibonacci!");
        return 0;
    }else if(n == 0 || n == 1 || n == 2){
        printf("Esse número faz parte da sequência de Fibonacci!");
        return 0;
        // aplicação da sequência lógica de fibonacci
    }else{
        for(int i = 3; fibSum <= n; i++){
            vector[i] = vector[i-1] + vector[i-2];
            fibSum = vector[i];
            if(fibSum == n){
                printf("Esse número faz parte da sequência de Fibonacci!");
                return 0;
            }
        }
    }
    
    printf("Esse número não faz parte da sequência de Fibonacci!");
    return 0;
}


## 03
#include <stdio.h>
int main(){
    double vector[] = {31490.7866, 37277.9400, 37708.4303, 0.0000, 0.0000, 17934.2269, 0.0000, 6965.1262, 24390.9374, 14279.6481, 0.0000, 0.0000, 39807.6622, 27261.6304, 39775.6434, 29797.6232, 17216.5017, 0.0000, 0.0000, 12974.2000, 28490.9861, 8748.0937, 8889.0023, 17767.5583, 0.0000, 0.0000, 3071.3283, 48275.2994, 10299.6761, 39874.1073};

    double maiorFaturamento, menorFaturamento, mediaDeFaturamentoMensal;
    int diasAcimaDaMediaMensal = 0;
    int diasValidos = 0;
    
    // tratamento da exceção dos dias com valores iguais a zero
    for(int i = 0; i < 30; i++){
        if(vector[i] > 0){
            diasValidos++;
        }
    }
    menorFaturamento = vector[0];
    maiorFaturamento = vector[0];

    // calculo da média mensal considerando os dias com valores acima de zero
    for(int i = 0; i < 30; i++){
        mediaDeFaturamentoMensal += vector[i] / diasValidos;
    }

    // comparações para pegar o menor e maior valor e os dias que ficaram com o valor de faturamento acima da média
    for(int i = 0; i < 30; i++){
        if(vector[i] > 0){
            if(vector[i] < menorFaturamento){
                menorFaturamento = vector[i];
            }
            if(vector[i] > maiorFaturamento){
                maiorFaturamento = vector[i];
            }
            if(vector[i] > mediaDeFaturamentoMensal){
                diasAcimaDaMediaMensal++;
            }
        }
    }

    printf("A média de faturamento mensal é R$%.4lf\n", mediaDeFaturamentoMensal);
    printf("O maior faturamento diário desse mês foi R$%.4lf\n", maiorFaturamento);
    printf("O menor faturamento diário desse mês foi R$%.4lf\n", menorFaturamento);
    printf("A quantidade de dias em que o faturamento diário esteve acima da média mensal foi %d", diasAcimaDaMediaMensal);
    
    return 0;
}



## 04
#include <stdio.h>
int main(){
    // declaração e inicialização de variáveis
    double faturamentoSP = 67836.43, faturamentoRJ = 36678.66, faturamentoMG = 29229.88, faturamentoES = 27165.48, faturamentoOutros = 19849.53, valorTotalMensal;
    float percentSP = 0, percentRJ = 0, percentMG = 0, percentES = 0, percentOutros = 0;

    // calculo do valor total, para depois calcular a porcentagem por Estado
    valorTotalMensal = faturamentoSP + faturamentoRJ + faturamentoMG + faturamentoES + faturamentoOutros;

    // calculo da porcentagem por Estado
    percentSP = ((faturamentoSP * 100) / valorTotalMensal);
    percentRJ = ((faturamentoRJ * 100) / valorTotalMensal);
    percentMG = ((faturamentoMG * 100) / valorTotalMensal);
    percentES = ((faturamentoES * 100) / valorTotalMensal);
    percentOutros = ((faturamentoOutros * 100) / valorTotalMensal);
    
    // Saídas
    printf("O faturamento do Estado de SP consiste em %.2f%%\n em relação ao valor total mensal da distribuidora.\n ", percentSP);
    printf("O faturamento do Estado do RJ consiste em %.2f%%\n em relação ao valor total mensal da distribuidora.\n ", percentRJ);
    printf("O faturamento do Estado de MG consiste em %.2f%%\n em relação ao valor total mensal da distribuidora.\n ", percentMG);
    printf("O faturamento do Estado do ES consiste em %.2f%%\n em relação ao valor total mensal da distribuidora.\n ", percentES);
    printf("O faturamento dos outros Estados consiste em %.2f%%\n em relação ao valor total mensal da distribuidora.\n ", percentOutros);

    return 0;
}


## 05
#include <stdio.h>
int main(){
    char string[] = "O rato roeu a roupa do Rei de Roma.";
    int sizeString = 0;
    
    // laço de repetição para descobrir o tamanho da string, mesmo já sabendo o tamanho, ter essa variável será útil
    while(string[sizeString] != '\0'){
        sizeString++;
    }

    // inversão de string
    for(int i = 0; i < sizeString/2; i++){
        char aux = string[i];
        string[i] = string[sizeString - i - 1];
        string[sizeString - i - 1] = aux;
         
    }

    // Saída da string invertida
    for(int i = 0; i < sizeString; i++){
        printf("%c", string[i]);
    }
    return 0;
}```
