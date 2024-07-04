Aquí está, por fin. El código fuente de DOOM está disponible para tu
uso sin fines de lucro. Aún necesitas datos reales de DOOM para trabajar con este código.
Si en realidad no posees una copia real de uno de los DOOM, deberías
Todavía podrás encontrarlos en tiendas de software.

Muchas gracias a Bernd Kreimeier por tomarse el tiempo para limpiar el
proyecto y asegurarse de que realmente funcione. Los proyectos tienden a pudrirse si
lo dejas en paz durante unos años y requiere esfuerzo que alguien logre
tratarlo de nuevo.

La mala noticia: este código sólo se compila y se ejecuta en Linux. no pudimos
liberar el código DOS debido a una biblioteca de sonidos con derechos de autor que utilizamos
(Vaya, ¿fue un error? Ahora escribo mi propio código de sonido), y
Honestamente ni siquiera sé qué pasó con el puerto que hizo Microsoft.
a las ventanas.

Aún así, el código es bastante portátil y debería ser sencillo de utilizar.
póngalo en práctica en casi cualquier plataforma.

Escribí este código hace mucho, mucho tiempo y hay muchas cosas
que parecen completamente tontos en retrospectiva (usando coordenadas polares para
me viene a la mente un recorte), pero en general debería seguir siendo una base útil
para experimentar y seguir construyendo.

El concepto básico de renderizado: líneas horizontales y verticales de constante.
Z con sombreado de luz fijo por banda fue acertado, pero la implementación
podría mejorarse dramáticamente desde el código original si fuera
revisitado. La forma en que el renderizado procedió desde las paredes hasta los pisos para
los sprites podrían colapsarse en un solo recorrido de adelante hacia atrás del bsp
árbol para recopilar información, luego dibujar todo el contenido de un subsector
en el camino de regreso al árbol. Requiere tratamiento de suelos y techos.
como polígonos, en lugar de solo los espacios entre paredes, y requiere
recortar vallas publicitarias de sprites en fragmentos de subsector, pero sería
Lo correcto.

El movimiento y la línea de visión que se comparan con las líneas es uno de los
Errores más grandes que recuerdo. Es un código desordenado que tenía algunos
casos de falla, y había una solución mucho más simple (y más rápida)
sentado frente a mi cara. Usé el árbol BSP para renderizar cosas,
pero no me di cuenta en ese momento de que también podría usarse para
pruebas ambientales. Reemplazo de la prueba de línea de visión con una línea bsp
clip sería bastante fácil. Los amplios volúmenes para el movimiento se vuelven un poco
más difícil y aborda muchos de los desafíos que se enfrentan en terremoto/sismo2
con biseles de borde sobre poliedros.

Algunas ideas de proyectos:

Póngalo a su sistema operativo favorito.

Agregue algunas características de renderizado: transparencia, mirar hacia arriba/abajo, pendientes,
etc.

Agregue algunas características del juego: armas, saltar, agacharse, volar, etc.

Crea un juego de Internet basado en un servidor de paquetes.

Cree un juego de Internet basado en cliente/servidor.

Haz una versión acelerada en 3D. En hardware moderno (pentium rápido + 3DFX)
Probablemente ni siquiera necesitarías ser inteligente: podrías simplemente dibujar el
todo el nivel y obtener una velocidad razonable. Con un poco de esfuerzo, debería
bloquear fácilmente a 60 fps (bueno, hay algunos problemas con los 35 hz de DOOM)
base de tiempo...). El mayor problema probablemente sería la falta de poder de dos
tamaños de textura y las paredes compuestas de múltiples texturas.


No tengo una idea muy clara de cuántas personas habrá
jugar con esto, pero si se emprenden proyectos importantes, sería
Sería genial ver un nivel de cooperación comunitaria. Lo sé más temprano
Los proyectos van a ser trucos toscos hechos de forma aislada, pero estaría
muy contento de ver un lanzamiento neto coordinado de una versión mejorada y al revés
versión compatible de DOOM en múltiples plataformas el próximo año.

Divertirse.

Papota
23-12-97
