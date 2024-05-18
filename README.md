import math
def calcular_entropia(texto_cifrado):
   
    frecuencias = {}
    total_caracteres = len(texto_cifrado)
    for caracter in texto_cifrado:
        if caracter in frecuencias:
            frecuencias[caracter] += 1
        else:
            frecuencias[caracter] = 1
   
    entropia = 0
    for frecuencia in frecuencias.values():
        probabilidad = frecuencia / total_caracteres
        entropia -= probabilidad * math.log2(probabilidad)
    
    return entropia

texto_cifrado_1 = "yulisa"
texto_cifrado_2 = "nataly"
texto_cifrado_3 = "del carmen"

entropia_1 = calcular_entropia(texto_cifrado_1)
entropia_2 = calcular_entropia(texto_cifrado_2)
entropia_3 = calcular_entropia(texto_cifrado_3)

print("Entropía para el sistema de cifrado 1:", entropia_1)
print("Entropía para el sistema de cifrado 2:", entropia_2)
print("Entropía para el sistema de cifrado 3:", entropia_3)
