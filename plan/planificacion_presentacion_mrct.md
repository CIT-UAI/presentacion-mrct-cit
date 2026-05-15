# Planificacion de presentacion MRCT

**Titulo tentativo:** Matriz de Resiliencia Climática Territorial: lectura integrada del cambio ecosistemico en Magallanes  
**Duracion objetivo:** 30 minutos  
**Audiencia:** equipo tecnico mixto, con foco en interpretacion y uso territorial  
**Estilo recomendado:** poco texto, una idea fuerte por lamina, mapas y diagramas como soporte principal.

## Objetivo de la presentacion

Explicar por que la Matriz de Resiliencia Climática Territorial (MRCT) es importante, como transforma datos satelitales en una lectura territorial integrada y como deben interpretarse sus resultados. La presentacion debe permitir responder preguntas tecnicas sin sobrecargar la exposicion principal con matematicas.

## Mensaje central

La MRCT no entrega solo un ranking de cuencas. Integra estado ecosistemico, trayectoria temporal, coherencia espacial y sensibilidad climatica para identificar donde el territorio muestra mayor presion de transicion y donde conviene mirar con mas detalle.

## Estructura general

| Bloque | Laminas | Tiempo | Funcion |
|---|---:|---:|---|
| Apertura y problema | 1-2 | 4 min | Instalar la necesidad de una lectura integrada. |
| Como se construye la MRCT | 3-10 | 21 min | Explicar el flujo metodologico con formulas de respaldo. |
| Como se interpretan los resultados | 11-12 | 4 min | Mostrar lectura territorial y resultados 2025. |
| Uso y cierre | 13 | 1 min | Dejar el mensaje principal y la utilidad operativa. |

Duracion total estimada: **30 minutos**.

## Guion por lamina

### 1. Apertura: el territorio cambia por varias senales a la vez

**Tiempo:** 2 min  
**Idea principal:** el cambio climatico no aparece como una sola variable, sino como una acumulacion de senales en vegetacion, agua, nieve, temperatura, humedad y estructura del paisaje.

**Texto en pantalla:**  
No basta mirar una senal aislada: necesitamos leer el sistema completo.

**Visual sugerido:**  
`../images/estrecho-de-magallanes.jpg` o `../images/mapa_magallanes.jpg`

**Nota para expositor:**  
Abrir con Magallanes como territorio extenso, remoto y ambientalmente contrastado. La pregunta no es solo "que cambio", sino si esos cambios estan empujando a las cuencas hacia otra condicion.

### 2. Que pregunta responde la MRCT

**Tiempo:** 2 min  
**Idea principal:** la matriz responde que tan cerca o lejos esta una cuenca de su regimen de referencia, como se mueve en el tiempo, si ese cambio es local o regional y que tan sensible es al clima.

**Texto en pantalla:**  
Estado, trayectoria, contexto y sensibilidad.

**Visual sugerido:**  
Diagrama simple de cuatro piezas: `D`, `V`, `D_local`, `SENS`.

**Nota para expositor:**  
Presentar la MRCT como un marco de lectura, no como una caja negra. Cada resultado final puede abrirse para entender que componente lo explica.

### 3. Flujo general de la matriz

**Tiempo:** 2 min  
**Idea principal:** la MRCT convierte mosaicos satelitales anuales en indicadores por cuenca, luego en un vector de estado, y finalmente en metricas de transicion y resiliencia.

**Texto en pantalla:**  
Datos satelitales -> indicadores -> estado -> trayectoria -> resiliencia.

**Visual sugerido:**  
Recrear como diagrama horizontal:

```text
Cuencas + Landsat -> Indicadores -> Vector de estado -> Dominio -> Trayectoria -> PT / RES
```

**Nota para expositor:**  
Esta lamina funciona como mapa de navegacion. No explicar todo todavia; solo anticipar que cada pieza tendra una interpretacion simple.

### 4. Unidad de analisis y base de datos

**Tiempo:** 2 min  
**Idea principal:** la unidad de lectura son cuencas hidrográficas observadas año a año entre 2013 y 2025.

**Texto en pantalla:**  
21.040 cuencas x 13 años = lectura territorial comparable.

**Visual sugerido:**  
`../images/metodologia/grilla_cuencas_huella_antropica.png` o `../images/cuenca_hidro.png`

**Datos clave para mencionar:**  
- 21.040 cuencas.
- Periodo 2013-2025.
- Linea base 2013-2022.
- Año de lectura principal: 2025.

