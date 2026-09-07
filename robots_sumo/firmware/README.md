## Códigos
# Código de los motores

const int pinIN1 = 7;
const int pinIN2 = 6;

void setup() {
  // inicializar la comunicación serial a 9600 bits por segundo:
  Serial.begin(9600);
  // configuramos los pines como salida
  pinMode(pinIN1, OUTPUT);
  pinMode(pinIN2, OUTPUT);
}

void loop() {
  
  MotorHorario();
  Serial.println("Giro en sentido horario");
  delay(5000);

  MotorStop();
  Serial.println("Motor para");
  delay(3000);
  
  MotorAntihorario();
  Serial.println("Giro en sentido antihorario");
  delay(5000);
  
  MotorStop();
  Serial.println("Motor para");
  delay(3000);
  
}

//función para girar el motor en sentido horario
void MotorHorario()
{
  digitalWrite (pinIN1, HIGH);
  digitalWrite (pinIN2, LOW);
}
//función para girar el motor en sentido antihorario
void MotorAntihorario()
{
  digitalWrite (pinIN1, LOW);
  digitalWrite (pinIN2, HIGH);
}

//función para apagar el motor
void MotorStop()
{
  digitalWrite (pinIN1, LOW);
  digitalWrite (pinIN2, LOW);
}
