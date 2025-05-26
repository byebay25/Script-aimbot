# Delta Force Android Aimbot Config Example

This is a simple example project showing how to store an aimbot configuration JSON file for a Delta Force Android game mod, and how to read and parse it in an Android app using Java.

## Project Structure

- `app/src/main/assets/aimbot_config.json`  
  The JSON configuration file for the aimbot.

- `app/src/main/java/com/example/aimbot/ConfigLoader.java`  
  Java class for loading and parsing the config file from assets.

## How to Use

1. Place the JSON config file inside `assets` folder in your Android project.

2. Use the `ConfigLoader` class to read and parse the JSON config:
```java
ConfigLoader loader = new ConfigLoader(getApplicationContext());
JSONObject config = loader.loadConfig();
if (config != null) {
    boolean enabled = config.optBoolean("aimbot_enabled", false);
    double aimSpeed = config.optDouble("aim_speed", 1.0);
    System.out.println("Aimbot enabled: " + enabled);
    System.out.println("Aim speed: " + aimSpeed);
}