**Nota para expositor:**  
Explicar que las cuencas permiten una lectura ambiental mas consistente que limites administrativos, aunque despues los resultados puedan agregarse por comuna.

### 5. Vector de estado ecosistemico

**Tiempo:** 2 min  
**Idea principal:** cada cuenca en cada año se transforma en un punto dentro de un espacio de indicadores ecosistemicos.

**Texto en pantalla:**  
Cada cuenca-año es un punto en el espacio de estados.

**Visual sugerido:**  
`../images/metodologia/series_indicadores_base.png`

**Formula de respaldo:**  

$$
\mathbf{T} \in \mathbb{R}^{N \times Y \times d}
$$

donde `N` es el numero de cuencas, `Y` el numero de años y `d` el numero de indicadores.

**Nota para expositor:**  
No listar todos los indicadores en pantalla. Mencionar familias: vegetacion, agua, nieve, humedad, estructura del paisaje, energia y aridez.

### 6. Linea base y distancia al dominio

**Tiempo:** 3 min  
**Idea principal:** la linea base define el comportamiento de referencia; la distancia `D` mide cuanto se aleja cada cuenca-año de ese regimen.

**Texto en pantalla:**  
`D` mide alejamiento respecto del regimen de referencia.

**Visual sugerido:**  
`../images/metodologia/distribucion_domain_series.png`

**Formula de respaldo:**  

$$
D(\mathbf{x}) =
\frac{
\sqrt{(\mathbf{x} - \boldsymbol{\mu})^\top \hat{\Sigma}^{-1}(\mathbf{x} - \boldsymbol{\mu})}
}{\sqrt{d}}
$$

**Interpretacion simple:**  
- `D` bajo: cuenca cercana a su referencia historica.
- `D` alto: cuenca mas alejada del regimen observado en la linea base.

**Nota para expositor:**  
Explicar la distancia como "que tan lejos esta el punto de la nube historica", considerando que las variables se mueven juntas.

### 7. Trayectoria temporal: no solo posicion, tambien movimiento

**Tiempo:** 3 min  
**Idea principal:** dos cuencas pueden tener la misma distancia actual, pero una puede estar recuperandose y otra alejandose rapidamente.

**Texto en pantalla:**  
La trayectoria distingue estabilidad, recuperacion y transicion activa.

**Visual sugerido:**  
`../images/metodologia/dinamica_temporal_domain.png`

**Formulas de respaldo:**  

$$
V_t = D_t - D_{t-1}
$$

$$
A_t = V_t - V_{t-1}
$$

$$
J_t = A_t - A_{t-1}
$$

**Interpretacion simple:**  
- `V` positiva: alejamiento.
- `V` negativa: retorno relativo.
- `A` muestra si el proceso se intensifica o se amortigua.
- `J` alerta cambios bruscos en la dinamica.

**Nota para expositor:**  
Usar un ejemplo verbal: una cuenca lejos pero volviendo no significa lo mismo que una cuenca cerca pero acelerando su alejamiento.

### 8. Contexto espacial: dominio global y dominio local

**Tiempo:** 3 min  
**Idea principal:** una señal puede ser parte de un patron regional o una anomalia local respecto de las cuencas vecinas.

**Texto en pantalla:**  
La misma distancia puede significar cosas distintas segun el entorno.

**Visual sugerido:**  
Diagrama de una cuenca central y sus 8 vecinas, o mapa de contraste local.

**Formula de respaldo:**  

$$
\bar{D}_{local,i,t} =
\sum_{j \in N_k(i)} \tilde{w}_{ij} D_{j,t}
$$

**Matriz de lectura:**  

| Dominio global | Dominio local | Lectura |
|---|---|---|
| Bajo | Bajo | Condicion cercana y coherente. |
| Alto | Bajo | Señal regional compartida. |
| Bajo | Alto | Anomalia local. |
| Alto | Alto | Caso prioritario de revision. |

**Nota para expositor:**  
El dominio local ayuda a evitar conclusiones apresuradas. Una cuenca critica rodeada de cuencas criticas sugiere un proceso extendido; una cuenca critica aislada pide revision focalizada.

### 9. Sensibilidad climatica

**Tiempo:** 2 min  
**Idea principal:** algunas cuencas reaccionan mas fuerte ante cambios en aridez, albedo y temperatura superficial.

**Texto en pantalla:**  
`SENS` mide reactividad relativa frente a presiones climaticas.

