# Taller 1 
## Descripción del dataset
El conjunto de datos Online Retail recoge información sobre transacciones de ventas realizadas entre diciembre de 2010 y diciembre de 2011, con un total de 541,909 registros. Las variables clave incluidas son:
 1. InvoiceNo: código de factura; los valores que comienzan con la letra 'C' indican cancelaciones.
 2. StockCode: código de producto de cinco dígitos.
 3. Quantity: cantidad de productos comprados; los valores negativos representan devoluciones.
 4. UnitPrice: precio unitario del producto, expresado en libras esterlinas (£).
 5. CustomerID: identificador único del cliente.
 6. Country: país desde el cual se realizó la compra.
  
## Análisis Exploratorio (EDA) - Dataset Online Retail

### 🔎 Resumen inicial
- **Registros totales:** 536,641
- **Registros duplicados:** 5,268 (0.98%)
- **Registros únicos para análisis:** 531,373 (99.02%)

### 🕰 Distribución temporal

- 2011: 494,660 (93.1%)
- 2010: 41,981  (6.9%)

-*Período cubierto: Diciembre 2010 - Diciembre 2011*

### 🌎 Distribución geográfica
**Países con transacciones:** 38  
**Top 5 mercados:**  

| País          | Transacciones |
|---------------|--------------:|
| United Kingdom| 490,300       |
| Germany       | 9,480         |
| France        | 8,541         |
| EIRE          | 8,184         |
| Spain         | 2,528         |

### ⚠️ Hallazgos 
#### Precios
- **Registros con UnitPrice = 0:** 2,510 
- **Registros con UnitPrice negativo:** 2
Puede ser debido a cancelaciones o errores del sistema

#### Cantidades
- **Transacciones con cantidad negativa:** 10,587
- **100% asociadas a cancelaciones** (InvoiceNo comienza con "C")

#### Descripciones
- **Descripciones con caracteres especiales:** 70 registros

Un análisis general del conjunto de datos:
![EDA](https://github.com/user-attachments/assets/6aaa8794-ca16-4e68-92cd-4039c98873f1)

## Meta-data
La combinación de StockCode y Description permite un análisis detallado del catálogo de productos, identificando no solo los artículos más vendidos (Quantity), sino también aquellos con descripciones ambiguas que podrían afectar la experiencia de compra. Al combinar Country con UnitPrice, se pueden detectar estrategias de precios diferenciados por mercado y su impacto en el volumen de ventas. La variable InvoiceNo, junto con InvoiceDate, posibilita el cálculo de la frecuencia de compra por cliente (CustomerID), permitiendo identificar patrones de recompra. 

### 📊 Campos del Dataset

| **Nombre**     | **Tipo**    | **Descripción**                                                                 |
|----------------|-------------|----------------------------------------------------------------------------------|
| `InvoiceNo`    | `string`    | Número de factura. Si comienza con `'C'` indica una cancelación.                |
| `StockCode`    | `string`    | Código único del producto.                                                      |
| `Description`  | `string`    | Descripción del producto comprado.                                              |
| `Quantity`     | `integer`   | Cantidad de unidades vendidas. Valores negativos indican devoluciones.          |
| `InvoiceDate`  | `datetime`  | Fecha y hora de la transacción. <br> Mínima: `2010-12-01 08:26:00` <br> Máxima: `2011-12-09 12:50:00` |
| `UnitPrice`    | `float`     | Precio por unidad del producto (en libras esterlinas).                          |
| `CustomerID`   | `integer`   | Identificador único del cliente.      |
| `Country`      | `string`    | País del cliente (38 países).                                                   |

## Visualizaciones
A continuación se presentan visualizaciones para mayor información.
Se observa una correlación prácticamente nula (≈ 0) entre la cantidad comprada (`Quantity`) y el precio unitario (`UnitPrice`), lo que indica que no existe una relación lineal significativa entre estas variables. Este hallazgo sugiere que:  
1. **El precio no depende** del volumen comprado (no hay descuentos por cantidad evidentes en los datos).  
2. **La cantidad adquirida** no está influenciada por el precio unitario.  
3. **No es posible predecir** una variable basándose en la otra mediante modelos lineales simples.  
Esta independencia entre variables resalta la necesidad de analizar otros factores como tipo de producto, temporada o perfil de cliente.


![Image](https://github.com/user-attachments/assets/e268ee95-d311-4603-9597-b98d5b054076)

El siguiente gráfico nos muestra que el mayor flujo de transacciones son realizadas en los últimos meses del año presentando un pico en Noviembre ya que la tonalidad de los colores nos muestra este resultado.
![Image](https://github.com/user-attachments/assets/4100f375-0d78-44e4-99c8-68038c4ebff6)

Y esta ultima figura nos demuestra que la mayor cantidad de transacciones viene del Reino unido con un total de 23494.
![Image](https://github.com/user-attachments/assets/f4af901c-f2a1-4c4a-bf28-cbac28f082e5)
