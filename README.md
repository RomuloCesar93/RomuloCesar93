def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        L = arr[:mid]
        R = arr[mid:]

        merge_sort(L)
        merge_sort(R)

        i = j = k = 0


        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1


        while i < len(L):
            arr[k] = L[i]
            i += 1
            k += 1

        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1


arr = [12, 11, 13, 5, 6, 7]
merge_sort(arr)
print("Array ordenado pelo Merge Sort:", arr)

def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    else:
        chave = arr[0]
        mac = [x for x in arr[1:] if x <= chave]
        o_chave = [x for x in arr[1:] if x > chave]
        return quick_sort(mac) + [chave] + quick_sort(o_chave)


arr = [10, 7, 8, 9, 1, 5]
arr_sorted = quick_sort(arr)
print("Array ordenado pelo Quick Sort:", arr_sorted)

def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    else:
        chave = arr[0]
        mac = [x for x in arr[1:] if x <= chave]
        o_chave = [x for x in arr[1:] if x > chave]
        return quick_sort(mac) + [chave] + quick_sort(o_chave)


arr = [10, 7, 8, 9, 1, 5]
arr_sorted = quick_sort(arr)
print("Array ordenado pelo Quick Sort:", arr_sorted)


def shell_sort(arr):
    if len(arr) <= 1:
        return arr
    else:
        chave = arr[0]
        mac = [x for x in arr[1:] if x <= chave]
        o_chave = [x for x in arr[1:] if x > chave]
        return quick_sort(mac) + [chave] + quick_sort(o_chave)


arr = [10, 7, 8, 9, 1, 5]
arr_sorted = quick_sort(arr)
print("Array ordenado pelo Quick Sort:", arr_sorted)

def insertion_sort(arr):
    for i in range(1, len(arr)):
        chave = arr[i]
        j = i - 1
        while j >= 0 and chave < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = chave


arr = [12, 11, 13, 5, 6]
insertion_sort(arr)
print("Array ordenado pelo Insertion Sort:", arr)

def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_id = i
        for j in range(i+1, n):
            if arr[j] < arr[min_id]:
                min_id = j
        arr[i], arr[min_id] = arr[min_id], arr[i]


arr = [64, 25, 12, 22, 11]
selection_sort(arr)
print("Array ordenado pelo Selection Sort:", arr)


def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]

arr = [64, 34, 25, 12, 22, 11, 90]
bubble_sort(arr)
print("Array ordenado pelo Bubble Sort:", arr)





def merge_sort(arr):
    # Função para ordenar um array usando o Merge Sort
    if len(arr) > 1:
        mid = len(arr) // 2  ------------- Encontra o ponto médio do array
        L = arr[:mid]        ----------------- Divide o array em duas metades
        R = arr[mid:]

        merge_sort(L)  ------------- Ordena a primeira metade
        merge_sort(R)  #------------------Ordena a segunda metade

        i = j = k = 0  # Índices para L, R e arr

     ----------------------Combina as duas metades ordenadas
        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1

        # Copia os elementos restantes de L, se houver
        while i < len(L):
            arr[k] = L[i]
            i += 1
            k += 1

        # Copia os elementos restantes de R, se houver
        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1


def quick_sort(arr):
    # Função para ordenar um array usando o Quick Sort
    if len(arr) <= 1:
        return arr  # Retorna o array se estiver vazio ou tiver um único elemento
    else:
        chave = arr[0]  # Escolhe o primeiro elemento como pivô
        # Particiona os elementos em dois subarrays
        mac = [x for x in arr[1:] if x <= chave]  # Elementos menores ou iguais ao pivô
        o_chave = [x for x in arr[1:] if x > chave]  # Elementos maiores que o pivô
        # Chama recursivamente o Quick Sort nas duas partes e combina
        return quick_sort(mac) + [chave] + quick_sort(o_chave)


def shell_sort(arr):
    # Função para ordenar um array usando o Shell Sort
    n = len(arr)
    gap = n // 2  # Inicializa a distância (gap)

    # Reduz o gap até que ele seja 0
    while gap > 0:
        # Realiza uma inserção em cada subarray definido pelo gap
        for i in range(gap, n):
            temp = arr[i]  # Elemento a ser posicionado
            j = i
            # Move os elementos do subarray para a direita
            while j >= gap and arr[j - gap] > temp:
                arr[j] = arr[j - gap]
                j -= gap
            arr[j] = temp  # Insere o elemento na posição correta
        gap //= 2  # Reduz o gap


def insertion_sort(arr):
    # Função para ordenar um array usando o Insertion Sort
    for i in range(1, len(arr)):
        chave = arr[i]  # O elemento a ser inserido
        j = i - 1
        # Move os elementos do array que são maiores que a chave para uma posição à frente
        while j >= 0 and chave < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = chave  # Insere a chave na posição correta


def selection_sort(arr):
    # Função para ordenar um array usando o Selection Sort
    n = len(arr)
    for i in range(n):
        min_id = i  # Assume que o primeiro elemento é o menor
        # Encontra o menor elemento no array não ordenado
        for j in range(i + 1, n):
            if arr[j] < arr[min_id]:
                min_id = j
        arr[i], arr[min_id] = arr[min_id], arr[i]  # Troca o menor elemento encontrado com o primeiro


def bubble_sort(arr):
    # Função para ordenar um array usando o Bubble Sort
    n = len(arr)
    # Passa pelo array várias vezes
    for i in range(n):
        # Compara elementos adjacentes e os troca se estiverem na ordem errada
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]  # Troca os elementos

# Testando os algoritmos de ordenação
arr_merge = [12, 11, 13, 5, 6, 7]
merge_sort(arr_merge)
print("Array ordenado pelo Merge Sort:", arr_merge)

arr_quick = [10, 7, 8, 9, 1, 5]
arr_sorted_quick = quick_sort(arr_quick)
print("Array ordenado pelo Quick Sort:", arr_sorted_quick)

arr_shell = [12, 11, 13, 5, 6]
shell_sort(arr_shell)
print("Array ordenado pelo Shell Sort:", arr_shell)

arr_insertion = [12, 11, 13, 5, 6]
insertion_sort(arr_insertion)
print("Array ordenado pelo Insertion Sort:", arr_insertion)

arr_selection = [64, 25, 12, 22, 11]
selection_sort(arr_selection)
print("Array ordenado pelo Selection Sort:", arr_selection)

arr_bubble = [64, 34, 25, 12, 22, 11, 90]
bubble_sort(arr_bubble)
print("Array ordenado pelo Bubble Sort:", arr_bubble)
