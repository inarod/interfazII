# interfazII
### ejercicio n1 Arduino "hola mundo hola raimundo"

```js
void setup() {
  Serial.begin(9600); // Inicia la comunicación serie a 9600 bps
  Serial.println("Hola, raiMundo!"); // Envía "Hola, Mundo!" al monitor serie
}

void loop() {
  // No es necesario poner nada en el loop para este ejemplo
}
```




### ej n°3 Luz parpadeante 


```void setup() {  // Configuración inicial (ej: pines como entrada/salida)
  pinMode(13, OUTPUT);  // Pin 13 como salida
  pinMode(8, OUTPUT);  // Pin 8 como salida
}



void loop() {   // Se repite infinitamente
  digitalWrite(13, HIGH);  // Encender LED
  delay(1000);             // Esperar 1 segundo
  digitalWrite(13, LOW);   // Apagar LED
  delay(1000);             // Esperar 1 segundo
   digitalWrite(8, HIGH);  // Encender LED
  delay(1000);             // Esperar 1 segundo
  digitalWrite(8, LOW);   // Apagar LED
  delay(1000);             // Esperar 1 segundo
}
```
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/blinker.png"/>


### Ej n°4 Led con pulsador


```void setup() {
  pinMode(2, INPUT);  // Botón como entrada
  pinMode(13, OUTPUT);
}
void loop() {
  if (digitalRead(2) == HIGH) {  // Si se presiona el botón
    digitalWrite(13, HIGH);
  } else {
    digitalWrite(13, LOW);
  }
}
```
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/pulsador.png"/> 




###  Ej n°5 Led con potenciador

```
void setup() {
  pinMode(9, OUTPUT);  // Pin PWM (símbolo ~)
}
void loop() {
  int valor = analogRead(A0);           // Leer potenciómetro (0-1023)
  int brillo = map(valor, 0, 1023, 0, 255);  // Convertir a rango PWM
  analogWrite(9, brillo);               // Ajustar brillo
}

```
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/potenciador.png"/>






### ejercicio n2 2.0 semaforo arduino


```js
// C++ code - Semáforo Autos y Peatones

// Definición de pines
int LED_1 = 6;  // Luz roja autos
int LED_2 = 7;  // Luz amarilla autos
int LED_3 = 8;  // Luz verde autos
int LED_4 = 9;  // Luz verde peatones
int LED_5 = 10; // Luz roja peatones

void setup() {
  // Configuramos todos los pines como salida
  pinMode(LED_1, OUTPUT);
  pinMode(LED_2, OUTPUT);
  pinMode(LED_3, OUTPUT);
  pinMode(LED_4, OUTPUT);
  pinMode(LED_5, OUTPUT);
}

void loop() {
  // 🚦 Fase 1: Autos en verde, peatones en rojo
  digitalWrite(LED_1, LOW);   // Rojo autos apagado
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado
  digitalWrite(LED_3, HIGH);  // Verde autos encendido
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  delay(5000); // 5 segundos

  // 🚦 Fase 2: Amarillo autos, peatones siguen en rojo
  digitalWrite(LED_3, LOW);   // Verde autos apagado
  digitalWrite(LED_2, HIGH);  // Amarillo autos encendido
  delay(2000); // 2 segundos
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado

  // 🚦 Fase 3: Rojo autos, verde peatones
  digitalWrite(LED_1, HIGH);  // Rojo autos encendido
  digitalWrite(LED_5, LOW);   // Rojo peatones apagado
  digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(5000); // 5 segundos

  // 🚦 Fase 4: Rojo autos, rojo peatones (tiempo intermedio)
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  delay(2000); // 2 segundos
}
```
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/semaforo.png"/>





