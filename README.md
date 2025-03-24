# 🔎 Hostname Generator & Analysis Tool

Este proyecto genera un conjunto ficticio de *hostnames* para servidores, simula sus atributos (sistema operativo, entorno, país), y crea visualizaciones estadísticas sobre su distribución.

---

## 📦 Requisitos

Instala las librerías necesarias ejecutando:

```bash
pip install pandas numpy matplotlib seaborn
```

## 🚀 ¿Qué hace este proyecto?

- Genera automáticamente hostnames con formato codificado.
- Extrae atributos (os, environment, country) a partir del hostname.
- Crea un DataFrame con todos los servidores simulados.
- Guarda los datos en un archivo CSV.
- Visualiza los datos con gráficos de barras, pastel, y más.

---

## 🧠 Estructura del hostname

Cada hostname tiene la siguiente estructura:

`<OS><ENV><COUNTRY><NODE_NUMBER>`

**Ejemplo:** `LPESP007`

**Significa:**
- **OS:** Linux
- **ENV:** Production
- **Country:** Spain
- **Node Number:** 007

---

## ⚙️ Funciones principales

1. `set_hostnames(n)`  
   Genera `n` hostnames aleatorios usando pesos predefinidos. Los resultados se almacenan globalmente en `dataset`.

2. `get_os(hostname)`  
   Devuelve el sistema operativo según la primera letra del hostname.

3. `get_environment(hostname)`  
   Devuelve el tipo de entorno según la segunda letra del hostname.

4. `get_country(hostname)`  
   Devuelve el país usando los caracteres 3-5 del hostname.

---

## 🧾 Flujo general del código

```python
set_dataframe(1500)     # Genera 1500 hostnames y crea un DataFrame
save_dataframe()        # Guarda el DataFrame como 'hosts.csv'
plot_environment_by_country()  # Visualización por país y entorno
plot_full_analysis()    # Panel completo con 4 gráficos
```

---

## 📊 Visualizaciones incluidas

1. `plot_environment_by_country()`  
   Gráfico de barras apiladas por país y tipo de entorno.

2. `plot_full_analysis()`  
   Matriz 2x2 con:
   - **Barras horizontales:** Sistemas operativos por país.
   - **Gráfico circular:** Porcentaje total de sistemas operativos.
   - **Barras horizontales (gradiente):** Total de hosts por país.
   - **Barras agrupadas:** Entornos por país.

---

## 🗂️ Estructura del archivo CSV

El archivo `hosts.csv` contiene las siguientes columnas:

| hostname   | os     | environment | country | node |
|------------|--------|-------------|---------|------|
| LPESP001   | Linux  | Production  | Spain   | 1    |
| SITAF002   | Solaris| Testing     | Italy   | 2    |
| ...        | ...    | ...         | ...     | ...  |

---

## 📌 Notas

- Se emplean probabilidades para simular una distribución realista.
- Variables globales utilizadas: `df`, `dataset`, `counter_dict`.
- Proyecto útil para prácticas de manipulación de datos, generación aleatoria y visualización con Python.
