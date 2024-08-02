## Trabajo #4
[Arduino](https://github.com/Cristian171/Arduino)

# La Raspi berry pi pico
![raspberry pi pico](https://github.com/vera-perez-upb/sfi-estudiantes-202310-Cristian171/assets/72422960/240579e4-f81e-494d-a8d8-cc9fdf89d539)
- Cuando se cambia de 100 a 500 baja el tiempo de encendido del led


void setup() { ... }: Esta es la función de configuración inicial del programa. Se ejecuta una vez al inicio del programa.

pinMode(LED_BUILTIN, OUTPUT);: Configura el pin LED_BUILTIN como salida, lo que significa que se utilizará para enviar señales de salida.

void loop() { ... }: Esta es la función principal del bucle. Se ejecuta continuamente después de que la función setup() se haya ejecutado una vez.

static uint32_t previousTime = 0;: Declara una variable estática llamada previousTime que almacena el tiempo desde el último cambio de estado del LED en milisegundos. Se inicializa en 0.

static bool ledState = true;: Declara una variable estática llamada ledState que almacena el estado actual del LED, representado como true para encendido y false para apagado. Se inicializa en true.

uint32_t currentTime = millis();: Obtiene el tiempo actual en milisegundos desde que el programa comenzó a ejecutarse y lo almacena en la variable currentTime.

if( (currentTime - previousTime) > 100){ ... }: Comprueba si ha pasado más de 100 milisegundos desde el último cambio de estado del LED.

previousTime = currentTime;: Actualiza previousTime con el valor actual de currentTime para seguir registrando el tiempo del último cambio de estado.

ledState = !ledState;: Invierte el estado del LED. Si estaba encendido (true), lo apaga (false), y viceversa.

digitalWrite(LED_BUILTIN, ledState);: Establece el estado del pin LED_BUILTIN (el pin del LED integrado en la placa Arduino) según el estado del LED. Si ledState es true, el LED se encenderá; de lo contrario, se apagará.

En resumen, este programa hace que el LED integrado en la placa Arduino parpadee a intervalos regulares de aproximadamente 100 milisegundos.
