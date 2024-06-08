# Medicion-de-trafico-con-OpenCV-Python
scripts autogeneran un video desde una cámara de trafico en tiempo real, lee el video, define un área específica en la calle, detecta movimiento en esa área usando sustracción de fondo, encuentra contornos que representan coches, cuenta los coches que cruzan una línea específica y muestra el conteo en pantalla.

1. Importación de Librerías: Se importan OpenCV, numpy e imutils.

2. Lectura del Video: Se especifica el video de entrada (sample.mp4).

Configuración Inicial:

Se crea un sustractor de fondo con cv2.bgsegm.createBackgroundSubtractorMOG().
Se define un kernel morfológico.
Se inicializa un contador de autos (car_counter).
Procesamiento de Fotogramas:

Se leen los fotogramas del video y se redimensionan a 640 píxeles de ancho.
Se especifican los puntos extremos del área de interés en la autopista.
Definición del Área de Interés:

Se crea una imagen auxiliar de ceros (imAux).
Se dibuja el contorno del área de interés en esta imagen auxiliar.
Aplicación de Sustracción de Fondo:

Se aplica la sustracción de fondo a la imagen del área de interés.
Se usan transformaciones morfológicas para mejorar la imagen binaria.
Detección de Contornos:

Se encuentran los contornos en la imagen binaria.
Se analiza cada contorno para determinar si corresponde a un auto (si el área es mayor a 1500 píxeles).
Se dibujan rectángulos alrededor de los autos detectados.
Conteo de Autos:

Se verifica si el punto superior derecho del contorno del auto cruza una línea amarilla en el eje x (entre 440 y 460).
Si cruza, se incrementa el contador de autos y se dibuja una línea verde.
Visualización:

Se dibujan el contorno del área de interés y una línea amarilla central.
Se muestra el contador de autos en un rectángulo verde a la derecha.
Se visualiza el fotograma con todos los elementos anteriores.
Finalización:

Se liberan los recursos del video y se cierran las ventanas de visualización al presionar la tecla ESC.
