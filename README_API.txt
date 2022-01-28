-------------Archivo que describe el parsing API de la pagina exchangerates-----------------

Objetivo: Hallar los tipos de cambio de las distintas monedas a nivel mundial usando al euro como referencia

1. Se importan las librerias:
  1.a json
  1.b requests

2. Se entra a la siguiente direccion: https://exchangeratesapi.io/

3. Una vez dentro se le da click a la pestaña 'Get API key'

4. Se le pedira crear un perfil dentro de la plataforma

5. Una vez creado su usuario, se le dara acceso a su propia llave API

6. Para tener acceso a los tipos de cambio actualizados se usa la url: ''http://api.exchangeratesapi.io/v1/latest?'
   seguido de la llave API generada en el paso anterior.

7. Para poder observar cualquier otra fecha anterior, se estructurara la url de la siguiente forma:
  7a. url principal: 'http://api.exchangeratesapi.io/v1/'
  7b. la fecha a consultar con el siguiente formato: 'AAAA-MM-DD'
  7c. url secundaria: '?access_key='
  7d. Llave API generada
  7e. Concatenamos los incisos anteriores: url principal+fecha+url secundaria+Llave API

8. Generamos un margen de datos usando 'Pandas'

9. Exportamos nuestra base de datos a un archivo 'csv' usando la funcion 'to_csv'