**Visual sugerido:**  
Diagrama: IA, ALB y TB -> modelo por cuenca -> `SENS`.

**Formulas de respaldo:**  

$$
D_{i,t} =
\beta_{0,i}
+ \beta_{\text{IA},i}\tilde{\text{IA}}_{i,t}
+ \beta_{\text{ALB},i}\tilde{\text{ALB}}_{i,t}
+ \beta_{\text{TB},i}\tilde{\text{TB}}_{i,t}
+ \varepsilon_{i,t}
$$

$$
SENS_i =
\frac{
\sqrt{
\beta_{\text{IA},i}^{2}
+ \beta_{\text{ALB},i}^{2}
+ \beta_{\text{TB},i}^{2}
}
}{
\sigma_{D,i} + 10^{-9}
}
$$

**Nota para expositor:**  
Enfatizar que sensibilidad alta no significa automaticamente peor estado. Significa que la cuenca responde mas ante variaciones climaticas observadas.

### 10. Sintesis: Potencial de Transicion y Resiliencia

**Tiempo:** 3 min  
**Idea principal:** el Potencial de Transicion combina distancia, movimiento, sensibilidad y contexto espacial; la resiliencia operativa es su transformacion inversa.

**Texto en pantalla:**  
Mayor `PT` implica menor resiliencia operativa.

**Visual sugerido:**  
`../images/resultados/mapa_res_pt_2025.png`

**Formula principal:**  

$$
PT_{i,t} =
D_{i,t}
\cdot
\left(1 + |V_{i,t}|\right)
\cdot
\left(1 + \alpha \cdot SENS_i\right)
\cdot
\left(1 + \beta_{local} \cdot D_{local,i,t}\right)
$$

$$
RES_{i,t} =
\frac{1}{1 + PT_{i,t}}
$$

**Interpretacion simple:**  
- `PT` alto: mayor propension de transicion.
- `RES` alta: menor presion de transicion.
- `RES` baja: mayor vulnerabilidad operativa dentro del marco MRCT.

**Nota para expositor:**  
Esta es la lamina mas importante de calculo. Conviene mostrar primero la logica visual de los factores y luego la formula como respaldo.

### 11. Como leer los resultados

**Tiempo:** 2 min  
**Idea principal:** el resultado final se interpreta combinando nivel de resiliencia y tipo de trayectoria.

**Texto en pantalla:**  
No todas las cuencas con baja resiliencia significan lo mismo.

**Visual sugerido:**  
`../images/resultados/distribucion_res_state_type.png`

**Contenido clave:**  
- `RES_STATE` resume nivel: alta resiliencia, media, baja o colapso potencial.
- `RES_TYPE` agrega direccion: estable, tensionada, recuperacion, degradacion activa o transicion.
- Una cuenca en baja resiliencia puede estar deteriorandose, recuperandose o mostrando una señal incompleta que requiere validacion.

**Nota para expositor:**  
Evitar decir "peores cuencas" como lectura unica. Usar "cuencas prioritarias para revision", porque la matriz ordena preguntas y evidencia.

### 12. Resultados 2025: lectura regional y comunal

**Tiempo:** 3 min  
**Idea principal:** Magallanes muestra una distribucion polarizada: hay cuencas de alta resiliencia y cuencas con presion de transicion muy alta.

**Texto en pantalla:**  
La señal regional es heterogenea y polarizada.

**Visuales sugeridos:**  
`../images/resultados/res_mediana_comunal_2025.png`  
`../images/resultados/sintesis_resultados_mrct_2025.png`

**Datos clave para mencionar:**  
- Mediana regional de `RES` 2025: 0,094.
- 43,7% de cuencas en alta resiliencia.
- 54,5% de cuencas en colapso potencial.
- Punta Arenas presenta mediana relativamente alta, pero fuerte heterogeneidad interna.

**Nota para expositor:**  
Usar los numeros como anclajes, no como el centro de la lamina. La conclusion importante es que el promedio no basta: se necesitan mapas, percentiles y tipologias.

### 13. Para que sirve la MRCT y cierre

**Tiempo:** 1 min  
**Idea principal:** la matriz permite priorizar donde mirar, que cuencas revisar y que hipotesis llevar a validacion territorial.

**Texto en pantalla:**  
La MRCT transforma datos en preguntas territoriales accionables.

**Visual sugerido:**  
`../images/resultados/punta_arenas_mapas_mrct_2025.png` o `../images/resultados/punta_arenas_series_prioritarias.png`

