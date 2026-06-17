# line-flower-robot
code, scheme, componets and software for a line folower robot

Pasul 1: Pregătirea și Debarasarea Șasiului
Se fixează suporturile de plastic sau metal ale celor două motoare DC pe platforma inferioară a șasiului, asigurându-se că axele motoarelor sunt perfect perpendiculare pe axa de mers înainte.

Pasul 2: Montarea Roților și a Sprijinului Caster
Se presează roțile principale pe axele motoarelor DC și se înșurubează roata pivotantă (tip caster) în partea din față a șasiului, asigurând stabilitatea pe trei puncte și o gardă la sol uniformă.

Pasul 3: Fixarea Plăcii de Dezvoltare și a Driverului
Se poziționează placa Arduino Nano/Uno și driverul L298N pe centrul de masă al șasiului folosind distanțiere de plastic pentru a preveni scurtcircuitele accidentale cu elementele metalice.

Pasul 4: Poziționarea Barei de Senzori IR
Se montează bara roșie de 8 senzori în partea frontală a robotului, la o distanță de maxim 5-10 milimetri față de sol. Orice distanță mai mare va duce la pierderea focalizării fasciculului infraroșu și la citiri eronate.

Pasul 5: Instalarea Unității de Stocare a Energiei
Se montează suportul pentru cei doi acumulatori reincarcabili 18650 în partea din spate a robotului pentru a echilibra greutatea exercitată pe puntea spate și a asigura aderența roților.

Pasul 6: Descărcarea și Pregătirea Mediului Arduino IDE
Se descarcă aplicația oficială Arduino IDE pe calculator, se rulează kitul de instalare și se conectează cablul USB la placa Arduino fără a introduce încă acumulatorii în robot.

Pasul 7: Încărcarea Firmware-ului de Control
Se deschide codul sursă furnizat în editor, se selectează tipul corect de placă și portul COM corespunzător din meniu, apoi se apasă butonul "Upload" până când pe ecran apare mesajul de confirmare succesivă.

Pasul 8: Testarea Sensibilității Senzorilor (Calibrare)
Se alimentează robotul și se apropie bara de senzori de linia neagră. Se ajustează potențiometrele mici (dacă modulul dispune de ele) până când ledurile indicatoare de pe spatele barei se aprind doar atunci când senzorul se află strict deasupra benzii negre.

Pasul 9: Testul de Direcție și Lansarea pe Pistă
Se plasează robotul pe circuitul cu linie neagră și se pornește alimentarea principală. Dacă robotul virează în direcția opusă liniei, se oprește alimentarea și se inversează firele motorului respectiv direct în puntea L298N pentru a corecta sensul cinematic.

Conexiiuni:
D6 -> ENA (L298N Driver)

D2 -> IN1 (L298N Driver)

D3 -> IN2 (L298N Driver)

D12 -> IN3 (L298N Driver)

D13 -> IN4 (L298N Driver)

D11 -> ENB (L298N Driver)

D4 -> Out 1 (Bara Senzori IR)

D5 -> Out 2 (Bara Senzori IR)

D7 -> Out 3 (Bara Senzori IR)

D8 -> Out 4 (Bara Senzori IR)

D9 -> Out 5 (Bara Senzori IR)

D10 -> Out 6 (Bara Senzori IR)

A0 -> Out 7 (Bara Senzori IR)

A1 -> Out 8 (Bara Senzori IR)

5V -> 5V (Arduino Nano din L298N)

GND -> GND (Masa Comună L298N - Arduino Nano)

5V -> VCC (Bara Senzori IR din Arduino)

GND -> GND (Bara Senzori IR din Arduino)

Baterie (+) -> +12V (L298N Driver)

Baterie (-) -> GND (L298N Driver)
