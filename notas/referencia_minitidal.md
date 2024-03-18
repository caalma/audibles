# Referencia sobre Minitidal

Es un subconjunto de TidalCycles.

*"Un lenguaje de codificación en vivo que permite crear patrones musicales con texto, describiendo secuencias y formas de transformarlas y combinarlas, explorando complejas interacciones entre partes sencillas."* (Estuary)

La documentación oficial de TidalCycles está disponible en https://tidalcycles.org/docs/ .

Minitidal está disponible actualmente en Estuary https://estuary.mcmaster.ca

## Comentario sobre Comentarios

En Haskell, lenguaje base de TidalCycles los comentarios dentro del código se producen al anteponer a cualquier texto dentro de la línea '-- ' (dos guiones medio y un espacio). Por ejemplo:

- `-- Este texto no se ejecuta`
- `s "drum" -- Sonará algo de percusión.`

## Estructura y uso de patrones

    ##minitidal

    -- slow 4 $ s "bajo ~ bd tumba db ~ tink drum"
    -- slow 2 $ s "bd dr sn ht"
    -- slow 2 $ s "bd [dr cp] ht sn"
    -- slow 2 $ s "[cp bd] [ht dr sn]"
    -- slow 2 $ s "cp bd dr ht sn"
    -- slow 2 $ s "[cp bd] dr ht sn"
    -- slow 2 $ s "[cp bd] dr [ht sn]"
    -- slow 2 $ s "cp [bd dr] [ht sn]"
    -- slow 2 $ s "[cp [bd dr]] [ht sn]"
    -- slow 3 $ s "cp [bd dr]*2 ~ [ht sn]*3" -- con * se añaden n apariciones manteniendo el compas
    -- slow 0.4 $ s "cp [dr*2 ~]/2 bd/4" -- con / se distancias las apariciones cada n compases
    -- stack [ slow 0.5 $ s "bd/2" , slow 1 $ s "bajo",  slow 2 $ s "[tink*2]! ~*3" ]
    -- slow 3 $ s "bd!2 sn*2 dr" -- con ! se añaden n apariciones dividiendo el compas
    -- slow 0.5 $ s "[bajo, <drum tink tumba>]"
    -- slow 0.5 $ s "[bajo | <drum tink tumba>] dr?" -- con  | se elige aleatoriamente alguna de las opciones de la lista. con ? se condiciona la aparición aleatoriamente del evento
    -- stack [ s "[bd|dr]" , s "[sn|cp]" ]

