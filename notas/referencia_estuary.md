# Referencia sobre Estuary

Acceso: https://estuary.mcmaster.ca/


## Composición de pantalla

Una columna:

	!localview $ grid 1 1 [ [code 1 0 []] ]

Dos filas:

	!localview $ grid 1 2 [ [code 1 0 []],[code 2 0 []] ]

Dos columnas:

	!localview $ grid 2 1 [ [code 1 0 []],[code 2 0 []] ]

Lista de vistas disponibles:

	!listviews

Muestra la configuración de la vista actual:

	!dumpview

Muestra el nombre de la vista actual:

	!activeview

Graba la vista actual con el nombre indicado:

	!publishview elegida

Carga la vista indicada:

	!presetview elegida


## Control de reloj interno y tempo

Cambia la velocidad de los ciclos por segundo. *Por ejemplo: 120 / 60 / 4 = 0.5*

	!setcps 0.5

Cambia la velocidad en beeps por minuto:

	!setbpm 60.0

Muestra la modalidad de tiempo/tempo actual:

	!showtempo


## Samples

Lista de samples disponibles:

	!localview audiomap


Importar bancos de samples:

	!reslist "http://page.xyz/samples.json"

## Canales de salida de audio

Máximo de canales disponibles en el navegador:
    !maxAudioOutputs

Cantidad de canales usados actualmente:

    !audioOutputs

Setear cantidad de canales:

    !setAudioOutputs [someNumber]
