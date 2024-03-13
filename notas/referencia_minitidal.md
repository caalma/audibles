# Referencia sobre Minitidal

Es un subconjunto de TidalCycles.

*"Un lenguaje de codificación en vivo que permite crear patrones musicales con texto, describiendo secuencias y formas de transformarlas y combinarlas, explorando complejas interacciones entre partes sencillas."* (Estuary)

La documentación oficial de TidalCycles está disponible en https://tidalcycles.org/docs/ .

Minitidal actualmente soporta las siguiente funciones:

- `accelerate` Cambia la velocidad de los samples. Acepta un patrón numérico. ¿funciona?
- `almostAlways` Aplica una función al patrón actual, en aproximadamente el 90% de las veces.
- `almostNever` Aplica una función al patrón actual, en aproximadamente el 10% de las veces.
- `always` Aplica una función al patrón actual, en aproximadamente el 100% de las veces.
- `append` Junta dos patrones diferentes alternando su ejecución.
- `arp` Arpegia el patrón de acordes según un patrón de modos suministrado. Los modos disponibles son: `up down updown downup up&down down&up converge diverge disconverge pinkyup pinkyupdown thumbup thumbupdown`
- `arpeggiate` Arpegia un acorder según un patrón numérico suministrado.

- `bandf` Convierte un patrón numérico en un patrón de control que establece la frecuencia central de un filtro pasa banda. En SuperDirt, esto es en Hz (prueba un rango entre 0 y 10000). En dirt clásico, es de 0 a 1.
- `bandq` o `bpq` Convierte un patrón numérico en un patrón de control que ajusta el factor q del filtro pasa banda. Los valores más altos (mayores que 1) estrechan el paso de banda.
- `begin` Saltea el principio de cada muestra, según un patrón numérico suministrado con valores entre 0 y 1.
- `brak` Hace que un patrón suene como un breakbeat. Para ello, cada dos ciclos, aplasta el patrón para que quepa medio ciclo y lo desfasa un cuarto de ciclo.

- `cat` Alias de `slowcat`
- `choose` Emite un patrón continuo, con los elementos de una lista dada, seleccionados aleatoriamente.
- `chooseBy` Similar a `choose` pero según una lista de ponderaciones suministrada.
- `chop` corta cada muestra en un número determinado de partes, lo que permite explorar una técnica conocida como "síntesis granular". Convierte un patrón de muestras en un patrón de partes de muestras.
- `chunk` Divide un patrón en un número determinado de partes y, a continuación, realiza un ciclo a través de esas partes sucesivamente, aplicando la función dada a cada parte sucesivamente (una parte por ciclo).
- `chunk'` Hace lo mismo que `chunk` pero recorre las partes en sentido inverso.
- `coarse` Convierte un patrón numérico en un patrón de control que reduce la frecuencia de muestreo de una muestra. Ej: 1 para el original, 2 para la mitad, 3 para un tercio y así sucesivamente.
- `contrast` Funciona como un `if-else`. Se le debe suministrar, en orden: la función para el caso `t`, la función para el caso `f`, y el patrón de control.
- `cosine` Emite un patrón continuo de valores según la onda coseno. Es similar a `(sine + 0.5)`
- `crush` Suministrado un patrón numérico, controla un efecto de aplastamiento de bit.
- `cut` Trunca un sample cuando se cumple la fracción de ciclo máxima especificada. Se le puede suministrar un patrón de eneteros.
- `cutoff` Según un patrón numérico suministrado, realiza un filtrado de paso bajo. En SuperDirt, esto es en Hz (prueba un rango entre 0 y 10000). En dirt clásico, es de 0 a 1.
- `degrade `Elimina aleatoriamente eventos de un patrón, el 50% de las veces.
- `degradeBy` Elimina aleatoriamente eventos de un patrón, según el valor suministrado (entre 0 y 1).
- `delay` Acepta un patrón numérico, que utiliza para marcar la fuerza de los ecos.
- `delayfeedback` Acepta un patrón numérico, que utiliza para especificar el retado de alimentación de el efecto indicado.
- `delaytime` Acepta un patrón numérico, que utiliza para cambiar la duración del efecto indicado.
- `density` Acelera la velocidad de un patrón.

- `end` Suministraod un patrón numérico de valores entre 0 y 1, controla el punto de finalización de los samples.
- `every` Permite aplicar una función segun una cantidad de ciclos suministrada.

- `fastcat` Encadena una lista de patrones comprimiéndolos para que ocupen un ciclo.
- `fit` Toma un patrón de números enteros, que se utilizan para seleccionar valores de la lista dada. Lo que lo hace un poco extraño es que sólo se selecciona un número determinado de valores en cada ciclo.

- `fit'` Es una generalización de fit, donde la lista se construye utilizando otro patrón entero para cortar un patrón dado. El primer argumento es el número de ciclos de este último patrón que se van a utilizar para el corte.
- `fix` Esta función aplica otra función a los eventos coincidentes en un patrón de controles. Es el `contrast` donde la función false-branching se establece en el `id` de identidad.

- `gain` Dado un patrón numérico controla el volumen. Funciona multiplicando el volumen del sample por el valor numérico.
- `ghost` Añade copias más silenciosas y desplazadas de tono de un evento después del evento, emulando las notas fantasma que son comunes en los patrones de percusión.

- `hcutoff` Según un patrón numérico suministrado, realiza un filtrado de paso alto. En SuperDirt, esto es en Hz (prueba un rango entre 0 y 10000). En dirt clásico, es de 0 a 1.
- `hresonance` Convierte un patrón numérico en un patrón de control que ajusta la resonancia de un filtro de paso alto. Acepta decimales entre 0 a 1.

