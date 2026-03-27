# ❎Cruce Dorado de Skewness

Este proyecto implementa una consulta SQL que detecta un cambio estructural temprano en la distribución de retornos, identificando activos cuya skewness pasa de negativa a positiva mientras el RSI permanece en zona de debilidad.

A diferencia de los cruces clásicos de medias móviles, esta señal busca capturar recuperaciones invisibles para los indicadores tradicionales de precio.

## 🧠Idea central

La mayoría de los traders espera:
 - que el precio suba
- que el RSI se recupere
- o que ocurra un cruce de medias

Este enfoque propone algo distinto:
- Cuando la forma de los retornos cambia antes que el precio, el mercado ya está mutando internamente.

Un cruce de skewness de negativo a positivo indica que:
- los retornos extremos negativos desaparecen
- comienzan a aparecer movimientos positivos asimétricos
- la presión vendedora se está agotando

## 📈Valor de negocio

- Detecta puntos de inflexión tempranos

- Señal útil para:
  - acumulación gradual
  - screening de activos infravalorados
  - estrategias contrarian de bajo drawdown
  - Complementa (no reemplaza) indicadores de precio

## 🗄️Estructura de datos esperada

- indicadores_tecnicos
- campo	descripción
- ticker_id	Identificador del activo
- fecha	Fecha del indicador
- skewness	Skewness de retornos
- rsi_14	RSI de 14 períodos
- tickers
- campo	descripción
- ticker_id	Identificador del activo

## ⚙️Lógica de la consulta

La query filtra activos que cumplen simultáneamente:
- Skewness actual mayor a 0
- Skewness previa menor a 0 (cruce)
- RSI de 14 períodos por debajo de 40

Esto asegura que:
- el mercado sigue débil en términos de momentum
- pero la distribución de retornos ya cambió de régimen

## 🔎 Interpretación de resultados

- Señal temprana: el mercado deja de castigar con retornos extremos
- El precio aún no confirma

Ideal para:
- watchlists
- entradas escalonadas
- confirmación con volumen o volatilidad

## 🚀Posibles extensiones

- Agregar filtro de volumen creciente
- Confirmar con volatilidad implícita
- Reemplazar subquery por LAG() si el motor lo permite
- Backtesting por régimen de mercado

## 📝Notas finales

- No es una señal de timing exacto
- Funciona mejor en activos líquidos
- Brilla cuando se combina con contexto macro o sectorial

## 👤Autora
Flavia Hepp Proyecto de SQL aplicó un análisis de riesgo basado en eventos.

***

📊 El precio todavía no sube… pero algo ya cambió.

Y no lo vas a ver en los indicadores tradicionales.

---

La mayoría mira cosas como:

* Cruces de medias móviles
* RSI saliendo de sobreventa

Pero hay una señal mucho más sutil:

👉 La **forma de los retornos**

---

🔍 Lo que analicé:

Casos donde:

* El **skewness pasa de negativo a positivo**
* Pero el **RSI sigue bajo (< 40)**

---

💡 ¿Por qué es interesante?

* El RSI todavía indica debilidad
* El precio todavía no confirma nada

Pero…

👉 la distribución de los retornos ya cambió

---

🧠 ¿Qué significa eso?

* Menos eventos extremos a la baja
* Mayor probabilidad de movimientos positivos
* El mercado empieza a “respirar distinto”

---

🔥 Insight clave:

Antes de que el precio suba…

👉 cambia la *estructura* del mercado

Y eso no lo capturan los indicadores clásicos.

---

🚀 Aplicaciones:

* Detectar recuperaciones tempranas
* Señales adelantadas de reversión
* Features para modelos cuantitativos
* Complemento a RSI y momentum

---

🧠 Takeaway:

Si solo mirás el precio… llegás tarde.

Pero si mirás la distribución de los retornos…

👉 podés ver el cambio antes de que ocurra.

---

Estoy explorando este tipo de insights combinando SQL + análisis cuantitativo.

Si te interesa este enfoque, conversemos 👇

#DataScience #Quant #Finance #Trading #MachineLearning #SQL #Investing
