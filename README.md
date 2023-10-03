# Minor_DET_IoT_AnoukPebesma

<h1>Hoe maak je een Philips Hue in minder dan 5 euro?</h1>
In dit artikel/verslag neem ik jou meer naar hoe jij dit kan maken. Ik zal hierbij de stappen uitleggen en de daarbij gemaakte fouten ook laten zien. 

<h2> Wat heb je nodig? </h2>
<li>1x Arduino Board (ESP8266)</li>
<li>1x Jump wire</li>
<li>1x LEDstrip </li>
<li>Maar natuurlijk ook een laptop/computer en een USB-c kabel om de Arduino te verbinden. </li>

<h2> Stap 1: Installeer de Arduino IO library </h2>
<ol>
  <li>
    De eerste stap is om een extra library te installeren, de Adafruit IO Arduino (gemaakt door: Adafruit).<br>
    Deze vind je door naar de library manager te gaan en 'Adafruit IO Arduino' op te zoeken in het zoekvlak, heb je hem gevonden? <br>
    Druk op install all.
  </li>
</ol>
<img width="326" alt="step1" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/5cd79055-d66b-435f-9132-06e8acc0da1a">
<br>

<h2> Stap 2: Adafruit IO Setup </h2>
<ol>
  <li>
      Om te kunnen beginnen en gebruik te mogen maken van deze library. Moeten we een account aanmaken. <br>
      Hiervoor gaan we naar 'https://io.adafruit.com/'. Druk hierbij op 'get started for free' en maak een account aan.
      <img width="326" alt="step2" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/4895e213-334e-4914-8975-63704313c61b)"> <br>
      Je zult dit scherm zien, druk hierbij bovenin oo IO, om naar stap 2 te kunnen.
  </li>
  <li>
      In Adafruit IO aangekomen druk je op de gele sleutel in het menu.<br>
      <img width="326" alt="step3" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/9b5286ca-b0f5-4419-85d8-04e16b931f20)"><br>
  </li>
  <li>
      In het scherm dat je nu ziet, kopiër jij je key en je username. Deze heb je zo nodig!
  </li>
</ol>
<br>

<h2> Stap 3: Adafruit IO Feed en Colorpicker aanmaken </h2>
<ol>
  <li>
      Ga naar Dashboards, in het menu van de io.adafruit site te vinden. Maak hierbij een nieuw dashboard aan, klik op 'New Dashboard'.<br>
      <img width="326" alt="step4" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/0d911c3c-bb3f-4228-9bea-6867fc4339b6)"> <br>

  </li>
  
  <li>
      Ga naar het dashboard.
  </li>
  
  <li>  
      Creëer een nieuw block, druk op het instellingen icoontje, zoals te zien op de afbeelding hieronder.<br>
      <img width="326" alt="step5" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/1ea1b522-7745-45c9-a191-50c40ad9594e)"><br>
      Hierbij krijg je onderstaand beeld tezien. Druk hierbij op 'Create New Block'. <br>
      <img width="326" alt="step6" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/a0fc1e22-036d-402a-9622-df4b6fb40eeb)"> <br>

  </li>
  
  <li>
      Kies color picker. <br> 
      <img width="326" alt="step7" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/f11cfa04-fbf6-4568-a5db-62dca2fad3c9"><br>
  </li>

   <li>
      Creëer de feed naam: "color".<br>
     <img width="326" alt="step8" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/c67e8e88-c5a2-4fb8-89f0-917aaf089b2f"> <br>
     Als je, je muis naast het tekst veld houd. Verschijnt hier een Creëer knop. <br>
     <img width="326" alt="step9" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/9be94224-379c-4d09-9d72-95d812dc114c"> <br>
  </li>

   <li>
      Creëer block.
  </li>

   <li>
      Stel een kleur in met de color picker. Druk hierbij op de feed: color, die je zojuist hebt gemaakt.<br> Ga hierbij naar de volgende stap en verander de HEX code.<br>
      <img width="326" alt="step10" src="https://github.com/AnoukPNL/Minor_DET_IoT_AnoukPebesma/assets/112867115/1f6e797f-ff56-47e1-aa98-ec022cbf0ae4"> <br>
     
  </li>
</ol>
<br>

<h2> Stap 4: Code aanpassen! </h2>
<ol>
  <li>
      Ga naar Arduino IDE. <br>
      Ga naar file > examples > Adafruit IO Arduino > Adafruitio_14_neopixel <br>
      <img width="326" alt="step11" src="."> <br>
  </li>

  <li>
    In tab ‘config.h’: plak je Adafruit IO username en Key in.
  </li>

  <li>
    In tab ‘config.h’: voer het wifi netwerk en wachtwoord in. <br>
    A. (De NodeMCU werkt niet op 5Ghz WiFi) <br>
    B. Gebruik liefst de hotspot van je telefoon, dit gebruikt < 0.1 Mb data per uur, dus niet bang zijn.
  </li>

  <li>
    Ga naar de Tab adafruit_14_Neopixel.ino <br>
    A. Pas: #define PIXEL_PIN 5 aan naar #define PIXEL_PIN D5
  </li>
</ol>

<h2> Stap 5: Code uploaden </h2>
<ol>
  <li>
    Upoad de code! 
  </li>

  <li>
    Activeer de 'serial monitor'. Dit doe je door op de knop te drukken die hier onderstaand te zien is. <br>
    <img width="326" alt="step7" src="."> <br>
  </li>

  <li>
    Open de serial monitor (tab onderaan).
  </li>

  <li>
    Zet de serial monitor op 115200 baud.
  </li>

  <li>
    Als alles gelukt is zie je in de serial monitor dat je verbonden bent. 
  </li>

  <li>
    Verander nu in Adafruit IO de kleur, dat zie je terug in de Serial monitor.
  </li>

  <li>
    Is je ledstrip ook goed aangesloten, dan kun je met de colorpicker de LED kleur aanpassen. Je hebt dus zelf een Philips (Signify) HUE gemaakt. Voor een paar euro. Adafruit draait ook op je mobiel!
  </li>
</ol>
<img width="326" alt="step7" src="."> <br>
