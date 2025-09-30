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
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/Captura%20de%20pantalla%202025-09-02%20124703.png"/>

### ej n° 8, potenciador y boton en processing
```
import processing.serial.*;

Serial myPort;
ArrayList<CircleData> circles; 

void setup() {
  size(1200, 720);
  background(235, 221, 221);
  
  // Ajusta el puerto según tu Arduino
  println(Serial.list());
  //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600);
  myPort = new Serial(this, Serial.list()[0], 9600);
  
  circles = new ArrayList<CircleData>();
}

void draw() {
  //background(250));
  
  // Dibujar todos los círculos guardados
  //fill(0, random(150), random(255));
  //noStroke();
  fill(209 , random(255), 186, 70);
  stroke(186, 136, random(255), 80);
  for (CircleData c : circles) {
    ellipse(c.x, c.y, c.size, c.size);
  }
  
  // Leer datos de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.startsWith("BTN")) {
        // Extraer el valor del potenciómetro
        String[] parts = split(val, ',');
        if (parts.length == 2) {
          float potVal = float(parts[1]);
          float circleSize = map(potVal, 60, 1023, random(300), random(150)); // tamaño 10-100 px
          circles.add(new CircleData(random(width), random(height), circleSize));
        }
      }
    }
  }
}

// Clase para guardar datos de cada círculo
class CircleData {
  float x, y, size;
  CircleData(float x, float y, float size) {
    this.x = x;
    this.y = y;
    this.size = size;
  }
}
```
## en arduino
```
int buttonPin = 2;       // Pin del botón
int potPin = A0;         // Pin del potenciómetro
int buttonState = 0;

void setup() {
  pinMode(buttonPin, INPUT_PULLUP); // Botón con resistencia interna
  Serial.begin(9600);
}

void loop() {
  buttonState = digitalRead(buttonPin);

  if (buttonState == HIGH) {   // Botón presionado
    int potValue = analogRead(potPin);   // 0 - 1023
    Serial.print("BTN,");     // etiqueta para Processing
    Serial.println(potValue); // mando el valor junto con el evento
    delay(200);               // debounce simple
  }
}
```
## resultados 
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/Captura%20de%20pantalla%202025-09-02%20133606.png"/>
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/Captura%20de%20pantalla%202025-09-02%20133635.png"/>
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/Captura%20de%20pantalla%202025-09-02%20133614.png"/>
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/Captura%20de%20pantalla%202025-09-02%20133653.png"/>

### ej n°9  led pares e impares
```
 int leds[] = {2, 3, 4, 5}; // Creamos un arreglo con los pines donde van conectados los LEDs

void setup() {
  // Esta función corre solo una vez al iniciar Arduino
  for (int i = 0; i < 4; i++) {         // Recorre el arreglo desde i = 0 hasta i = 3
    pinMode(leds[i], OUTPUT);           // Configura cada pin del arreglo como salida (para controlar LEDs)
  }
}

void loop() {
  // Esta función corre en bucle infinito
  for (int i = 0; i < 4; i++) {         // Recorre los 4 LEDs, uno por uno
    if (i % 2 == 0) {                   // Si el índice es par (0, 2)...
      digitalWrite(leds[i], HIGH);      // Enciende el LED correspondiente
    } else {                            // Si el índice es impar (1, 3)...
      digitalWrite(leds[i], LOW);       // Apaga el LED correspondiente
    }
    delay(500);                         // Espera 0,5 segundos antes de pasar al siguiente
  }
}
``` 
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/impar.png"/>


