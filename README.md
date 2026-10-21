# GeneralTransit
Esta app integra dos temas de conducción de calor transitoria: Sólidos semiinfinitos y Sistemas multidimensionales. Cada sección se compone de INtroducción, Fórmulas, Recursos (simulador / calculadora, tabla). Aplicaciones. Ejemplos. Y al final hay una actividad general.
Documento HTML interactivo de una sola página que integra, en un solo recurso, los dos grandes temas de la conducción transitoria: sólidos semiinfinitos (Sección I) y sistemas multidimensionales (Sección II), con simuladores, calculadoras, ejemplos resueltos y una actividad final evaluada con verificación automática.

Este proyecto es un recurso educativo autocontenido (un único archivo HTML) diseñado para cursos de transferencia de calor. Combina la teoría, las ecuaciones, los datos tabulares y las herramientas de cálculo de la conducción transitoria en dos grandes secciones con estructura común:

Introducción → Ecuaciones → Tablas/Geometrías → Simulador o Calculadora → Ejemplos de aplicación

…y cierra con una actividad final de 5 retos con retroalimentación inmediata.
Características principales
Un solo archivo, sin build ni dependencias que instalar — basta con abrirlo en el navegador.
Fórmulas renderizadas con MathJax (ecuaciones diferenciales, erfc, Bi, Fo, productos).
Sección I · Semiinfinitos
Ecuación de conducción transitoria 1D y variable de semejanza 
η
=
x
/
4
α
t
η=x/ 
4αt
​
 .
Caso 1 (temperatura superficial constante) y Caso 2 (flujo de calor constante), con flujo en la frontera.
Tabla completa de 
e
r
f
c
(
η
)
erfc(η) generada dinámicamente (3 columnas, scroll fijo).
Simulador/Calculadora: sliders de tiempo, temperatura superficial 
T
s
T 
s
​
  y posición 
x
x; lecturas en vivo de 
T
(
x
)
T(x), 
η
(
x
)
η(x) y profundidad de penetración al 5 %, con marcador sobre la curva.
3 ejemplos resueltos (tuberías en invierno, bloque de madera, uso de la tabla) y 4 aplicaciones industriales.
Sección II · Multidimensionales
Teorema del producto formalizado (bloque 3D, cilindro corto 2D) + hipótesis de exactitud.
Tarjetas de geometrías con la fórmula de superposición de cada una.
Simulador comparativo 1D/2D/3D basado en la solución de un término (autovalores 
λ
1
λ 
1
​
  y coeficientes 
A
1
A 
1
​
  resueltos numéricamente, no curvas arbitrarias), con slider de 
h
h y nota pedagógica sobre la comparación de tasas.
Ejemplo mejorado del cilindro corto de aluminio: diagrama SVG de la intersección (pared × cilindro = cilindro corto), 5 pasos rigurosos (Bi, Fo, 
λ
1
λ 
1
​
 , 
A
1
A 
1
​
 , 
θ
θ, T), condición de validez verificada y calculadora interactiva que recalcula el problema con 
h
h, 
t
t y 
T
∞
T 
∞
​
  variables.
Actividad final
5 retos (2 semiinfinitos, 1 de penetración térmica, 1 de teorema del producto, 1 conceptual) con verificación automática con tolerancia, intentos, pistas y solución revelada tras 2 fallos.
Barra de progreso, marcación visual de aciertos y mensaje de actividad completada al 100 %.
3 retos extra opcionales de desarrollo en acordeones.
UX: navegación fija con menú móvil, anclas con scroll-padding, botón de volver arriba, diseño responsive, paleta de colores diferenciada por sección (naranja = Sección I, índigo = Sección II).
🗂 Estructura del documento
text

Portada
│
├── SECCIÓN I · Conducción transitoria en sólidos semiinfinitos
│   ├── 1–2. Introducción y conceptos (profundidad de penetración)
│   ├── 3. Ecuaciones · modelo matemático (Caso 1 erfc · Caso 2 flujo constante)
│   ├── 4. Tabla de la función de error complementaria
│   ├── 5. Simulador / Calculadora interactiva
│   ├── 6. Ejemplos de aplicación (3 resueltos)
│   └── 7. Aplicaciones industriales
│
├── SECCIÓN II · Conducción transitoria multidimensional
│   ├── 1. Introducción · el salto a las 3 dimensiones
│   ├── 2. Ecuaciones · Teorema del producto
│   ├── 3. Geometrías · intersecciones (barra, cilindro corto, bloque)
│   ├── 4. Simulador de enfriamiento comparativo (1D/2D/3D)
│   └── 5. Ejemplo mejorado + calculadora (cilindro corto de aluminio)
│
├── ACTIVIDAD FINAL · 5 retos con verificación + retos extra
│
└── Footer · bibliografía
🎮 Contenido interactivo
Componente	Ubicación	Qué permite hacer
Simulador de perfil 
T
(
x
,
t
)
T(x,t)	Sección I · §5	Variar 
t
t (1–180 min), 
T
s
T 
s
​
  (40–400 °C) y 
