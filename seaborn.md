
Sí, exactamente igual que el famoso estilo _"10 minutes to pandas"_, Seaborn tiene su propia filosofía rápida basada en **tratar directamente con DataFrames**.

Aquí tienes la guía exprés condensada con lo esencial para dominar Seaborn en 10 minutos y sin rodeos.

### 1. El ritual de inicio y el superpoder de Seaborn

Seaborn dibuja por encima de Matplotlib, pero entiende los DataFrames a la perfección. Solo necesitas pasarle la tabla entera mediante el parámetro `data=...` y decirle qué columna va en la `x` y cuál en la `y`.

Python

```
import matplotlib.pyplot as plt
import seaborn as sns

# Activa el diseño estético moderno por defecto de Seaborn
sns.set_theme()

# Usaremos el dataset de ejemplo que viene integrado en Seaborn
df = sns.load_dataset("tips")
df.head()
```

### 2. Gráficos Relacionales (Para ver relaciones numéricas)

#### • `sns.scatterplot()`: Gráfico de dispersión

Python

```
sns.scatterplot(data=df, x="total_bill", y="tip", hue="smoker", size="size")
```

- **`hue`**: Pinta los puntos de colores diferentes según los valores de otra columna (¡clave para meter otra dimensión visual!).
    
- **`size`**: Cambia el tamaño de los puntos según una variable numérica.
    

#### • `sns.lineplot()`: Gráfico de líneas (ideal para series temporales)

Python

```
flights = sns.load_dataset("flights")
sns.lineplot(data=flights, x="year", y="passengers", hue="month")
```

### 3. Gráficos Categóricos (Para comparar grupos)

#### • `sns.barplot()` y `sns.countplot()`: Alturas y conteos

Python

```
# Muestra la media de una variable numérica por categoría (con barra de error)
sns.barplot(data=df, x="day", y="total_bill", hue="sex")

# Cuenta automáticamente cuántos elementos hay por categoría (como un .value_counts())
sns.countplot(data=df, x="day")
```

#### • `sns.boxplot()` y `sns.violinplot()`: Distribuciones estadísticas

Python

```
# Muestra la mediana, cuartiles y valores atípicos (outliers)
sns.boxplot(data=df, x="day", y="total_bill", hue="smoker")

# Hace lo mismo pero dibujando la forma de la densidad de probabilidad
sns.violinplot(data=df, x="day", y="total_bill")
```

### 4. Distribuciones (Para ver cómo se reparten los datos)

#### • `sns.histplot()`: El histograma definitivo

Python

```
# Histograma con una línea de densidad (KDE) superpuesta
sns.histplot(data=df, x="total_bill", kde=True, bins=20)
```

#### • `sns.pairplot()`: La matriz definitiva de gráficos cruzados

Si quieres cruzar **todas** las columnas numéricas de tu DataFrame de golpe para ver correlaciones en una sola instrucción:

Python

```
sns.pairplot(df, hue="sex")
```

### 5. Paneles múltiples (Grid / Facetas)

Aquí es donde Seaborn brilla con luz propia. Puedes replicar un gráfico en varios paneles dividiéndolo según una categoría usando `relplot`, `catplot` o `displot`:

Python

```
# Te crea una cuadrícula de gráficos de dispersión separados por columnas según el momento ('time')
sns.relplot(
    data=df,
    x="total_bill",
    y="tip",
    col="time",
    hue="smoker",
    kind="scatter",
)
```

### 6. Personalización rápida (El puente con Matplotlib)

Como Seaborn devuelve objetos de Matplotlib o se apoya en él, puedes usar los comandos de `plt` de toda la vida para tunear títulos y ejes al instante:

Python

```
plt.figure(figsize=(8, 5))
sns.boxplot(data=df, x="day", y="total_bill")

# Tunning extra con matplotlib
plt.title("Propina total por día de la semana", fontsize=14)
plt.xlabel("Día")
plt.ylabel("Factura Total ($)")
plt.show()
```