## Efectos

    ##minitidal

    -- s "bajo!4 ~ bass*2" # vowel "<[a i]*2 [e i o]*2>"
    -- s "gtr*4 ~ bajo*6" # vowel "[p o p a] ~ [p a p p o p]"
    -- s "bajo!8 ~" # note "[0 4 7 2 <5 7> 9 4 [9 | 3] <11 1>] ~"
    -- s "bajo!6" # note "<0 1 3> <2 3 4> <4 5 6> <6 7 8> <8 9 10> <10 11 12>"
    -- s "bajo!6" # note "<0..11> <1..13> <2..14> <3..15> <4..16> <5..17>"
    -- s "bajo!6" # note "<-11..11>/6"
    -- stack [ fast 2 $ s "bajo"  # speed 2, hurry 2 $ s "gtr" ]

## Funciones soportadas en MiniTidal:

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

- `echo` ???
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
- `hurry` Dado un patrón numérico aplica en conjunto `fast` y `speed` con dicho valor.

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

- `often` Recibe una función y patrón, al cual le aplica dicha función el 75% de las veces de forma aleatoria.
- `outside` Toma el exterior de un patrón y lo introduce en el interior.
- `overlay` Encadena dos patrones, que preservan su duración original.

- `palindrome` Aplica `rev` a un patrón cada dos ciclos, de modo que el patrón alterna entre avance y retroceso.
- `pan` Convierte un patrón numérico (entre 0 a 1) en un patrón de control que especifíca el canal de audio. '0' corresponde al parlante izquierdo y '1' al derecho.
- `perlin` Emite ruido 1D suavizado. En cada ciclo se genera un nuevo valor aleatorio.
- `perlin2` Emite ruido 2D  permitiendo especificar un patrón personalizado como segunda dimensión. El número de ciclo permanece como primera dimensión.
- `perlin2With` Similar a `perlinWith` pero con 2 dimensiones.
- `perlinWith` Permite especificar un patrón como entrada para generar valores aleatorios en lugar de utilizar el recuento de ciclos predeterminado.
- `ply` Repíte cada evento una n cantidad de veces indicada.

- `quantise` Útil para redondear una colección de números a una fracción de base determinada. =VERIFICAR SI FUNCIONA=

- `rand` Emite un patrón continuo de valores pseudo-aleatorios comprendidos enter 0 y 1.
- `randcat` Similar a `cat` pero eligiendo aleatoriamente los elementos de la lista suministrada.
- `range` Recibe un patrón (entre 0 a 1), y lo escalará a un rango diferente - entre el primer y el segundo argumento.
- `rangex` versión exponencial de `range`
- `rarely` Recibe una función y patrón, al cual le aplica dicha función el 25% de las veces de forma aleatoria.
- `repeatCycles` Dada una lista de enteros y un patrón, repite este último según el entero actual.

- `resonance` Convierte un patrón numérico en un patrón de control que ajusta la resonancia de un filtro de paso bajo. Acepta decimales entre 0 a 1.
- `rev` Devuelve la versión invertida de un patrón.
- `run` Patrón de valores enteros entre 0 y n-1. `(run 4)` a `"0..3"`.

- `s` Versión breve de `sound`.
- `saw` Secuencia numérica con una onda lineal zigzag.
- `scale` Interpreta un patrón de números de notas en una escala con un nombre determinado. Las escalas disponibles son: `minPent majPent ritusen egyptian kumai hirajoshi iwato chinese indian pelog prometheus scriabin gong shang jiao zhi yu whole wholetone augmented augmented2 hexMajor7 hexDorian hexPhrygian hexSus hexMajor6 hexAeolian major ionian dorian phrygian lydian mixolydian aeolian minor locrian harmonicMinor harmonicMajor melodicMinor melodicMinorDesc melodicMajor bartok hindu todi purvi marva bhairav ahirbhairav superLocrian romanianMinor hungarianMinor neapolitanMinor enigmatic spanish leadingWhole lydianMinor neapolitanMajor locrianMajor diminished octatonic diminished2 octatonic2 messiaen1 messiaen2 messiaen3 messiaen4 messiaen5 messiaen6 messiaen7 chromatic bayati hijaz sikah rast saba iraq`.
- `scan` Patrón de valores enteros entre 1 y n. `(scan 4)` a `"1..5"`.
- `scramble` Recibe un número y un patrón. Divide el patrón en el número dado de partes y devuelve un nuevo patrón seleccionando aleatoriamente entre las partes.
- `selectF` Elige entre una lista de funciones, utilizando un patrón de decimales entre 0 a 1.
- `shape` Produce distorsión en forma de onda. Reciben un patrón de números desde 0 para ninguna distorsión hasta 1 para mucha distorsión. =VERIFICAR SI FUNCIONA=
- `shuffle` Toma un número y un patrón como entrada, divide el patrón en el número dado de partes, y devuelve un nuevo patrón como una permutación aleatoria de las partes, escogiendo una de cada por ciclo.
- `silence` Es el patrón vacio. Silencia (o se traga) todo lo que pase por él.
- `silent` Es un patrón que silencia. Similar a utilizar `(mask "~")`.
- `sine` Emine un patrón contínuo con valores de una función seno.
- `slow` Cambia la velocidad de un patrón.
- `slowcat` Encadena una lista de patrones, que preservan su duración original.
- `sometimes` Recibe una función y un patrón. Aplica la función al patrón el 50% de las veces.
- `sometimesBy` Recibe un patron de decimal entre 0 y 1, una función y un patrón. Aplica la función al patrón según del decimal suministrado.
- `sound` Selecciona el banco de sonido a utilizar.
- `sparsity` Recibe un decimal y un patrón, luego ralentiza el patrón según el valor suministrado.
- `speed` Dado un patrón numérico lo convierte a un patrón de control que establece la velocidad de reproducción de una muestra. 1 es velocidad normal, >1 más velocidad <1 menor velocidad, <0 invierte la muestra.
- `spread` Permite tomar una transformación de patrón que toma un parámetro, como lento, y proporcionar varios parámetros que se alternan entre sí. En otras palabras, "reparte" una función entre varios valores.
- `spreadr` o `spreadChoose` Similar a `spread` pero los valores se seleccionan al azar, un ciclo cada vez.
- `spreadf` Abreviatura de `spread ($)`
- `square` Una onda cuadrada que empieza en 0 y sube a 1 a mitad de ciclo.
- `stack` Toma una lista de patrones y los combina en un nuevo patrón superponiéndolos, reproduciendo simultáneamente todos los patrones de la lista.
- `step` Genera un patrón de cadenas con la sintaxis exacta que se desea para seleccionar muestras y que puede introducirse directamente en la función s.
- `step'` Similar a `step` pero más general, utilizando los números de la cadena de secuenciación por pasos como índices en la lista de cadenas que le des.
- `steps` Similar a `step` pero toma una lista de pares como haría `step` y los reproduce todos simultáneamente.
- `stitch` Recibe 3 patrones. Utiliza el primer patrón (binario) para cambiar entre los dos patrones siguientes. La estructura resultante proviene del patrón binario, no de los patrones fuente.
- `striate` Corta las muestras en trozos de forma similar a `chop`, pero los trozos resultantes se organizan de forma diferente.
- `striate'` o `striateBy` Similar a `striate` pero con un parámetro extra para definir la longitud de los trozos.
- `stripe` Repite un patrón a velocidades aleatorias. El primer parámetro indica el número de ciclos sobre los que se va a actuar. Cada ciclo se reproducirá a una velocidad aleatoria, pero de forma que la duración total sea la misma.
- `struct` Coloca una estructura rítmica "booleana" sobre el patrón que le has dado.
- `stut` Aplica un tipo de retardo a un patrón. Tiene tres parámetros, que podrían llamarse profundidad, realimentación y tiempo. Profundidad es un entero y los otros de coma flotante.
- `stutter` ??? Es como `stut` que no reduce el volumen o `ply` si controlas el tiempo. `stutter n t` repite cada evento en el patrón n veces, separadas por t tiempo (en fracciones de un ciclo).
- `swing` ??? Rompe cada ciclo en n trozos, y entonces retrasa los eventos en la segunda mitad de cada trozo por la cantidad x, que es relativa al tamaño del (medio) trozo. Así, si x es 0 no hace nada, 0.5 retrasa la mitad de la duración de la nota, y 1 volverá a no hacer nada.

- `timecat` o `timeCat`  Es como `fastcat` excepto en que se proporcionan tamaños proporcionales de los patrones entre sí para cuando se concatenan en un ciclo. Cuanto mayor sea el valor de la lista, mayor será el tamaño relativo del patrón en el bucle final.
- `toScale` Permite aplicar rápidamente una escala sin nombrarla.
- `tri` Una onda triangular, que empieza en 0, sube linealmente hasta 1 a mitad de ciclo y vuelve a bajar.
- `trigger` Alinea el inicio de un patrón con el tiempo en que se evalúa un patrón, en lugar de con la tiempo de inicio global. Debido a esto, es probable que el patrón no esté alineado con la rejilla de patrones.
- `trunc` Recorta un patrón según el porcentaje indicado.

- `unfix` Similar a `fix` pero sólo se aplica cuando el patrón de comprobación no coincide.

- `up` Dado un patrón numérico flotante y/o entero controla la densidad del sample hacia más agudo "n>0" o más grave "n<0".

- `vowel` Dado un patrón de texto, lo convierte a un patrón de control que crea un filtro de formantes para producir sonidos vocálicos en las muestras. Utilice los valores a, e, i, o y u para añadir el efecto.

- `wchoose` Similar a `choose`, pero le permite "ponderar" las opciones, de modo que algunas tengan más probabilidades de ser elegidas que otras.
- `wchooseBy` Como `wchoose` pero en lugar de seleccionar elementos de la lista aleatoriamente, utiliza el patrón dado para seleccionar elementos.
- `weave` Aplica un patrón de control a una lista de otros patrones de control, con un desfase temporal sucesivo.
- `weaveWith` Similar a `weave`, pero teje con una lista de funciones, en lugar de una lista de controles.
- `wedge` Combina dos patrones aplastándolos en un único ciclo. Toma un ratio como primer argumento. El ratio determina qué porcentaje del ciclo del patrón ocupa el primer patrón. El segundo patrón rellena el resto del ciclo del patrón.
- `whenmod` Similar a `every`, pero requiere un número adicional. Aplica la función al patrón, cuando el resto del número del bucle actual dividido por el primer parámetro, es mayor o igual que el número indicado.

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
- `palindrome $ n "[0..4]?" # s "cuerdas" # speed "0.22 0.1 0.4"`
- `s (steps [("tok","x  xx  xxx"),("tink", " xx xx ")])`
- `n (stitch "t*2 f  f ~ f ~" 1 2) # s "bd"`
- `n (toScale [0,2,4,5,7] "0 1 2 3 4 5 6 7") # s "notes"`
- `s "arpy*8" # up "-0.3 7 -4 2 -4*4 6"`
