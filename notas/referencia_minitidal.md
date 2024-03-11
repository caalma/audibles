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
- `hresonance`

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
- `resonance`
- `rev`
- `run`

- `s` Versión breve de `sound`.
- `saw`
- `scale`
- `scan`
- `scramble`
- `selectF`
- `shape`
- `shuffle`
- `silence` Es el patrón vacio. Silencia (o se traga) todo lo que pase por él.
- `silent` Es un patrón que silencia. Similar a utilizar `(mask "~")`.
- `sine`
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
- `trunc`

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