### ej n°10 Botonera & 4 leds
```
// --- Configuración de botones ---
const int numButtons = 3;
const int buttonPins[numButtons] = {2, 4, 7};
const int ledButtonPins[numButtons] = {9, 10, 11}; // LEDs botones

// --- Configuración de potenciómetros ---
const int numPots = 2;
const int potPins[numPots] = {A0, A1};
const int ledPotPins[numPots] = {3, 5}; // LEDs PWM

// Variables de estados previos
int lastButtonState[numButtons];
int lastPotValue[numPots];

void setup() {
  Serial.begin(9600);

  // Configurar botones y LEDs
  for (int i = 0; i < numButtons; i++) {
    pinMode(buttonPins[i], INPUT_PULLUP);
    pinMode(ledButtonPins[i], OUTPUT);
    lastButtonState[i] = digitalRead(buttonPins[i]);
  }

  // Configurar LEDs de potenciómetros
  for (int i = 0; i < numPots; i++) {
    pinMode(ledPotPins[i], OUTPUT);
    lastPotValue[i] = analogRead(potPins[i]);
  }
}

void loop() {
  // Leer y enviar botones
  for (int i = 0; i < numButtons; i++) {
    int buttonState = digitalRead(buttonPins[i]);

    // LED se enciende cuando botón está presionado
    digitalWrite(ledButtonPins[i], buttonState == LOW ? HIGH : LOW);

    if (buttonState != lastButtonState[i]) {  // enviar cambios
      Serial.print("B");
      Serial.print(i); 
      Serial.print(":");
      Serial.println(buttonState);
      lastButtonState[i] = buttonState;
    }
  }

  // Leer y enviar potenciómetros
  for (int i = 0; i < numPots; i++) {
    int potValue = analogRead(potPins[i]); // 0–1023
    int pwmValue = potValue / 4;           // 0–255

    // Ajustar LED según valor
    analogWrite(ledPotPins[i], pwmValue);

    if (abs(pwmValue - lastPotValue[i]) > 2) { // evitar ruido
      Serial.print("P");
      Serial.print(i);
      Serial.print(":");
      Serial.println(pwmValue);
      lastPotValue[i] = pwmValue;
    }
  }

  delay(10);
}
``` 
<img src="https://raw.githubusercontent.com/inarod/interfazII/refs/heads/main/IMG/botonera.png"/>