- `id` ???
- `inside` Toma el interior de un patrón y lo expone al exterior.
- `interlace` ???
- `inv` ???
- `irand` Emite un patrón continuo de valores enteros pseudo-aleatorios. Se le debe suministrar un límite máximo, al que tiende el patrón.
- `iter` Divide un patrón en un número determinado de subdivisiones, reproduce las subdivisiones en orden, pero incrementa la subdivisión inicial en cada ciclo. El patrón vuelve a la primera subdivisión después de reproducir la última subdivisión.
- `iter'` Similar a `iter` pero en sentido inverso.

- `jux` Crea extraños efectos estéreo, aplicando una función a un patrón, pero sólo en el canal derecho.
- `jux'` ???
- `juxBy` Con `jux`, las versiones original y con efectos del patrón se panoramizan fuertemente a izquierda y derecha (es decir, se panoramizan a 0 y 1). Esto puede resultar excesivo, sobre todo si se escucha con auriculares. La variante juxBy tiene un parámetro adicional, que acerca el canal al centro.
- `juxcut` ???
- `juxcut'` ???

- `layer` Permite superponer varias funciones en un patrón
- `lindenmayer` Toma un número entero b, un conjunto de reglas del sistema Lindenmayer y una cadena inicial como entrada para generar una cadena de árbol del sistema L de b iteraciones. Puede utilizarse junto con una función de pasos para convertir la cadena generada en un patrón reproducible.

- `n` Dado un patrón numérico, lo convierte en un patrón de control para seleccionar un sonido del banco de sonidos utilizado.
- `never` Aplica una función al patrón actual, en aproximadamente el 90% de las veces.

- `often`
- `outside` Toma el exterior de un patrón y lo introduce en el interior.
- `overlay`

- `palindrome`
- `pan`
- `perlin` Emite ruido 1D suavizado. En cada ciclo se genera un nuevo valor aleatorio.
- `perlin2` Emite ruido 2D  permitiendo especificar un patrón personalizado como segunda dimensión. El número de ciclo permanece como primera dimensión.
- `perlin2With` Similar a `perlinWith` pero con 2 dimensiones.
- `perlinWith` Permite especificar un patrón como entrada para generar valores aleatorios en lugar de utilizar el recuento de ciclos predeterminado.
- `ply`

- `quantise`

- `rand` Emite un patrón continuo de valores pseudo-aleatorios comprendidos enter 0 y 1.
- `randcat` Similar a `cat` pero eligiendo aleatoriamente los elementos de la lista suministrada.
- `rangex`
- `rarely`
- `repeatCycles`
- `resonance` Convierte un patrón numérico en un patrón de control que ajusta la resonancia de un filtro de paso bajo. Acepta decimales entre 0 a 1.
- `rev` Devuelve la versión invertida de un patrón.
- `run` Patrón de valores enteros entre 0 y n-1. `(run 4)` a `"0..3"`.

- `s` Versión breve de `sound`.
- `saw` Secuencia numérica con una onda lineal zigzag.
- `scale`
- `scan`
- `scramble`
- `selectF`
- `shape`
- `shuffle`
- `silence` Es el patrón vacio. Silencia (o se traga) todo lo que pase por él.
- `silent` Es un patrón que silencia. Similar a utilizar `(mask "~")`.
- `sine` Emine un patrón contínuo con valores de una función seno.
- `slow`
- `slowcat` Encadena una lista de patrones, que preservan su duración original.
- `sometimes`
- `sometimesBy`
- `sound` Selecciona el banco de sonido a utilizar.
- `sparsity`
- `speed`
- `spreadChoose/spreadr`
- `spreadf`
- `square`
- `stack`
- `step`
- `step'`
- `steps`
- `stitch`
- `striate`
- `striate'`
- `striateBy`
- `stripe`
- `struct`
- `stut`
- `stutWith`
- `stutter`
- `swing`

- `timeCat/timecat`
- `toScale`
- `tri`
- `trigger`
- `trunc` Recorta un patrón según el porcentaje indicado.

- `unfix`
- `up`
- `ur`

- `vowel`

- `wchoose`
- `wchooseBy`
- `weave`
- `weaveWith`
- `wedge`
- `whenmod`


- `<>`
- `.`
- `#`
- `$`
- `|`
- `+|`



# Casos de usos

- `n "5*2 ~ 5" # s "hh27"`
- `n "10*8" # s "ab" # cutoff (sine * 20000)`
- `every 3 rev $ n "0..8" # s "future"`
- `every "3 2 5" rev $ n "0..8" # s "bass" # hresonance (perlin - 0.1) # resonance "0.8 0 <0.95 0.2>" `
- `slow "3 0.3" $ chunk' "2 3" (# speed "0.4 0.2") $ sound "gtr*<8 7 9>"`
- `contrast (# speed "<2 -1>") (rev)  (n "<2 3 5 7>") $ n "0..8" # s "bass"`
- `s "gtr(6,8)" # speed (sine * perlin + 0.5) # pan (cosine - rand)`
- `n "0..5(9, 12)" # s "bajo . tok" # speed (perlin * 0.8)`
- `s (density 6 "~ bajo gtr ~ bd") # cutoff 400`
- `s "gtr*16" # end 0.2 # begin 0.7 # speed (saw - sine * perlin) # cut 2 # gain 1`
- `degradeBy 0.2 $ juxBy 0.3 (# speed (2 * perlin)) $ sound "bass:1*9" # gain 0.8`
