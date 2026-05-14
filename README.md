# Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi   

## 15.05.2026 - İstanbul Medeniyet Üniversitesi - Üsküdar / İstanbul

![alternatif metin](https://github.com/acetinkaya/Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi/blob/main/medeniyet_egitim.jpeg)

🚀 İstanbul Medeniyet Üniversitesi bünyesinde gerçekleştirilen “Mikrodenetleyici ve Nesnelerin İnterneti (IoT) Eğitimi” kapsamında uygulamalı atölye eğitimi sürecinde teknik eğitmen olarak yer almaktayım.

Bu eğitim sürecinde katılımcılarla birlikte;

🔹 ESP32 ve Arduino tabanlı mikrodenetleyici sistemleri   
🔹 Sensör teknolojileri ve veri toplama süreçleri   
🔹 IoT (Internet of Things) mimarisi   
🔹 Gerçek zamanlı sıcaklık ve nem izleme uygulamaları   
🔹 İnternet tabanlı veri haberleşmesi   
🔹 Servo motor, potansiyometre ve temel otomasyon sistemleri   
🔹 Uygulamalı proje geliştirme süreçleri   

üzerine teorik ve uygulamalı çalışmalar gerçekleştireceğiz.

Atölye kapsamında özellikle;

📌 sensörlerden veri okuma,  
📌 verilerin internet ortamına aktarılması,  
📌 gerçek zamanlı IoT sistemlerinin geliştirilmesi,  
📌 mikrodenetleyici tabanlı otomasyon uygulamaları  

üzerine uygulamalı çalışmalar yapılacaktır.

Eğitim sonunda ise mini hackathon yapısıyla öğrencilerin kendi sistemlerini geliştirerek hızlı prototipleme süreçlerini deneyimlemeleri hedeflenmektedir.

Teknoloji, algoritma geliştirme, gömülü sistemler ve otonom teknolojiler alanında üretmeye devam ediyoruz 🚀

#IoT #ESP32 #Arduino #Mikrodenetleyici #EmbeddedSystems #InternetOfThings #YapayZeka #Robotik #OtonomSistemler #Teknoloji #Eğitim #DanışmanlıÖğrenme #Hackathon #İstanbulMedeniyetÜniversitesi

----

# 1. BÖLÜM — IoT ve ESP32’ye Giriş

![alternatif metin](https://github.com/acetinkaya/Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi/blob/main/esp-danismanliogrenme-kart2.png)

![alternatif metin](https://github.com/acetinkaya/Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi/blob/main/esp_blok_diyagram.png)   
ESP32 Datasheet --> https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf

# 2. BÖLÜM — Arduino IDE Kurulumu ve ESP32 Aktivasyonu   
   2.1. ESP32 Board Manager URL: https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json   
   2.2. Board --> ESP32 Dev Module   
   2.3. Port Seçimi --> COM(....)   

# 3. BÖLÜM - İlk Test Kodu - Seri Port

         void setup()   
         {   
         Serial.begin(115200);   
         }
   
         void loop()   
         {  
         Serial.println("ESP32 Calisiyor");   
         delay(1000);   
         }

# 4. BÖLÜM - İkinci Test Kodu - Led

         #define LED 2
   
         void setup()
         {
           pinMode(LED, OUTPUT);
         }
   
         void loop()
         {
           digitalWrite(LED, HIGH);
           delay(1000);
           digitalWrite(LED, LOW);
           delay(1000);
         }

# 5. BÖLÜM - Üçüncü Test Kodu - DHT11 Isı Nem Sensörü

         #include "DHT.h"
         #define DHTPIN 4
         #define DHTTYPE DHT11
         
         DHT dht(DHTPIN, DHTTYPE);
         
         void setup() 
         {
           Serial.begin(115200);
           dht.begin();
         }
         
         void loop() 
         {
           float sicaklik = dht.readTemperature();
           float nem = dht.readHumidity();
           Serial.print("Sicaklik: ");
           Serial.print(sicaklik);
           Serial.print(" Nem: ");
           Serial.println(nem);
           delay(2000);
         }
   
# 6. BÖLÜM - Dördüncü Test Kodu - IoT Veriyi İnternet Ortamına Aktarma

Bu kısmın gercekleştirilmesi için https://thingspeak.mathworks.com/ sayfasına üyelik yapılması gerekmektedir. Öğrenci mail adresleri veya şahsi mail adresiniz ile ücretsiz deneme için üyelik yapabilirsiniz. 

<table align="center">
  <!-- 1. SATIR / 3 GÖRSEL -->
  <tr>
    <td align="center">
      <img src="https://raw.githubusercontent.com/acetinkaya/Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi/main/ThingSpeak-sistemi-1.png" width="220"><br>
      Şema 1. ThingSpeak Sayfası (https://thingspeak.mathworks.com/)
    </td>
    <td align="center">
      <img src="https://raw.githubusercontent.com/acetinkaya/Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi/main/ThingSpeak-sistemi-2.png" width="220"><br>
      Şema 2. Mail adresi ile üyelik oluşturma kısmı
    </td>
    <td align="center">
      <img src="https://raw.githubusercontent.com/acetinkaya/Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi/main/ThingSpeak-sistemi-3.png" width="220"><br>
      Şema 3. Üyelik şifre oluşturma kısmı
    </td>
  </tr>

  <!-- 2. SATIR / 2 GÖRSEL -->
  <tr>
    <td align="center" colspan="1">
      <img src="https://raw.githubusercontent.com/acetinkaya/Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi/main/ThingSpeak-sistemi-4.png" width="330"><br>
      Şema 4. Üyelik mail adresi doğrulaması
    </td>
    <td align="center" colspan="2">
      <img src="https://raw.githubusercontent.com/acetinkaya/Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi/main/ThingSpeak-sistemi-5.png" width="330"><br>
      Şema 5. Üyelik detay bilgileri
    </td>
  </tr>

  <!-- 3. SATIR / 1 GÖRSEL -->
  <tr>
    <td align="center" colspan="3">
      <img src="https://raw.githubusercontent.com/acetinkaya/Mikrodenetleyici-ve-nesnelerin-interneti-IOT-egitimi/main/ThingSpeak-sistemi-6.png" width="660"><br>
      Şema 6. Üyelik işleminin tamamlanmış hali
    </td>
  </tr>

</table>



