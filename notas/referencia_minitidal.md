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
- `contrast`
- `cosine`
- `crush`
- `cut`
- `cutoff`

- `degrade`
- `degradeBy`
- `delay`
- `delayfeedback`
- `delaytime`
- `density`

- `end`
- `every`

- `fastcat` Encadena una lista de patrones comprimiéndolos para que ocupen un ciclo.
- `fit`
- `fit'`
- `fix`

- `gain`
- `ghost`

- `hcutoff`
- `hresonance` Convierte un patrón numérico en un patrón de control que ajusta la resonancia de un filtro de paso alto. Acepta decimales entre 0 a 1.

- `id`
- `inside`
- `interlace`
- `inv`
- `irand`
- `iter`
- `iter'`

- `jux`
- `jux'`
- `jux4`
- `juxBy`
- `juxcut`
- `juxcut'`

- `layer`
- `lindenmayer`

- `n`
- `never` Aplica una función al patrón actual, en aproximadamente el 90% de las veces.

- `often`
- `outside`
- `overlay`

- `palindrome`
- `pan`
- `perlin2`
- `perlin2With`
- `perlinWith`
- `ply`

- `quantise`

- `rand`
- `randcat`
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
- `sine` Secuencia numérica con una onda sinusoidal.
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