x
x (0.5–20 cm); ver curva, 
η
η, 
T
(
x
)
T(x) y 
δ
5
%
δ 
5%
​
 
Tabla erfc	Sección I · §4	Consulta rápida de 
e
r
f
c
(
η
)
erfc(η) para resolver a mano
Simulador 1D/2D/3D	Sección II · §4	Variar 
h
h (10–400 W/m²·K) y comparar 
θ
(
t
)
θ(t) de pared, cilindro corto y bloque
Calculadora del ejemplo	Sección II · §5	Recalcular Bi, Fo, 
θ
p
a
r
e
d
θ 
pared
​
 , 
θ
c
i
l
θ 
cil
​
 , 
θ
t
o
t
a
l
θ 
total
​
  y 
T
c
e
n
t
r
o
T 
centro
​
  con 
h
h, 
t
t, 
T
∞
T 
∞
​
  libres; advierte si 
F
o
<
0.2
Fo<0.2
Actividad final	Cierre · 5 retos	Respuestas numéricas con tolerancia ±0.4–0.6, opción múltiple, pistas, soluciones y progreso
🛠 Tecnologías utilizadas
Tecnología	Uso
HTML5 / JavaScript vanilla	Estructura y lógica (sin frameworks ni paso de compilación)
Tailwind CSS (CDN)	Diseño responsive y utilidades visuales
Chart.js (CDN)	Gráficas interactivas de ambos simuladores
MathJax 3 (CDN)	Renderizado de notación matemática LaTeX
Font Awesome (CDN)	Iconografía
A&S 7.1.26	Evaluación numérica de erfc (error < 1.5×10⁻⁷)
Bisección + series de Bessel	Autovalores 
λ
1
λ 
1
​
  y coeficientes 
A
1
A 
1
​
  de pared y cilindro
🚀 Uso y despliegue
Opción 1 — Abrir directamente (más fácil)
Descargue 
conduccion_transitoria_general.html
.
Ábralo con doble clic en cualquier navegador moderno.
⚠️ Requiere conexión a internet la primera vez (CDNs de Tailwind, Chart.js, MathJax y Font Awesome). Si necesita uso 100 % offline, descargue esos cuatro archivos y sustituya las etiquetas <script src=...> / <link href=...> por rutas locales.

Opción 2 — Servidor local
Bash

git clone https://github.com/<TU-USUARIO>/<TU-REPO>.git
cd <TU-REPO>
python3 -m http.server 8000
# abrir http://localhost:8000/conduccion_transitoria_general.html
Opción 3 — GitHub Pages (despliegue público)
Suba el archivo al repositorio.
Opcional pero recomendado: renómbrelo (o cúpelo) como index.html para que se sirva en la raíz.
En GitHub: Settings → Pages → Deploy from a branch → main / root → Save.
En unos minutos estará en https://<TU-USUARIO>.github.io/<TU-REPO>/.
📁 Estructura del repositorio
text

.
├── README.md                            # Este archivo
└── conduccion_transitoria_general.html  # Aplicación completa (autocontenida)
✅ Verificación numérica
Los motores de cálculo del documento fueron contrastados con los valores tabulados:

Prueba	Esperado	Obtenido
e
r
f
c
(
0.50
)
erfc(0.50) (tabla)	0.4795	0.4795 ✔
e
r
f
c
(
1.00
)
erfc(1.00) (tabla)	0.1573	0.1573 ✔
Ejemplo cilindro corto (Al): 
λ
1
,
A
1
λ 
1
​
 ,A 
1
​
  pared	0.1584, 1.0042	✔
Ejemplo cilindro corto: 
T
c
e
n
t
r
o
T 
centro
​
 	≈ 69.8 °C	69.8 °C ✔
Reto 1 (erfc, Ts constante)	≈ 43.5 °C	43.5 °C ✔
Reto 2 (flujo constante)	≈ 44.4 °C	44.4 °C ✔
Reto 3 (penetración 5 %)	≈ 18.2 cm	18.2 cm ✔
Reto 4 (producto 3D)	78.8 °C	78.8 °C ✔
🌐 Requisitos del navegador
Navegadores modernos (Chrome/Edge ≥ 90, Firefox ≥ 88, Safari ≥ 14).
JavaScript habilitado y conexión a internet para los CDN.
Resolución recomendada: ≥ 1024 px de ancho (diseño responsive desde 360 px).
📚 Bibliografía
Cengel, Y. A. (2007). Transferencia de calor y masa: un enfoque práctico. McGraw-Hill. — Cap. 4: conducción transitoria (semiinfinitos y sistemas multidimensionales).
Fernández Díez, P. Ingeniería Térmica. Universidad de Cantabria.
Abramowitz, M. & Stegun, I. A. (1964). Handbook of Mathematical Functions — fórmula 7.1.26 para 
e
r
f
c
(
x
)
erfc(x).
📄 Licencia
Este proyecto se distribuye bajo la licencia MIT (véase el archivo 

LICENSE
). Puede adaptarse libremente con fines educativos citando la autoría original.

© 2026 Universidad de América — Cátedra de Termodinámica.
