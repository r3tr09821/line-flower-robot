# line-flower-robot
code, scheme, componets and software for a line folower robot

Pasul 1: Pregătirea, Alinierea și Fixarea Mecanică a Motoarelor

Fixarea suporturilor: Poziționați cele două suporturi metalice sau de plastic pe șasiu. Asigurați-vă că acestea sunt perfect paralele între ele și perpendiculare pe axa longitudinală a robotului.

Scurtcircuitarea zgomotului parazit: Opțional, dar recomandat, lipiți un condensator ceramic de 100 nF direct între bornele fiecărui motor DC pentru a filtra zgomotul electromagnetic ce poate reseta placa Arduino.

Strângerea hardware: Utilizați șuruburi cu piulițe auto-blocante (cu inserție de nylon). Vibrațiile provocate de rotația motoarelor vor slăbi rapid șuruburile simple, ducând la pierderea alinierii pe pistă.

Pasul 2: Montarea Ansamblului de Rulare (Roți și Caster)

Presarea roților principale: Introduceți roțile pe axele teșite (în formă de D) ale motoarelor. Împingeți ferm, dar fără a forța carcasa reductorului de plastic, lăsând un spațiu de 1–2 mm între roată și șasiu pentru a evita frecarea.

Montarea roții pivotante (Caster): Fixați roata caster în punctul cel mai avansat al șasiului (pe axa centrală).

Echilibrarea gărzii la sol: Ajustați înălțimea roții caster folosind distanțiere astfel încât șasiul să rămână perfect paralel cu solul, asigurând o distribuție egală a greutății.

Pasul 3: Fixarea Componentelor Logice și de Control (Arduino și L298N)

Izolarea electrică: Plasați distanțiere de plastic (sau bandă izolatoare) pe șasiu sub zonele unde veți monta Arduino Nano/Uno și driverul L298N. Pinii lipiți pe spatele acestor plăci nu trebuie să atingă nicio suprafață conductoare.

Poziționarea L298N: Fixați driverul în centrul geometric al robotului. Acest lucru scurtează traseele de fire către motoare și către acumulatori.

Poziționarea Arduino: Fixați placa Arduino în spatele driverului sau pe un etaj superior (dacă șasiul este de tip dublu), lăsând portul USB liber și ușor accesibil pentru cablul de programare.

Pasul 4: Montarea și Ajustarea Geometrică a Barei de Senzori IR

Alinierea centrală: Fixați bara roșie cu cei 8 senzori în cel mai avansat punct frontal al robotului. Centrul fizic al barei (spațiul dintre senzorii 4 și 5) trebuie să coincidă perfect cu axa centrală a robotului.

Reglarea înălțimii critice: Poziționați bara astfel încât ledurile emițătoare/receptoare să se afle la o distanță cuprinsă strict între 5 mm și 8 mm față de suprafața pistei.

Rigidizarea suportului: Asigurați-vă că suportul barei de senzori este complet rigid. Dacă bara oscilează sau se mișcă în timpul frânărilor sau virajelor, robotul va pierde instantaneu linia din cauza modificării unghiului de citire.

Pasul 5: Instalarea și Securizarea Subsistemului de Alimentare

Poziționarea suportului de baterii: Fixați suportul pentru cele două celule 18650 în partea din spate a șasiului, direct deasupra sau imediat în spatele axei roților motoare pentru a maximiza tracțiunea (aderența).

Securizarea acumulatorilor: Utilizați o bandă velcro sau cleme de fixare rigide. În timpul virajelor strânse, forța centrifugă poate deplasa acumulatorii dacă nu sunt fixați, modificând centrul de greutate și destabilizând robotul.

Adăugarea unui întrerupător: Întrerupeți firul pozitiv (+) care pleacă de la baterie către borna +12V a L298N și introduceți un comutator mecanic (ON/OFF) pentru a putea opri de urgență robotul în caz de eșec al codului.

Pasul 6: Configurarea și Testarea Mediului Software (Arduino IDE)

Instalarea driverelor: Dacă folosiți o placă Arduino clonă (foarte comună în kituri), descărcați și instalați driverul CH340 de pe internet, altfel calculatorul nu va aloca un port COM pentru placa USB.

Deschiderea și curățarea schiței: Lansați Arduino IDE, ștergeți liniile generate automat (void setup() și void loop() goale) și introduceți prin copy-paste codul complet furnizat anterior.

Compilarea de siguranță: Apăsați butonul cu pictogramă "bifă" (Verify). Urmăriți bara de status din josul paginii; procesul trebuie să se încheie fără text roșu (erori de sintaxă).

Pasul 7: Transferul Firmware-ului (Upload) pe Microcontroler

Conectarea fără putere externă: Conectați cablul USB la calculator și la Arduino. Atenție: Comutatorul de alimentare al bateriilor trebuie să fie pe poziția OFF. Placa se va alimenta direct din USB pentru programare.

Selectarea țintei: Accesați meniul Tools -> Board și bifați tipul plăcii dumneavoastră. Accesați Tools -> Port și selectați portul nou apărut (ex. COM3).

Procedura de Upload: Apăsați butonul cu pictogramă "săgeată" (Upload). Dacă încărcarea eșuează cu eroarea "stk500_getsync()", schimbați procesorul din Tools -> Processor în ATmega328P (Old Bootloader) și reîncercați.

Pasul 8: Calibrarea Hardware a Senzorilor pe Pistă

Pregătirea terenului: Plasați robotul pe o zonă a pistei unde linia neagră este perfect dreaptă. Porniți comutatorul bateriilor (ON).

Verificarea polarității: Ridicați ușor robotul și treceți un senzor peste linia neagră. Verificați dacă ledul corespunzător de pe spatele barei își schimbă starea (se aprinde sau se stinge pe negru).

Reglarea pragului de sensibilitate: Dacă ledurile nu reacționează sau rămân mereu aprinse, folosiți o șurubelniță mică pentru a învârti fin potențiometrul de pe bara de senzori până când obțineți o distincție clară între alb (suprafața de rulare) și negru (linia de urmat).

Pasul 9: Diagnosticul Cinematic Final și Corecția Direcției

Testul în gol: Cu robotul suspendat (roțile în aer) și pornit, acoperiți cu degetul senzorii din extrema stângă. Roata stângă ar trebui să se rotească înapoi sau mai încet, iar cea dreaptă înainte (robotul încearcă să vireze stânga pentru a reveni pe linie).

Corectarea inversării de fază: Dacă în urma testului de mai sus roțile se comportă invers (ex: robotul virează dreapta când linia este în stânga), opriți imediat alimentarea.

Remedierea cablajului: Nu modificați codul. Inversați fizic firele motorului care rulează greșit în bornele albastre ale driverului L298N (schimbați firul din OUT1 cu cel din OUT2 sau OUT3 cu OUT4). Reporniți și lansați robotul pe pistă.

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
