# casandra
temperaturas de las ciudades 
def calcular_temperatura_promedio(datos_temperatura):
    """
    Calcula la temperatura promedio de cada ciudad a partir de un diccionario de datos.

    :param datos_temperatura: Diccionario con ciudades como claves y listas de temperaturas semanales como valores.
    :return: Diccionario con ciudades y sus temperaturas promedio.
    """
    promedios = {}

    for ciudad, temperaturas in datos_temperatura.items():
        promedio = sum(temperaturas) / len(temperaturas)
        promedios[ciudad] = round(promedio, 2)  # Redondear a 2 decimales

    return promedios

# Datos de prueba (ejemplo con 3 ciudades y 4 semanas de temperaturas)
datos = {
    "Quito": [15, 16, 14, 15, 16, 17, 16, 15, 14, 15, 14, 16],
    "Guayaquil": [28, 29, 30, 31, 32, 31, 30, 29, 28, 27, 29, 30],
    "Cuenca": [10, 11, 12, 13, 12, 11, 10, 9, 10, 11, 12, 13]
}

# Prueba de la función
resultado = calcular_temperatura_promedio(datos)

# Mostrar resultados
for ciudad, promedio in resultado.items():
    print(f"{ciudad}: {promedio}°C")
