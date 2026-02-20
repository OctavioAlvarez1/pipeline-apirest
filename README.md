# API Pipeline -- E-commerce Data

Pipeline de Data Engineering que consume datos desde una API REST de
e-commerce, aplica transformaciones y validaciones, y persiste los
resultados en formato Parquet particionado.

El proyecto simula un flujo ETL real:

Extract → Transform → Load

------------------------------------------------------------------------

## 🚀 Funcionalidad

El pipeline realiza:

✔ Consumo de API REST\
✔ Manejo de errores y reintentos (retry + backoff)\
✔ Transformaciones con Pandas\
✔ Validaciones de calidad de datos\
✔ Escritura en Parquet particionado\
✔ Logging estructurado

------------------------------------------------------------------------

## ⚙️ Setup

1.  Clonar el repositorio

``` bash
git clone https://github.com/tu_usuario/tu_repo.git
cd tu_repo
```

2.  Crear archivo `.env`

``` env
API_TOKEN=tu_token_aqui
API_BASE_URL=https://iansaura.com/api
```

API_BASE_URL es opcional (tiene valor por defecto).

3.  Instalar dependencias

``` bash
pip install -r requirements.txt
```

------------------------------------------------------------------------

## ▶️ Uso

Ejecutar el pipeline:

``` bash
python main.py
```

------------------------------------------------------------------------

## 🧩 Transformaciones aplicadas

El pipeline enriquece los datos de órdenes agregando:

-   Conversión de tipos (datetime, numeric)
-   Año de la orden (order_year)
-   Mes de la orden (order_month)
-   Día de la semana (day_of_week)
-   Flag de órdenes de alto valor (is_high_value)

También se validan valores inválidos en campos numéricos.

------------------------------------------------------------------------

## 💾 Output

Los datos se almacenan en el directorio output/:

output/ ├── orders/ │ ├── order_year=2024/ │ │ ├── order_month=2024-01/
│ │ ├── order_month=2024-02/ │ │ └── ... └── orders_all.parquet

✔ Dataset particionado (óptimo para engines analíticos)\
✔ Archivo consolidado

------------------------------------------------------------------------

## 🛠 Tecnologías utilizadas

-   Python\
-   Requests\
-   Pandas\
-   Parquet\
-   Logging\
-   dotenv

------------------------------------------------------------------------

## 📌 Características de Data Engineering

Este proyecto demuestra prácticas comunes en pipelines productivos:

✔ Idempotencia\
✔ Retry logic\
✔ Data validation\
✔ Schema handling\
✔ Partitioned storage\
✔ Observabilidad (logs)

------------------------------------------------------------------------

## 👤 Autor

Octavio Alvarez
