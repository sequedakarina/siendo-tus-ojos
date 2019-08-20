# SIENDO-TUS-OJOS

<b>INTEGRANTES:</b><br>     VERÓNICA LUCENA (2152903)  
                            KARINA SEQUEDA (2152476)  
                            
<b>MOTIVACIÓN:</b> Algunos de los estudiantes que integran la comunidad UIS cuentan con discapacidad visual, muchos de ellos no poseen herramientas útiles para consultar la información que requieren, pues no todos los libros se encuetran en sistema braile. Es por esto que se decidió plantear una propuesta de solución, creando un mecanismo que les permite escuchar el texto que necesitan, a través de una fotografía.

<b>DESCRIPCIÓN GENERAL:</b> El proyecto busca implementar los conocimientos adquiridos en la asignatura respecto a
Deep-Learning. Se incorporan también transformaciones morfológicas tales como cierre, apertura, dilitación y erosión, que permiten localizar los objetos de interés en una imagen para luego proceder a segmentarlos, logrando así un buen reconocimiento de caracteres, a partir del ingreso de una imagen(Fotografía) con texto, haciendo lectura de este a través de un reproductor de voz.

<b>DATASET:</b> AbecedarioUIS--> Datos, Labels.

 <b>METODOLOGÍA Y DESCRIPCIÓN DE DATOS CAPTURADOS:</b> En el proyecto se empleará una base de datos propia, creada con la colaboración de un grupo de estudiantes de ingeniería de Sistemas, a quienes se les pidió escribir el alfabeto (excluyendo la ñ) en mayúscula y minúscula. El dataset cuenta con 832 imágenes etiquetadas, de las cuales se emplea el 80% para entrenamiento y el 20% para test.
 
El proyecto se desarrolla en cinco fases. En la primera fase se emplearán las imágenes del dataset para entrenar y evaluar el modelo con tres redes CNN, la primera red continene dos capas convolucionales, una con 30 y otra con 15 filtros, dos MaxPooling, un Dropout para evitar overfitting y dos full connected, una con 128 y otra con 50 neuronas, la segunda red contiene dos capas convolucionales, una con 32 y otra con 64 filtros, dos MaxPooling, dos Dropout y una full connected con 128 neuronas, la tercera red continene dos capas convolucionales, una con 6 y otra con 16 filtros, dos MaxPooling, un Dropout y dos full connected, una con 120 y otra con 84 neuronas, se evalua la precisión obtenida y se elige cuál debe implementarse. En la segunda fase se realiza el procesamiento de las imágenes que contienen las palabras a analizar, para ello se implementa la transformación morfológica denominada erosión, que permite adelgazar el objeto de interés, seguido de una apertura (elimina los puntos blancos presentes en un fondo negro), dilatación, cierre (elimina puntos negros presentes en un fondo blanco) y nuevamente erosión; después de esto se hace la segmentación. En la tercera fase se pasan los datos a la red neuronal seleccionada. En la cuarta fase se transforman y concatenan los números arrojados por la red neuronal a las letras correspondientes para formar la palabra inicial. Por último, en la quinta fase, se toma el vector con la palabra final y se pasa a la librería que la leerá. 