### ejercicio n2 3.0 semaforo arduino
```
// C++ code - Semáforo Autos y Peatones

// Definición de pines
int LED_1 = 6;  // Luz roja autos
int LED_2 = 7;  // Luz amarilla autos
int LED_3 = 8;  // Luz verde autos
int LED_4 = 9;  // Luz verde peatones
int LED_5 = 10; // Luz roja peatones

void setup() {
  // Configuramos todos los pines como salida
  pinMode(LED_1, OUTPUT);
  pinMode(LED_2, OUTPUT);
  pinMode(LED_3, OUTPUT);
  pinMode(LED_4, OUTPUT);
  pinMode(LED_5, OUTPUT);
}

void loop() {
  // 🚦 Fase 1: Autos en verde, peatones en rojo
  digitalWrite(LED_1, LOW);   // Rojo autos apagado
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado
  digitalWrite(LED_3, HIGH);  // Verde autos encendido
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
  delay(5000); // 5 segundos

  // 🚦 Fase 2: Amarillo autos, peatones siguen en rojo
  digitalWrite(LED_3, LOW);   // Verde autos apagado
  digitalWrite(LED_2, HIGH);  // Amarillo autos encendido
  delay(2000); // 2 segundos
  digitalWrite(LED_2, LOW);   // Amarillo autos apagado

  // 🚦 Fase 3: Rojo autos, verde peatones
  digitalWrite(LED_1, HIGH);  // Rojo autos encendido
  digitalWrite(LED_5, LOW);   // Rojo peatones apagado
  digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(3000); // 3 segundos
 digitalWrite(LED_4, LOW);  // Verde peatones apagado
 delay(250); // 0,25 segundos
   digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(250); // 0,25 s
 digitalWrite(LED_4, LOW);  // Verde peatones apagado
 delay(250); // 0,25 segundos
   digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(250); // 0,25 segundos
 digitalWrite(LED_4, LOW);  // Verde peatones apagado
 delay(250); // 0,25 segundos
   digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(250); // 0,25 segundos
 digitalWrite(LED_4, LOW);  // Verde peatones apagado
 delay(250); // 0,25 segundos
   digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(250); // 0,25 segundos
 digitalWrite(LED_4, LOW);  // Verde peatonenes apagado
 delay(250); // 0,25 segundos
   digitalWrite(LED_4, HIGH);  // Verde peatones encendido
  delay(250); // 0,25 segundos
  // 🚦 Fase 4: Rojo autos, rojo peatones (tiempo intermedio)
  digitalWrite(LED_4, LOW);   // Verde peatones apagado
  digitalWrite(LED_5, HIGH);  // Rojo peatones encendido
 // 2 segundos
}
``` 

### ej n°6 elipses en processing
```
import processing.serial.*;

Serial myPort;  // Crear objeto de la clase Serial
static String val;    // Datos recibidos desde el puerto serial
int sensorVal = 0;

void setup()
{
  background(228, 204, 214, 1); 
  //fullScreen(P3D);
   size(1080, 720);
   noStroke();
  noFill();
  String portName = "COM3";// Cambia el número (en este caso) para que coincida con el puerto correspondiente conectado a tu Arduino. 

  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort = new Serial(this, Serial.list()[0], 9600);

}

void draw()
{
  if ( myPort.available() > 0) {  // Si hay datos disponibles,
  val = myPort.readStringUntil('\n'); 
  try {
   sensorVal = Integer.valueOf(val.trim());
  }
  catch(Exception e) {
  ;
  }
  println(sensorVal); // léelos y guárdalos en vals!
  }  
 background(228, 204, 214, 1);
  // Escala el valor de mouseX de 0 a 640 a un rango entre 0 y 175
  float c = map(sensorVal, 70, width, 0, 800);
  // Escala el valor de mouseX de 0 a 640 a un rango entre 40 y 300
  float d = map(sensorVal, c, width, 40,3000);
  fill(135, c, 88);
  ellipse(width/230, height/67, 90, d);   
    fill(c, 170, 179);
  ellipse(width/d, height/2, d, 80);
    ellipse(width/2, height/2, 90, d);   
    fill(241, c, 89);
  ellipse(width/9, height/2, d, 34);
}
 ```
<img src="https://github.com/inarod/interfazII/blob/main/IMG/elipse%201.png"/>
<img src="https://github.com/inarod/interfazII/blob/main/IMG/elipse%202.png" />



### ej n° 7pulsador y visuales de processing 
## en processing
```
import processing.serial.*;

Serial myPort;
ArrayList<PVector> circles; 

void setup() {
  size(1080, 1080);
  background(0);
  
  // Ajusta el nombre del puerto según tu Arduino
  println(Serial.list());
  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort = new Serial(this, Serial.list()[0], 9600);
  
  circles = new ArrayList<PVector>();
}

void draw() {
  //background(0);
  
  // Dibujar círculos almacenados
  fill(random(150), random(30), random(120));
  //noStroke();
  stroke(random(250), random(250), 230, random(180));
  for (PVector c : circles) {
    ellipse(c.x, c.y, random(100), random(100));
  }
  
  // Revisar si llega algo de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.equals("1")) {
        // Cada vez que se aprieta el botón, agregar un círculo en posición aleatoria
        circles.add(new PVector(random(width), random(height)));
      }
    }
  }
}
```
## en  arduino
```
int buttonPin = 2;  // Pin del botón
int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Botón con resistencia interna
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {   // Botón presionado
    Serial.println(1);        // Enviar un "1" a Processing
    delay(200);               // Evitar rebotes
  }
}

```
