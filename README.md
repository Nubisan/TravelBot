# TravelBot
Es un chatbot que va a permitir a los usuarios realizar consultas complejas en una sola frase en lugar de llenar múltiples formularios para una agencia de viajes.

# Extracción de información + Enriquecimiento IATA

Este proyecto implementa un asistente en Python que:
- Extrae información estructurada desde texto en español (origen, destino, fecha, cantidad, aerolínea).
- Genera un **JSON extraído** (salida intermedia) y un **JSON final**.
- En el JSON final, convierte ciudades a códigos **IATA** usando la API de Air-Port-Codes (con fallback local).
- Normaliza fechas al formato **dd-mm-yyyy** en el JSON final.

## Requisitos
- Python 3.10+ recomendado
- Librerías:
  - spacy
  - requests
  - python-dotenv (para leer la API Key desde `.env`)

## Instalación
## (Google Colab)
Ejecuta todas las celdas del notebook hasta cargar las funciones y podras empezar a interactuar con el chatbot.

## (Jupyter / Local)
En una terminal (o en una celda con ! si tu Jupyter lo permite):

```bash
pip install spacy requests python-dotenv
python -m spacy download es_core_news_sm
```

## Configuración de la API (recomendado con .env)

Crea un archivo llamado .env en la raíz del proyecto con:

APC_API_KEY=TU_API_KEY_AQUI
APC_API_SECRET=TU_API_SECRET_AQUI

Nota: No subas .env a GitHub. Agrega .env a tu .gitignore.

## Ejecución

1. Ejecuta/Importa todo el código (todas las celdas en Colab/Jupyter).

2. Llama a la función del chatbot:

asistente()

3. Escribe frases como:

- Comprar tres billetes para el 15-10 con Iberia de Quito a Madrid
- Quiero 2 billetes de Madrid a Frankfurt en Septiembre
- Billete barato AirEuropa de Madrid a Sevilla

Para salir:

- salir

Salidas

JSON Extraído: muestra lo detectado desde el texto.
JSON Final: incluye IATA y fecha normalizada a dd-mm-yyyy.