#### ej. PRESENTACIÓN
En este ejercicio  realizare visuales similares a las que realizamos en el ejercicio 
para esto trabaje adjuntando el codigo de processing del ejercico número 6, enviando este codigo a chat gpt y que me ayudara a modificarlo.
## primer codigo
para el primer codigo, le di el siguiente prompt a chat gpt:
necesito que conviertas este mismo codigo de processing en algo nuevo, cambiando los ellipses en una nueva figura, estrellas de colores que lentamente giren y se desplacen por el espacio, creando visuales psicodelicas. adjunto el codigo a continuacion
import processing.serial.*; Serial myPort; ArrayList<PVector> circles; void setup() { size(1080, 1080); background(0); // Ajusta el nombre del puerto según tu Arduino println(Serial.list()); //myPort = new Serial(this, "/dev/cu.usbmodem1101", 9600); myPort = new Serial(this, Serial.list()[0], 9600); circles = new ArrayList<PVector>(); } void draw() { //background(0); // Dibujar círculos almacenados fill(random(150), random(30), random(120)); //noStroke(); stroke(random(250), random(250), 230, random(180)); for (PVector c : circles) { ellipse(c.x, c.y, random(100), random(100)); } // Revisar si llega algo de Arduino if (myPort.available() > 0) { String val = myPort.readStringUntil('\n'); if (val != null) { val = trim(val); if (val.equals("1")) { // Cada vez que se aprieta el botón, agregar un círculo en posición aleatoria circles.add(new PVector(random(width), random(height))); } } } }

# resultado de codigo dado por chat gpt
```
import processing.serial.*;

Serial myPort;
ArrayList<Star> stars;

void setup() {
  size(1080, 1080);
  background(0);
  println(Serial.list());
  myPort = new Serial(this, Serial.list()[0], 9600);
  stars = new ArrayList<Star>();
}

void draw() {
  fill(0, 20);  // Fondo semi-transparente para dejar rastros
  rect(0, 0, width, height);  // "Limpieza" con transparencia

  // Dibujar y actualizar cada estrella
  for (Star s : stars) {
    s.update();
    s.display();
  }

  // Leer datos de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.equals("1")) {
        stars.add(new Star());
      }
    }
  }
}

// ==== Clase Star (estrella animada) ====
class Star {
  PVector pos, vel;
  float angle, rotSpeed;
  color col;
  float size;

  Star() {
    pos = new PVector(random(width), random(height));
    vel = PVector.random2D().mult(random(0.5, 2));
    angle = random(TWO_PI);
    rotSpeed = random(-0.01, 0.01);
    col = color(random(255), random(255), random(255));
    size = random(20, 60);
  }

  void update() {
    pos.add(vel);
    angle += rotSpeed;

    // Rebote en bordes
    if (pos.x < 0 || pos.x > width) vel.x *= -1;
    if (pos.y < 0 || pos.y > height) vel.y *= -1;
  }

  void display() {
    pushMatrix();
    translate(pos.x, pos.y);
    rotate(angle);
    noStroke();
    fill(col, 180);
    drawStar(0, 0, size * 0.5, size, 5);
    popMatrix();
  }

  // Función para dibujar una estrella
  void drawStar(float x, float y, float radius1, float radius2, int npoints) {
    float angle = TWO_PI / npoints;
    float halfAngle = angle / 2.0;
    beginShape();
    for (float a = 0; a < TWO_PI; a += angle) {
      float sx = x + cos(a) * radius2;
      float sy = y + sin(a) * radius2;
      vertex(sx, sy);
      sx = x + cos(a + halfAngle) * radius1;
      sy = y + sin(a + halfAngle) * radius1;
      vertex(sx, sy);
    }
    endShape(CLOSE);
  }
}
```
el resultado de este codigo me pareció impresionante, sin embargo habian cosas que ajustar.

## segundo codigo 
para este codigo, este fue el prompt que le di a chat gpt para que modificara mi trabajo
"haz que todos los colores de las estrellas correspondan a una gama de rosados, que dentro de las mismas estrellas surgan mas particulas y estrellas, y que ademas estas puedan interactuar evitando el contacto con el mouse"

```
import processing.serial.*;

Serial myPort;
ArrayList<Star> stars;
ArrayList<Particle> particles;

void setup() {
  size(1080, 1080);
  background(0);
  println(Serial.list());
  myPort = new Serial(this, Serial.list()[0], 9600);
  stars = new ArrayList<Star>();
  particles = new ArrayList<Particle>();
}

void draw() {
  fill(0, 20);
  rect(0, 0, width, height);  // Fondo con transparencia para efecto rastro

  // Actualizar y mostrar partículas
  for (int i = particles.size() - 1; i >= 0; i--) {
    Particle p = particles.get(i);
    p.update();
    p.display();
    if (p.isDead()) {
      particles.remove(i);
    }
  }

  // Actualizar y mostrar estrellas
  for (Star s : stars) {
    s.update();
    s.display();
  }

  // Leer datos de Arduino
  if (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.equals("1")) {
        stars.add(new Star());
      }
    }
  }
}

// ==== Clase Star ====
class Star {
  PVector pos, vel;
  float angle, rotSpeed;
  color col;
  float size;
  int emitTimer = 0;

  Star() {
    pos = new PVector(random(width), random(height));
    vel = PVector.random2D().mult(random(0.5, 1.5));
    angle = random(TWO_PI);
    rotSpeed = random(-0.01, 0.01);
    col = randomPink();
    size = random(30, 60);
  }

  void update() {
    applyMouseRepulsion(pos, vel, 80, 0.5);
    pos.add(vel);
    angle += rotSpeed;

    // Rebote
    if (pos.x < 0 || pos.x > width) vel.x *= -1;
    if (pos.y < 0 || pos.y > height) vel.y *= -1;

    // Emitir partículas cada ciertos frames
    emitTimer++;
    if (emitTimer > 15) {
      particles.add(new Particle(pos.copy(), col));
      emitTimer = 0;
    }
  }

  void display() {
    pushMatrix();
    translate(pos.x, pos.y);
    rotate(angle);
    noStroke();
    fill(col, 180);
    drawStar(0, 0, size * 0.4, size, 5);
    popMatrix();
  }
}

// ==== Clase Particle ====
class Particle {
  PVector pos, vel;
  float lifespan;
  float angle;
  float size;
  color col;

  Particle(PVector origin, color c) {
    pos = origin.copy();
    vel = PVector.random2D().mult(random(1, 2));
    lifespan = 255;
    angle = random(TWO_PI);
    size = random(5, 15);
    col = c;
  }

  void update() {
    applyMouseRepulsion(pos, vel, 60, 1.0);
    pos.add(vel);
    angle += 0.05;
    lifespan -= 2;
  }

  void display() {
    pushMatrix();
    translate(pos.x, pos.y);
    rotate(angle);
    noStroke();
    fill(col, lifespan);
    drawStar(0, 0, size * 0.4, size, 5);
    popMatrix();
  }

  boolean isDead() {
    return lifespan <= 0;
  }
}

// ==== Dibujar estrella ====
void drawStar(float x, float y, float radius1, float radius2, int npoints) {
  float angle = TWO_PI / npoints;
  float halfAngle = angle / 2.0;
  beginShape();
  for (float a = 0; a < TWO_PI; a += angle) {
    float sx = x + cos(a) * radius2;
    float sy = y + sin(a) * radius2;
    vertex(sx, sy);
    sx = x + cos(a + halfAngle) * radius1;
    sy = y + sin(a + halfAngle) * radius1;
    vertex(sx, sy);
  }
  endShape(CLOSE);
}

// ==== Repulsión del mouse ====
void applyMouseRepulsion(PVector pos, PVector vel, float radius, float strength) {
  float d = dist(mouseX, mouseY, pos.x, pos.y);
  if (d < radius && d > 0) {
    PVector dir = PVector.sub(pos, new PVector(mouseX, mouseY));
    dir.normalize();
    dir.mult(strength / d);
    vel.add(dir);
    vel.limit(3); // Limitar velocidad
  }
}

// ==== Generador de rosados ====
color randomPink() {
  float r = random(200, 255);
  float g = random(20, 100);
  float b = random(150, 255);
  return color(r, g, b);
}
```
# notas
este codigo seguia siendo bueno, pero necesitaba seguir probando con diferentes variables para ver las posibilidades que tenia y transformar esto a la visión que se iba formando en mente. por lo que segui especificando que es lo que buscaba.

## tercer codigo 
"me gustaria que en vez de estrellas fueran una forma de destellos, y que en vez de el color magenta, los tonos de rosado sean pastel, que el destello sea una forma 3d que se mueva aun mas lento y que gire sobre su eje, que no salga de este mas de 1 a 5 partículas que varien de tamaño por segundo, agregando un aleatorizador a esto, que mientras se mantenga presiónado el boton del pulsador aparezcan las figuras, y que el fondo sea de un color azul marino oscuro."
a lo que chat gpt me respondio con este codigo:

```
import processing.serial.*;

Serial myPort;
ArrayList<Glow> glows;
ArrayList<Particle> particles;

boolean buttonPressed = false;

void setup() {
  size(1080, 1080, P3D);
  background(10, 10, 40);  // Azul marino oscuro
  println(Serial.list());
  myPort = new Serial(this, Serial.list()[0], 9600);
  glows = new ArrayList<Glow>();
  particles = new ArrayList<Particle>();
}

void draw() {
  background(10, 10, 40, 100);  // Azul marino oscuro con transparencia para rastros

  if (buttonPressed) {
    // Generar nuevas glows lentamente
    if (frameCount % 30 == 0) {
      glows.add(new Glow());
    }
  }

  // Actualizar y mostrar partículas
  for (int i = particles.size() - 1; i >= 0; i--) {
    Particle p = particles.get(i);
    p.update();
    p.display();
    if (p.isDead()) {
      particles.remove(i);
    }
  }

  // Actualizar y mostrar glows
  for (Glow g : glows) {
    g.update();
    g.display();
  }

  // Leer datos Arduino para botón presionado
  while (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.equals("1")) {
        buttonPressed = true;
      } else {
        buttonPressed = false;
        glows.clear();
        particles.clear();
      }
    }
  }
}

// ==== Clase Glow (destello 3D) ====
class Glow {
  PVector pos, vel;
  float angleX, angleY;
  float rotSpeedX, rotSpeedY;
  color col;
  float size;
  int emitTimer = 0;

  Glow() {
    pos = new PVector(random(width), random(height), random(-50, 50));
    vel = PVector.random3D().mult(0.2);
    angleX = random(TWO_PI);
    angleY = random(TWO_PI);
    rotSpeedX = random(-0.002, 0.002);
    rotSpeedY = random(-0.002, 0.002);
    col = randomPastelPink();
    size = random(50, 100);
  }

  void update() {
    applyMouseRepulsion3D(pos, vel, 80, 0.3);
    pos.add(vel);
    angleX += rotSpeedX;
    angleY += rotSpeedY;

    // Mantener dentro del canvas 2D + z limitado
    pos.x = constrain(pos.x, 0, width);
    pos.y = constrain(pos.y, 0, height);
    pos.z = constrain(pos.z, -50, 50);

    // Emitir partículas aleatoriamente entre 1 y 5 por segundo
    emitTimer++;
    if (emitTimer >= 60) {  // 60 frames ~1 seg
      int numToEmit = (int)random(1, 6);
      for (int i = 0; i < numToEmit; i++) {
        particles.add(new Particle(pos.copy(), col));
      }
      emitTimer = 0;
    }
  }

  void display() {
    pushMatrix();
    translate(pos.x, pos.y, pos.z);
    rotateX(angleX);
    rotateY(angleY);
    noStroke();
    fill(col, 180);
    drawGlowShape(size);
    popMatrix();
  }
}

// ==== Clase Particle ====
class Particle {
  PVector pos, vel;
  float lifespan;
  float angle;
  float size;
  color col;

  Particle(PVector origin, color c) {
    pos = origin.copy();
    vel = PVector.random3D().mult(random(0.2, 1.0));
    lifespan = 255;
    angle = random(TWO_PI);
    size = random(5, 20);
    col = c;
  }

  void update() {
    applyMouseRepulsion3D(pos, vel, 60, 0.5);
    pos.add(vel);
    angle += 0.01;
    lifespan -= 3;
  }

  void display() {
    pushMatrix();
    translate(pos.x, pos.y, pos.z);
    rotateZ(angle);
    noStroke();
    fill(col, lifespan);
    drawGlowShape(size * 0.3);
    popMatrix();
  }

  boolean isDead() {
    return lifespan <= 0;
  }
}

// ==== Dibujar forma destello 3D ====
void drawGlowShape(float s) {
  // Octaedro simple con picos brillantes
  beginShape(TRIANGLES);

  // 6 vértices básicos octaedro
  PVector[] vertices = {
    new PVector(0, s, 0),
    new PVector(-s, 0, 0),
    new PVector(0, 0, s),

    new PVector(0, s, 0),
    new PVector(0, 0, s),
    new PVector(s, 0, 0),

    new PVector(0, s, 0),
    new PVector(s, 0, 0),
    new PVector(0, 0, -s),

    new PVector(0, s, 0),
    new PVector(0, 0, -s),
    new PVector(-s, 0, 0),

    new PVector(0, -s, 0),
    new PVector(0, 0, s),
    new PVector(-s, 0, 0),

    new PVector(0, -s, 0),
    new PVector(s, 0, 0),
    new PVector(0, 0, s),

    new PVector(0, -s, 0),
    new PVector(0, 0, -s),
    new PVector(s, 0, 0),

    new PVector(0, -s, 0),
    new PVector(-s, 0, 0),
    new PVector(0, 0, -s)
  };

  for (PVector v : vertices) {
    vertex(v.x, v.y, v.z);
  }

  endShape();
}

// ==== Repulsión mouse 3D ====
void applyMouseRepulsion3D(PVector pos, PVector vel, float radius, float strength) {
  PVector mousePos = new PVector(mouseX, mouseY, 0);
  float d = PVector.dist(mousePos, pos);
  if (d < radius && d > 0) {
    PVector dir = PVector.sub(pos, mousePos);
    dir.normalize();
    dir.mult(strength / d);
    vel.add(dir);
    vel.limit(1.5);
  }
}

// ==== Generar color pastel rosa ====
color randomPastelPink() {
  float r = random(230, 255);
  float g = random(180, 200);
  float b = random(200, 230);
  return color(r, g, b);
}
```

le pedi a chat gpt que editara el codigo para que funcione junto al potenciometro y a la vez le pedi un nuevo codigo de arduino

## NUEVO CODIGO PARA PROCESSING
```
import processing.serial.*;

Serial myPort;
ArrayList<Glow> glows;
ArrayList<Particle> particles;

boolean buttonPressed = false;
float sizeFactor = 1.0;  // Factor de escala para tamaños

void setup() {
  size(1080, 1080, P3D);
  background(10, 10, 40);  // Azul marino oscuro
  println(Serial.list());
  myPort = new Serial(this, Serial.list()[0], 9600);
  glows = new ArrayList<Glow>();
  particles = new ArrayList<Particle>();
}

void draw() {
  background(10, 10, 40, 100);  // Azul marino oscuro con transparencia para rastros

  if (buttonPressed) {
    // Generar nuevas glows lentamente
    if (frameCount % 30 == 0) {
      glows.add(new Glow());
    }
  }

  // Actualizar y mostrar partículas
  for (int i = particles.size() - 1; i >= 0; i--) {
    Particle p = particles.get(i);
    p.update();
    p.display();
    if (p.isDead()) {
      particles.remove(i);
    }
  }

  // Actualizar y mostrar glows
  for (Glow g : glows) {
    g.update();
    g.display();
  }

  // Leer datos Arduino para botón y potenciómetro
  while (myPort.available() > 0) {
    String val = myPort.readStringUntil('\n');
    if (val != null) {
      val = trim(val);
      if (val.startsWith("BTN:")) {
        String btnVal = val.substring(4);
        buttonPressed = btnVal.equals("1");
        if (!buttonPressed) {
          glows.clear();
          particles.clear();
        }
      } else if (val.startsWith("POT:")) {
        String potValStr = val.substring(4);
        try {
          int potVal = Integer.parseInt(potValStr);
          // Mapear de 0-1023 a 0.5 - 2.0 factor de tamaño
          sizeFactor = map(potVal, 0, 1023, 0.5, 2.0);
        } catch (Exception e) {
          // Ignorar errores de parseo
        }
      }
    }
  }
}

// ==== Clase Glow (destello 3D) ====
class Glow {
  PVector pos, vel;
  float angleX, angleY;
  float rotSpeedX, rotSpeedY;
  color col;
  float size;
  int emitTimer = 0;

  Glow() {
    pos = new PVector(random(width), random(height), random(-50, 50));
    vel = PVector.random3D().mult(0.2);
    angleX = random(TWO_PI);
    angleY = random(TWO_PI);
    rotSpeedX = random(-0.002, 0.002);
    rotSpeedY = random(-0.002, 0.002);
    col = randomPastelPink();
    size = random(50, 100);
  }

  void update() {
    applyMouseRepulsion3D(pos, vel, 80, 0.3);
    pos.add(vel);
    angleX += rotSpeedX;
    angleY += rotSpeedY;

    // Mantener dentro del canvas 2D + z limitado
    pos.x = constrain(pos.x, 0, width);
    pos.y = constrain(pos.y, 0, height);
    pos.z = constrain(pos.z, -50, 50);

    // Emitir partículas aleatoriamente entre 1 y 5 por segundo
    emitTimer++;
    if (emitTimer >= 60) {  // 60 frames ~1 seg
      int numToEmit = (int)random(1, 6);
      for (int i = 0; i < numToEmit; i++) {
        particles.add(new Particle(pos.copy(), col));
      }
      emitTimer = 0;
    }
  }

  void display() {
    pushMatrix();
    translate(pos.x, pos.y, pos.z);
    rotateX(angleX);
    rotateY(angleY);
    noStroke();
    fill(col, 180);
    drawGlowShape(size * sizeFactor);
    popMatrix();
  }
}

// ==== Clase Particle ====
class Particle {
  PVector pos, vel;
  float lifespan;
  float angle;
  float size;
  color col;

  Particle(PVector origin, color c) {
    pos = origin.copy();
    vel = PVector.random3D().mult(random(0.2, 1.0));
    lifespan = 255;
    angle = random(TWO_PI);
    size = random(5, 20);
    col = c;
  }

  void update() {
    applyMouseRepulsion3D(pos, vel, 60, 0.5);
    pos.add(vel);
    angle += 0.01;
    lifespan -= 3;
  }

  void display() {
    pushMatrix();
    translate(pos.x, pos.y, pos.z);
    rotateZ(angle);
    noStroke();
    fill(col, lifespan);
    drawGlowShape(size * 0.3 * sizeFactor);
    popMatrix();
  }

  boolean isDead() {
    return lifespan <= 0;
  }
}

// ==== Dibujar forma destello 3D ====
void drawGlowShape(float s) {
  // Octaedro simple con picos brillantes
  beginShape(TRIANGLES);

  // 6 vértices básicos octaedro
  PVector[] vertices = {
    new PVector(0, s, 0),
    new PVector(-s, 0, 0),
    new PVector(0, 0, s),

    new PVector(0, s, 0),
    new PVector(0, 0, s),
    new PVector(s, 0, 0),

    new PVector(0, s, 0),
    new PVector(s, 0, 0),
    new PVector(0, 0, -s),

    new PVector(0, s, 0),
    new PVector(0, 0, -s),
    new PVector(-s, 0, 0),

    new PVector(0, -s, 0),
    new PVector(0, 0, s),
    new PVector(-s, 0, 0),

    new PVector(0, -s, 0),
    new PVector(s, 0, 0),
    new PVector(0, 0, s),

    new PVector(0, -s, 0),
    new PVector(0, 0, -s),
    new PVector(s, 0, 0),

    new PVector(0, -s, 0),
    new PVector(-s, 0, 0),
    new PVector(0, 0, -s)
  };

  for (PVector v : vertices) {
    vertex(v.x, v.y, v.z);
  }

  endShape();
}

// ==== Repulsión mouse 3D ====
void applyMouseRepulsion3D(PVector pos, PVector vel, float radius, float strength) {
  PVector mousePos = new PVector(mouseX, mouseY, 0);
  float d = PVector.dist(mousePos, pos);
  if (d < radius && d > 0) {
    PVector dir = PVector.sub(pos, mousePos);
    dir.normalize();
    dir.mult(strength / d);
    vel.add(dir);
    vel.limit(1.5);
  }
}

// ==== Generar color pastel rosa ====
color randomPastelPink() {
  float r = random(230, 255);
  float g = random(180, 200);
  float b = random(200, 230);
  return color(r, g, b);
}
```
### CODIGO PARA ARDUINO 

```
// Pines Arduino
const int buttonPin = 2;      // Pin donde está conectado el botón
const int potPin = A0;        // Pin analógico donde está conectado el potenciómetro

void setup() {
  Serial.begin(9600);
  pinMode(buttonPin, INPUT_PULLUP);  // Asumiendo botón conectado a GND con resistencia pull-up interna
}

void loop() {
  // Leer estado botón (invertido porque INPUT_PULLUP)
  int buttonState = digitalRead(buttonPin);
  int btnValue = (buttonState == LOW) ? 1 : 0;  // Presionado = 1, no presionado = 0

  // Leer potenciómetro (0-1023)
  int potValue = analogRead(potPin);

  // Enviar datos por Serial en formato esperado
  Serial.print("BTN:");
  Serial.println(btnValue);

  Serial.print("POT:");
  Serial.println(potValue);

  delay(50);  // Ajustar tasa de envío (20 veces por segundo)
}
``` 
