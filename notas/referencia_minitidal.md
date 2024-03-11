# Referencia sobre Minitidal

Es un subconjunto de TidalCycles.

*"Un lenguaje de codificación en vivo que permite crear patrones musicales con texto, describiendo secuencias y formas de transformarlas y combinarlas, explorando complejas interacciones entre partes sencillas."* (Estuary)

La documentación oficial de TidalCycles está disponible en https://tidalcycles.org/docs/ .

Minitidal actualmente soporta las siguiente funciones:

- `accelerate`
- `almostAlways`
- `almostNever`
- `always`
- `append`
- `arp`
- `arpeggiate`

- `bandf`
- `bandq`
- `begin`
- `brak`

- `cat`
- `choose`
- `chooseBy`
- `chop`
- `chunk`
- `chunk'`
- `coarse`
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

- `fastcat`
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
- `never`

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
- `slowcat`
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
