# SnakeLoop
Juego Snake Loop

*Archivos Principales:
1.Snake.js: Contiene toda la lógica del juego, clases, entrada y bucle principal.

2.Index.html: Define el contenedor canvas y el evento de teclado. Carga el script y estructura la página.

*Como funciona el bucle

Se ejecuta la función main() cada X milisegundos además controla colisiones y se mueven la serpiente.

*Codigo Interesante

function dibujar () {
    var canvas = document.getElementById("workspace");
    var contexto = canvas.getContext("2d");
    contexto.clearRect(0, 0, canvas.width, canvas.height);
    // Aqui va todo el dbujo
    // contexto.fillRect(10, 10, 100, 100);
    cabeza.dibujar(contexto);
    comida.dibujar(contexto);}

Creo que esta es una de las partes interesantes del código, ya que es responsable de actualizar lo que verá el jugador en pantalla, es parte importante del código porque gracias a ella se comprende como se representa y actualiza el estado del juego.

Propuesta(reutilización):

*Descripción del concepto
Este proyecto es una version personalizada del clasico juego Snake. El jugador controla una serpiente que crece al comer comida mientras evita chocar con los bordes, su propio cuerpo y obstáculos. 

*Características:
Estilo retro con colores tipo arcoíris.

-Incremento progresivo de dificultad (velocidad y número de obstáculos).
-Manejo de colisiones: cuerpo, bordes, obstáculos.
-Interfaz personalizada (nombre del jugador en pantalla).
-Juego infinito hasta perder

*Componentes del juego reutilizadas ¿porque?

class objeto
Es una clase base reutilizada por Cola y Comida porque tiene la propiedad tamano y la función choque(), que calcula si un objeto ha colisionado con otro. Esto evita repetir código en cada clase y hace que sea fácil añadir nuevos objetos con colisión.

dibujar()
El método dibujar de cada clase se reutiliza dentro de la función principal dibujar() que se ejecuta en cada frame. Así se actualiza visualmente el estado del juego sin mezclar la lógica visual con la lógica del movimiento

*Modificaciones o nuevas adiciones 

1.Pantalla de instrucciones y nombre del jugador
Se agregó una pantalla emergente (popup) que explica las reglas antes de comenzar el juego.
Ademas el jugador puede ingresar su nombre y este se muestra en pantalla junto al puntaje.
/La intención es que a pesar de ser un juego aparentemente simple, se sienta personalizado con esta opción/

2. Sistema de obstáculos dinámicos
Los obstáculos ahora son más de uno, y aumentan en cantidad cada 50 puntos.
/Con esta modificación se busca brindar un juego interesante al avanzar para que el jugador quiera seguir o repetir el juego./

3.Aumento progresivo de velocidad cada 50 puntos
Como parte del reto el juego no solo aumenta en dificultad por los obstáculos sino que también por la velocidad de la serpiente

4.Triángulo como cabeza de la serpiente
La cabeza de la serpiente ahora tiene forma triangular y rota según la dirección, lo cual hace más clara la dirección del movimiento.
/Es una modificación que visualmente da mas claridad del juego al jugador, además el entorno de colores también se modifico colocando un fondo negro para dar contraste a los colores arcoíris de la serpiente/

5.Reset completo al perder
Se reinicia el puntaje, la velocidad, la posición, el número de obstáculos.
/El plus adicional es que a pesar de que reinicia todo, al final le muestra el puntaje al jugador para darle un feedback y lo invite a superarlo/
