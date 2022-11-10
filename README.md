João Pedro Vieira Caramelo 

Bubble sort:

Compara pares de elementos adjacentese os troca de lugar se estiverem na ordem errada. Esse processo se repete até que mais nenhuma troca seja necessária (elementos já ordenados)
Possui complexidade C(n) = O(n) no melhor caso e C(n) = O(n²) no pior caso. Não recomendado para grandes conjuntos de dados.

Código:

void bubbleSort (int *V , int N) {
	int i, continua, aux, fim = N;
	do{
		continua = 0;
		for (i=0; i < fim-1; i++){
			if (V[i] > V[i+1]{
				aux = V[i];
				V[i] = V[i+1];
				v[i+1] = aux;
				continua = i.
			}
		}
		fim --;
	}while (continua !=0);	
}

Insertion Sort:

Percorre um vetor da esquerda para a direita e vai ordenando os elementos à esquerda. Possui complexidade C(n) = O(n) no melhor caso e C(n) = O(n²) no caso médio e pior caso. É um método de ordenação estável, não altera a ordem de dados iguais. Capaz de ordenar os dados a medida que recebe (tempo real).

Código:

void insertionSort (int *V, int N){
	int i, j, aux;
	for (i=1; i < N; i++){
		aux = V[i];
		for (j=i; (j > 0) && (aux < V[j - 1]) ; j--)
			V[j] = V[j - 1];
	 	V[j] = aux;
    }
}

Selection Sort:

A cada passo, procura o menor valor do array e o coloca na primeira posição do array. Descarta-se a primeira posição do array e repete-se o processo para a segunda posição. Isso é feita para todas as posições do array
Possui complexidade C(n) = O(n²) em todos os casos. Ineficiente para grandes conjuntos de dados. É um método estável, não altera a ordem de dados iguais.

Código:

void selectionSort(int *V, int N){
    int i, j, menor, troca;
    for (i = 0; i < N-1; i++){
        menor = i;
	for (j = i+1; j < N; j++){
            if (V[j] < V[menor])
	        menor = j;
	}
	if(i !=menor){
		troca = V[i];
		V[i] = V[menor];
		v[menor] = troca;
	}
    }
}

Quick sort:

É o método de ordenação interna mais rápido e mais utilizado que se conhece. Possui complexidade C(n) = O(n²) no pior caso e C(n) = O(n log n) no melhor e médio caso e não é um algorítmo estável. 
Emprega a estratégia "divisão e conquista". Um elemento é escolhido como pivô. Particiona, os dados são rearranjados (valores menores do que o pivô são colocados antes dele e os maiores, depois). Recursivamente ordena as 2 partições.

Código:

void quickSort (int *V, int inicio, int fim) {
	int pivo;
	if(fim > inicio) {
		pivo = particiona(V, inicio, fim);
		quickSort (V, inicio, pivo-1);
		quickSort (V, pivo+1, fim);
	}
}

int particiona (int *V, int inicio, int final) {
	int esq, dir, pivo, aux;
	esq = inicio;
	dir = final;
	pivo = V[inicio];
	while(esq < dir){
		while(V[esq] <= pivo)
			esq++;
		while(V[dir] > pivo)
			dir--;
		if(esq < dir){
			aux = V[esq];
			V[esq] = V[dir];
			V[dir] = aux;
		}
	}
	V[inicio] = V[dir];
	V[dir] = pivo;
	return dir;
}



