-------------Archivo que describe el web scraping de la pagina Goodreads-----------------

Objetivo: Encontrar los mejores libros de Machine Learning clasificados

1. Se importan las librerias de:
  1.a numpy as np
  1.b pandas as pd
  1.c re
  1.d requests
  1.e urllib
  1.f from bs4 import BeautifulSoup
 
2. La url con la que se trabajara es la siguiente:
  'https://www.goodreads.com/list/show/24366.Best_machine_learning_books'

3. Dicha url se convierte a un archivo html con las funciones 'requests' y 'content'

4. Hecho esto, a su vez usamos el importe 'BeautifulSoup' trabajando ahora con un archivo 'lxml'

5. El siguiente procedimiento lo haremos acabo para tres variables que queremos encontrar: el titulo del libro, su autor y el puntaje dado por los compradores
  
6. Para ubicar el titulo del libro:
  6a. El titulo del libro se encuentra a un lado del objeto 'a' dentro de la clase 'bookTitle'
  6b. Se extrae cada elemento dentro de la cadena usando un ciclo for y usando la funcion 'text'
  6c. Nos deshacemos de los saltos de linea con la funcion 'strip'

7. Para ubicar al autor:
  7a. El autor se encuentra a un lado del objeto 'a' dentro de la clase 'authorName'
  7b. Se extrae cada elemento dentro de la cadena usando un ciclo for y usando la funcion 'text'
  7c. Nos deshacemos de los saltos de linea con la funcion 'strip'


8. Para ubicar el puntaje dado por los compradores:
  8a. El puntaje se encuentra dentro de la clase 'minirating'
  8b. Se extrae cada elemento dentro de la cadena usando un ciclo for y usando la funcion 'text'
  8c. Nos deshacemos de los saltos de linea con la funcion 'strip'
  8d. El obstaculo mas grande en este punto, es que se encontrara el puntaje junto con algunas reseñas dejadas
      por los compradores como 'it was amazing', 'liked it ', 'it was ok ', y demas, junto con algunos anglicismos
      que deben ser traducidos al español. La funcion que nos ayudara en este paso sera el de 'replace'

9. Se verifica que las 3 variables antes mencionadas tengan la misma longitud usando la funcion 'len'

10. Convertimos las 3 variables (titulo del libro, autor y puntaje) en una lista usando la funcion 'zip'

11. Convertimos las 3 variables en columnas con la funcion 'columns' y las renombramos como: 'Libros Machine Learning, 'Autor' y 'Calificacion escala 1 al 5'

12. Convertimos el conjunto de datos a un DataFrame usado 'Pandas'

13. LLevamos la base de datos a un formato 'csv' usando la funcion 'to_csv'