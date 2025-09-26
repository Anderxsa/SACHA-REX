## SACHA REX
Haz que sacha no rompa los edificios, consigue los mejores puntos y rompe el ranking.
## Link del Juego

https://anderxsa.github.io/SACHA-REX/
(Se debe jugar si o si en Pc o Laptop)
Instrucciones:
-Para saltar usa la tecla espacio

-Para volver a empezar dele click al texto "Perdiate Causa"

(un amigo mio llego a los 500 puntos)
## Explicacion de Creacion

Este juego usa ecuación cuadrática en la siguiente parte del código:

```js
// Fórmula
// y = y0 + v0*t - 0.5*g*t^2
//
// y0 → posición inicial (suelo)
// v0 → impulso o velocidad inicial
// g  → gravedad
// t  → tiempo transcurrido

````
Asi que lo adapte asi:

```js
var saltoTiempo = 0;
var saltoEnCurso = false;
var saltoInicioY = sueloY;
var saltoImpulso = impulso;
var saltoInicio = 0;

function Saltar(){
    if(dinoPosY === sueloY && !saltoEnCurso){
        saltando = true;
        saltoEnCurso = true;
        saltoTiempo = 0;
        saltoInicioY = sueloY;
        saltoImpulso = impulso;
        saltoInicio = performance.now() / 1000;
        dino.classList.remove("dino-corriendo");
    }
}

function MoverDinosaurio() {
    if(saltoEnCurso){
        saltoTiempo = (performance.now() / 1000) - saltoInicio;
        
        dinoPosY = saltoInicioY + saltoImpulso * saltoTiempo - 0.5 * gravedad * Math.pow(saltoTiempo, 2);
        if(dinoPosY <= sueloY){
            TocarSuelo();
            saltoEnCurso = false;
        }
    } else {
        dinoPosY = sueloY;
    }
    dino.style.bottom = dinoPosY+"px";
}


````
Cuando hice el primer borrador, iba usando la física como guía para calcular el salto, pero luego recordé que se podía resolver con una ecuación cuadrática. ASI que no me quedaba de otra y lo cambie 
# NOTA 
El bug solo está en la generación de edificios y en la adaptación a móvil. Intentaré arreglar pronto la generación de edificios pipipi Próximamente, el salto de Sacha tendrá una parábola más realista para mejorar la distancia 
att: Anderson V.
# POSTDATA
Profe no me salio el juego de angry birds y asi que me inspire con el dinosaurio de google que segun fuentes tambien usa ecuyacion cuadrantica, pero para que no sean iguales use texturas diferentes para marcar una diferencia y dar motivacion a seguir haciendolo conm la imagen chistosa del streamer conocido como sachauzumaki. iNTENTARE QUE SACHA LO PRUEBE

# ATENTAMENTE 
Anderson V. "4-H"