**Usos principales:**  
- Identificar cuencas prioritarias para revision.
- Separar procesos regionales de anomalias locales.
- Reconocer degradacion activa, recuperacion y transicion.
- Orientar trabajo de terreno y monitoreo.
- Transparentar que componentes explican cada resultado.

**Nota para expositor:**  
Cerrar con la idea de trazabilidad: cada caso prioritario puede abrirse en sus componentes `D`, `V`, `SENS` y `D_local`. La MRCT no reemplaza la validacion territorial, pero permite llegar a ella con mejor evidencia y mejores preguntas.

## Laminas de respaldo tecnico

Estas laminas no deberian entrar en la exposicion principal salvo que haya preguntas especificas.

### Respaldo A. Normalizacion robusta

$$
\tilde{x} =
\frac{x - \text{med}(x)}
{\text{MAD}(x) \times 1{,}4826}
$$

Uso: explicar por que las variables quedan en unidades comparables y por que el metodo reduce la influencia de valores extremos.

### Respaldo B. Covarianza Ledoit-Wolf

Uso: explicar que la distancia al dominio considera correlaciones entre variables y requiere una matriz estable. No entrar en derivacion matematica salvo pregunta tecnica.

### Respaldo C. Parametros del Potencial de Transicion

Valores por defecto:

$$
\alpha = 1{,}0
\qquad
\beta_{local} = 0{,}5
$$

Uso: explicar que estos pesos son decisiones de calibracion operativa y pueden evaluarse con analisis de sensibilidad.

### Respaldo D. Estados de resiliencia

| Condicion | Estado |
|---|---|
| `RES > 0,7` | Alta resiliencia |
| `0,4 < RES <= 0,7` | Resiliencia media |
| `0,2 < RES <= 0,4` | Resiliencia baja |
| `RES <= 0,2` | Colapso potencial |

Uso: aclarar que son categorias operativas, no diagnosticos ecologicos irreversibles.

## Recomendaciones de diseno

- Usar maximo 3 bullets cortos por lamina.
- Reservar las formulas para una franja inferior, una lamina partida o anexos tecnicos.
- Priorizar mapas, diagramas y series temporales por sobre tablas extensas.
- Evitar laminas con parrafos largos.
- En resultados, mostrar valores clave solo si ayudan a leer el mapa.
- Usar una codificacion visual consistente: estado, trayectoria, sensibilidad y resiliencia.
- Mantener las tablas grandes como material de respaldo, no como contenido principal.

## Imagenes recomendadas

| Uso | Archivo |
|---|---|
| Apertura territorial | `../images/estrecho-de-magallanes.jpg` |
| Mapa regional | `../images/mapa_magallanes.jpg` |
| Unidad territorial | `../images/cuenca_hidro.png` |
| Grilla y huella | `../images/metodologia/grilla_cuencas_huella_antropica.png` |
| Indicadores base | `../images/metodologia/series_indicadores_base.png` |
| Dominio y linea base | `../images/metodologia/distribucion_domain_series.png` |
| Trayectoria temporal | `../images/metodologia/dinamica_temporal_domain.png` |
| Mapa RES/PT | `../images/resultados/mapa_res_pt_2025.png` |
| Estados y tipos | `../images/resultados/distribucion_res_state_type.png` |
| Comparacion comunal | `../images/resultados/res_mediana_comunal_2025.png` |
| Drivers PT | `../images/resultados/drivers_pt_2025.png` |
| Punta Arenas | `../images/resultados/punta_arenas_mapas_mrct_2025.png` |
| Series prioritarias | `../images/resultados/punta_arenas_series_prioritarias.png` |
| Sintesis final | `../images/resultados/sintesis_resultados_mrct_2025.png` |

## Control de ritmo

| Lamina | Tiempo recomendado |
|---|---:|
| 1 | 2 min |
| 2 | 2 min |
| 3 | 2 min |
| 4 | 2 min |
| 5 | 2 min |
| 6 | 3 min |
| 7 | 3 min |
| 8 | 3 min |
| 9 | 2 min |
| 10 | 3 min |
| 11 | 2 min |
| 12 | 3 min |
| 13 | 1 min |
| **Total** | **30 min** |

Si el expositor necesita recuperar tiempo durante la charla, la lamina 9 puede resumirse en 1 minuto y dejar la ecuacion de `SENS` solo como respaldo oral.
