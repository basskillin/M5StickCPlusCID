#include <M5StickCPlus.h>
#include <WiFi.h>
#include <WebServer.h>

const char* ssid = "your_ssid";
const char* password = "your_password";

WebServer server(80);

void handleRoot() {
  if (server.hasArg("CLID") && server.hasArg("thenumber")) {
    String callerID = server.arg("CLID");
    String callerNumber = server.arg("thenumber");
    
    M5.Lcd.fillScreen(BLACK);
    M5.Lcd.setCursor(0, 20); // Adjusted for M5StickC Plus resolution
    M5.Lcd.setTextColor(WHITE);
    M5.Lcd.setTextSize(3); // Adjusted text size for better readability
    M5.Lcd.printf("Caller ID:\n%s\n", callerID.c_str());
    M5.Lcd.printf("Number:\n%s", callerNumber.c_str());
    
    server.send(200, "text/plain", "Caller ID received");
  } else {
    server.send(400, "text/plain", "Missing parameters");
  }
}

void setup() {
  M5.begin();
  M5.Lcd.setRotation(1);
  M5.Lcd.fillScreen(BLACK);
  M5.Lcd.setTextColor(WHITE);
  M5.Lcd.setTextSize(3);
  
  WiFi.begin(ssid, password);
  while (WiFi.status() != WL_CONNECTED) {
    delay(1000);
    Serial.println("Connecting to WiFi...");
  }
  Serial.println("Connected to WiFi");

  server.on("/", handleRoot);
  server.begin();
}

void loop() {
  server.handleClient();
}
