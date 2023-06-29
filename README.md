## GeneradorRostrosGAN

Resumen de los resultados que obtuve al experimentar con una red GAN.

### Que es una Redes Neuronales Generativa Adversaria (GAN)

En una red adversaria se tienen dos modelos (que pueden ser Redes Neuronales o Convolucionales) compitiendo: un Generador y un Discriminador.

Se genera un primer modelo que llamaremos Discriminador para que sea capaz de reconocer rostros humanos. Este discriminador será simplemente un clasificador,que buscara indicar si una imagen es real o falsa

Se genera un segundo modelo, que llamaremos Generador y nuestro objetivo es entrenarlo para que sea capaz de tomar una entrada aleatoria y a la salida generar algo muy parecido a una imagen de un rostro.

La idea es entrenar esos dos modelos simultáneamente buscando que al final sea el Generador el vencedor en esta competencia. La idea del entrenamiento es la siguiente:

    1. “Descongelar” los coeficientes del Discriminador
    2. Entrenar solo el Discriminador con imagenes falsas y reales
    3. “Congelar” los coeficientes del Discriminador
    4. Entrenar la GAN, al estar congelado el discriminador únicamente se entrenara el Generador
    5. Repetir los pasos 1 a 4 por el número de iteraciones que se vayan a usar el entrenamiento
    
### Resultados de modelos

#### Modelo 2 (el 1 tenia un error por lo que se descarto)
Se usaron imagenes de 32x32 y redes convolucionales. Se optuvo como resultado:
![resultado](\resultados\resultadosGAN-2\r5000.png)
El modelo esta estancado no logra generar imagen alguna
