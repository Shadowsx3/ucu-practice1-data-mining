# UCU 2024 - Practice 1: Data Mining

## REST API

### Consumo de Datos Históricos Financieros desde una API y Exportación a JSON

#### Modalidad de presentación

1. Debes crear un repositorio en tu cuenta de GitHub desde el siguiente template:

https://github.com/hchocobar/ucu-2024-practice-1-data-mining

2. Luego en tu repositorio, debes editar el archivo practice.ipynb para resolver la práctica.

3. Finalmente, en WebAsignatura debes presentar el enlace a tu repositorio. Para ello debes:

     a. Pulsar el enlace "Enviar su trabajo" (más arriba, en el segundo cuadro debajo de "Fase de envío/ Fase actual"),

     b. Pulsar el botón "Adicionar envío"

     c. Completar la información "Título" y "Contenido del envío"

     d. Pulsar el botón "Guardar cambios"

#### Enunciado:

**Objetivo:** El objetivo de este ejercicio es que los estudiantes consuman datos históricos de una criptomoneda utilizando una API financiera, extraigan la información requerida y la guarden en un archivo en formato JSON.

#### Requisitos del ejercicio:

1. **Obtener datos históricos:** Utiliza la API de CoinGecko para obtener los datos históricos de precios de Bitcoin. Debes consultar el precio de Bitcoin para una serie de fechas específicas.

2. **URL de la API:** Utiliza la siguiente URL de la API de CoinGecko para consultar los precios históricos de Bitcoin:
   
   ```bash
   https://api.coingecko.com/api/v3/coins/bitcoin/history?date=DD-MM-YYYY
   ```
   
   - **Nota:** Cambia `DD-MM-YYYY` por la fecha que deseas consultar en formato día-mes-año (por ejemplo, `30-12-2020`).

3. **Fechas a consultar:**
   
   - 01-01-2022
   - 01-07-2022
   - 01-01-2023
   - 01-07-2023
   - 01-01-2024
   - 01-07-2024

4. **Datos a extraer:**
   
   - Precio en USD.
   - Precio en EUR.

5. **Instrucciones:**
   
   - Realiza una solicitud HTTP GET a la API para cada una de las fechas indicadas.
   - Extrae los datos mencionados (precio en USD, precio en EUR).
   - Guarda estos datos en un archivo en formato JSON llamado `bitcoin_historical_data.json`.

6. **Formato esperado del archivo JSON:**
   El archivo debe contener la siguiente estructura:
   
   ```json
   {
       "data": [
           {
               "date": "01-01-2022",
               "price_usd": 47832.12,
               "price_eur": 42000.45,
               "market_cap": 896540123456
           },
           {
               "date": "01-07-2022",
               "price_usd": 19845.89,
               "price_eur": 18850.34,
               "market_cap": 423540987654
           },
           ...
       ]
   }
   ```

7. **Manejo de errores:**
   
   - Verifica que las solicitudes sean exitosas (código de estado 200). Si hay un error en la solicitud, imprime un mensaje en consola.
   - Si algún dato no está disponible para la fecha consultada, el valor debe ser `null` en el archivo JSON.

#### Criterios de Evaluación:

1. **Correctitud del código:**
   
   - Las solicitudes HTTP se deben realizar correctamente para cada fecha.
   - El archivo JSON debe ser generado en el formato especificado.

2. **Manejo de errores:**
   
   - El código debe verificar que las solicitudes sean exitosas y manejar errores de forma adecuada.

3. **Formato del archivo JSON:**
   
   - El archivo debe seguir la estructura solicitada y contener todos los datos requeridos.
