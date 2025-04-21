1- Análisis de facturación
# Facturación total por tienda (sin columna de cantidad)
for i, tienda_df in enumerate([tienda, tienda2, tienda3, tienda4], start=1):
    facturacion_total = tienda_df['Precio'].sum()
    print(f"Facturación total Tienda {i}: ${facturacion_total:,.2f}")

    #Resultado arojado
Facturación total Tienda 1: $1,150,880,400.00
Facturación total Tienda 2: $1,116,343,500.00
Facturación total Tienda 3: $1,098,019,600.00
Facturación total Tienda 4: $1,038,375,700.00

2- Ventas por categoría

import matplotlib.pyplot as plt

# Función para graficar ventas por categoría
def ventas_por_categoria(df, tienda_nombre):
    categorias = df['Categoría del Producto'].value_counts()
    categorias.plot(kind='bar', figsize=(8,5), title=f"Ventas por categoría - {tienda_nombre}", color='skyblue')
    plt.xlabel("Categoría")
    plt.ylabel("Cantidad de ventas")
    plt.xticks(rotation=45)
    plt.grid(axis='y')
    plt.tight_layout()
    plt.show()

# Graficar para las 4 tiendas
ventas_por_categoria(tienda, "Tienda 1")
ventas_por_categoria(tienda2, "Tienda 2")
ventas_por_categoria(tienda3, "Tienda 3")
ventas_por_categoria(tienda4, "Tienda 4")

3- Calificación promedio de la tienda

# Calificación promedio por tienda
for i, df in enumerate([tienda, tienda2, tienda3, tienda4], start=1):
    promedio = df['Calificación'].mean()
    print(f"Calificación promedio Tienda {i}: {promedio:.2f} ⭐")

#Resultado arojado
Calificación promedio Tienda 1: 3.98 ⭐
Calificación promedio Tienda 2: 4.04 ⭐
Calificación promedio Tienda 3: 4.05 ⭐
Calificación promedio Tienda 4: 4.00 ⭐

4- Producto más y menos vendidos
# Función para mostrar top y bottom productos
def productos_populares(df, tienda_nombre, top=5):
    print(f"\n{tienda_nombre}")
    print("🔝 Productos más vendidos:")
    print(df['Producto'].value_counts().head(top))

    print("\n🔻 Productos menos vendidos:")
    print(df['Producto'].value_counts().tail(top))

# Aplicar a cada tienda
productos_populares(tienda, "Tienda 1")
productos_populares(tienda2, "Tienda 2")
productos_populares(tienda3, "Tienda 3")
productos_populares(tienda4, "Tienda 4")

 #Resultado arojado
Tienda 1
🔝 Productos más vendidos:
Producto
Microondas          60
TV LED UHD 4K       60
Armario             60
Secadora de ropa    58
Mesa de noche       56
Name: count, dtype: int64

🔻 Productos menos vendidos:
Producto
Ciencia de datos con Python    39
Pandereta                      36
Olla de presión                35
Auriculares con micrófono      33
Celular ABXY                   33
Name: count, dtype: int64

Tienda 2
🔝 Productos más vendidos:
Producto
Iniciando en programación    65
Microondas                   62
Batería                      61
Guitarra acústica            58
Pandereta                    58
Name: count, dtype: int64

🔻 Productos menos vendidos:
Producto
Auriculares        37
Sillón             35
Mesa de comedor    34
Impresora          34
Juego de mesa      32
Name: count, dtype: int64

Tienda 3
🔝 Productos más vendidos:
Producto
Kit de bancas      57
Mesa de comedor    56
Cama king          56
Set de ollas       55
Mesa de noche      55
Name: count, dtype: int64

🔻 Productos menos vendidos:
Producto
Guitarra eléctrica         38
Set de vasos               36
Mochila                    36
Microondas                 36
Bloques de construcción    35
Name: count, dtype: int64

Tienda 4
🔝 Productos más vendidos:
Producto
Cama box                     62
Cubertería                   59
Dashboards con Power BI      56
Cama king                    56
Carrito de control remoto    55
Name: count, dtype: int64

🔻 Productos menos vendidos:
Producto
Refrigerador                   38
Ciencia de datos con Python    38
Guitarra acústica              37
Armario                        34
Guitarra eléctrica             33
Name: count, dtype: int64

5- Envío promedio por tienda
# Envío promedio por tienda
for i, df in enumerate([tienda, tienda2, tienda3, tienda4], start=1):
    envio_promedio = df['Costo de envío'].mean()
    print(f"Costo de envío promedio Tienda {i}: ${envio_promedio:.2f}")

#Resultado arojado
Costo de envío promedio Tienda 1: $26018.61
Costo de envío promedio Tienda 2: $25216.24
Costo de envío promedio Tienda 3: $24805.68
Costo de envío promedio Tienda 4: $23459.46


Resumen

Después de analizar las métricas clave de las 4 tiendas de Alura Store, se presentan las siguientes conclusiones:

Facturación total: Las tiendas con mayor facturación muestran un mayor volumen de ventas, lo cual indica buena demanda. La tienda con menor facturación puede tener problemas de ventas o productos poco atractivos. Tienda 1:  1,150,880,400.00Tienda2: 1,116,343,500.00 Tienda 3  1,098,019,600.00Tienda4: 1,038,375,700.00

Ventas por categoría: Algunas tiendas se enfocan en categorías más demandadas, mientras que otras muestran poca variedad o categorías de menor movimiento. Esto puede influir directamente en su facturación. Tienda 1: Segunda mejor venta Tienda 2: Mejor venta Tienda 3: Cuarta mejor venta Tienda 4: Tercera mejor venta

Calificación promedio: La calificación promedio es un fuerte indicador de satisfacción del cliente. Una tienda con una calificación baja podría tener problemas con atención, entrega o calidad del producto.

Tienda 1: Cuarto mejor puntaje 3.98

Tienda 2: Segundo mejor puntaje 4.04

Tienda 3: El mejor promedio 4.05

Tienda 4: Tercer mejor puntaje 4.00

Productos más y menos vendidos: Identificar productos poco vendidos puede revelar exceso de stock o productos no deseados por el público. Las tiendas con muchos productos poco vendidos tienen bajo rendimiento.

Tienda 1: 294 – 176 = 118 Tienda 2: 304 – 172 = 132 Tienda 3: 279 – 181 = 98 Tienda 4: 288 – 180 = 108

Costo de envío promedio: Una tienda con alto costo de envío puede desincentivar las compras y reducir la satisfacción del cliente. Esto también afecta los márgenes de ganancia.
Tienda 1:  26018.6111.Tienda2: 25216.24
Tienda 3:  24805.6813.Tienda4: 23459.46
🧾 Recomendación Con base en los datos analizados, se recomienda que el Sr. Juan considere vender la Tienda 4, ya que: • Tiene la facturación más baja. Es la tienda que tiene la facturación más baja • Posee menores ventas por categoría. Quedó en tercer lugar de ventas por categoría • Su calificación promedio está: Su calificación quedó en el tercer lugar

Si analizamos está tienda queda siempre en el tercer lugar en la mayoría de los puntos a evaluar los que nos arroja que es la que está en peor posición.

Vender esta tienda permitiría al Sr. Juan enfocar sus esfuerzos y recursos en tiendas más rentables y eficientes, y así tener una base más sólida para su nuevo emprendimiento.

    
