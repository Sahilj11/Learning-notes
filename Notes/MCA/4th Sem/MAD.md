# UNIT 1
## Android
### Android Architecture

#### 📱 **Android Architecture (Layers)**

Android is a **software stack** divided into **four main layers**. Each layer provides specific functionality and serves the layer above it.

1. ✅ **Applications**

- These are the top-level apps like:
    
    - Phone, Contacts, Messages, Camera, etc.
        
- Built using Java/Kotlin and run within the **Android runtime**.
    
- End-user directly interacts with this layer.
    

---

 2. ✅ **Application Framework**

- Provides APIs for building apps.
    
- Helps developers access system services.
    
- **Key components:**
    
    - `ActivityManager` – Manages activity lifecycle.
        
    - `ContentProviders` – Data sharing between apps.
        
    - `ResourceManager` – Manages app resources (layouts, strings).
        
    - `View System` – UI building blocks (buttons, text views).
        
    - `NotificationManager` – Status bar alerts.
        

---

3. ✅ **Android Runtime (ART) + Core Libraries**
Android runtime layer is consisting of core java libraries and Dalvik virtual machine. Dalvik
virtual machine is just like JVM of java which help in running the applications on android device. The
Dalvik VM also enables every android apps as a separate space to run in its own process of DVM
        
- **Core Libraries:**
    
    - Provides Java classes (collections, I/O, etc.) to app developers.
        

---

4. ✅ **Native Libraries (Platform Libraries)**

- Written in C/C++ and used via Java through JNI (Java Native Interface).
    
- Examples:
    
    - `Surface Manager` – Handles display.
        
    - `OpenGL | ES` – 3D graphics rendering.
        
    - `Media Framework` – Audio/video codecs.
        
    - `SQLite` – Lightweight embedded database.
        
    - `WebKit` – Web browser engine.
        

---

5. ✅ **Linux Kernel**

- Base of the Android architecture.
    
- Provides:
    
    - **Hardware abstraction**
        
    - **Memory & process management**
        
    - **Security** (permissions, user management)
        
    - **Device drivers** (camera, audio, display, etc.)
        
- Acts as a bridge between the hardware and the rest of the stack.

 📊 Summary Diagram (Top to Bottom):

```
Applications
↓
Application Framework
↓
Android Runtime + Core Libraries
↓
Platform (Native) Libraries
↓
Linux Kernel
```

## Blackberry OS

### 🔹 Overview:

- **Developer:** Research In Motion (RIM)
    
- **Device Support:** Exclusive to BlackBerry phones (Bold, Curve, Pearl, Storm series)
    
- **Type:** Proprietary mobile operating system
    
- **Key Feature:** Strong **push email support** using **BlackBerry Enterprise Server (BES)**
    

---

### 🔹 Technical Highlights:

- **Email Services:** Supports Microsoft Exchange, Lotus Domino, Novell GroupWise via BES
    
- **App Development:**
    
    - Uses **Java ME (Micro Edition)** for native apps
        
    - Introduced **BlackBerry Web SDK** (2010) to build apps using HTML, CSS, JavaScript
        

---

### 🔹 RIM Mobile Fusion (2011):

- A **web-based console** for IT admins to manage multiple devices
    
- Features:
    
    - Enable email/contact access remotely
        
    - Manage lost devices
        
    - Enforce security policies
        
    - Push notifications
        

---

Let me know if you'd like this turned into a printable PDF or visual chart!

### 1. 📦 **Java Application Manager (JAM)**

- **Role:** Manages the lifecycle of network-downloaded apps.
    
- **Functions:** Install, launch, inspect, uninstall apps.
    
- **Challenge:** Mobile OS has limited resources (may lack file systems).
    
- **Note:** Key for handling dynamic app management on BlackBerry devices.
    

---

### 2. 📡 **HAL and Radio (Hardware Abstraction Layer)**

- **Purpose:** Interfaces with **Software Defined Radio (SDR)**.
    
- **Functions:**
    
    - Transfers data between hardware and software components (e.g., waveform FPGA).
        
    - Reduces cost by separating **core** and **custom modules**.
        
- **Importance:** Simplifies radio hardware development across different platforms.
    

---

### 3. 🎀 **Ribbon**

- **Role:** Acts as an **application launcher** for BlackBerry apps.
    
- **Function:**
    
    - Recognizes each app via its icon.
        
    - Sends a message to the app upon successful launch.
        
- **Feature:** Offers dynamic app execution and basic app lifecycle management.
    

---

### 4. 🧰 **Lower Layer Services (API Layer)**

Provides core mobile functionalities:

- 📩 **Messaging API**: Sends and handles messages step-by-step.
    
- 📞 **Phone API**: Supports call/dial-out features.
    
- 📒 **Address Book API**: Manages contacts and user data.
    
- 📝 **Memo API**: Activates emulator to test apps under development.
    

---

### 📌 Summary Table

|Layer|Key Function|
|---|---|
|Java Application Manager|Manage lifecycle of downloaded apps|
|HAL & Radio|Hardware control via SDR|
|Ribbon|App launcher using icons|
|Lower Layer Services|Core APIs: Messaging, Phone, Contacts, Memo|
## Firefox OS

Firefox OS was designed to provide a complete community-based alternative operating system, for running web applications directly or those
installed from an application marketplace. The applications use open standards and approaches such as JavaScript and HTML-5. Firefox OS was
publicly demonstrated in February 2012, on Android-compatible smartphones By December 16, 2014, fourteen operators in 28 countries
throughout the world offered Firefox OS phones.

### Layers
**Gonk Layer**  
This is the base layer of Firefox OS. It combines the Linux kernel and Android hardware abstraction libraries. It includes user-space drivers and libraries such as GPS, camera, and Bluetooth (using open-source projects like libusb and bluez). It also includes the Radio Interface Layer (RIL) to communicate with modem hardware. Gonk provides low-level services to higher layers.

**Gecko Runtime**  
This is the web engine that powers the Firefox browser and acts as the middle layer in Firefox OS. It supports internet standards like HTML, CSS, JavaScript, and XML. Gecko also provides a programming interface for apps and is responsible for rendering, networking, and media services.

**Gaia**  
Gaia is the user interface layer (topmost layer). It includes everything the user sees and interacts with—home screen, lock screen, default apps (like dialer, messaging, camera). All Gaia components are built using web technologies (HTML, CSS, JavaScript). Developers can modify Gaia since it's open source and available on GitHub.

**Firefox OS Applications**  
Apps are built using web technologies and can be downloaded from the Firefox Marketplace. These run on Gaia and interact with the device through Web APIs provided by Gecko.

**Mobile Hardware**  
This refers to device components like battery, sensors, camera, GPS, Bluetooth, etc., which interact with the OS via the Gonk and Gecko layers.

## ARM vs MIPS
| Feature                          | MIPS Architecture                                               | ARM Architecture                                                                 |
| -------------------------------- | --------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **Type**                         | RISC (Reduced Instruction Set Computing)                        | RISC (Reduced Instruction Set Computing)                                         |
| **Usage**                        | Smartphones, embedded systems, supercomputers, Sony PlayStation | Smartphones, tablets, embedded systems                                           |
| **Year of Invention**            | 1981                                                            | 1985                                                                             |
| **Instruction Set**              | Fixed-size instructions                                         | Fixed-size instructions                                                          |
| **Number of Registers**          | 32 general-purpose registers                                    | 16 general-purpose registers                                                     |
| **Multiply Operation Registers** | Has special registers to hold multiply results                  | Uses general-purpose registers for all operations                                |
| **Data Bus Support**             | Typically 32-bit                                                | Supports 64-bit data buses                                                       |
| **Memory Addressing**            | Byte addressing                                                 | Byte addressing                                                                  |
| **Addressing Modes**             | 3 modes: Register, Immediate, Displacement                      | Similar, but also supports multiple advanced addressing modes in latest versions |
| **Performance**                  | Moderate                                                        | Higher efficiency (better performance)                                           |
## Challenges of Mobile Platform

1. **Interactive Apps**
    - Should use built-in sensors and provide smooth data processing for better user engagement.
        
2. **Involving End User**
    
    - User feedback during design helps improve popularity and usability.
        
3. **Keeping App Simple**
    
    - UI should be intuitive with clear instructions, tutorials, and structured guidelines.
        
4. **Power Consumption & Performance**
    
    - Optimize app to use fewer resources and release them when idle to save battery.
        
5. **Marketing the App**
    
    - Success depends heavily (80-90%) on marketing; development is only a small part.
        
6. **Choosing Development Technology**
    
    - Decide between **native**, **hybrid**, or **cross-platform** based on app needs.
        
7. **World-Class Application**
    
    - Create unique apps with intuitive design, key features, and appealing graphics.
        
8. **Cross-Platform Compatibility**
    
    - Apps should run on multiple OS/devices due to varied user base.
        
9. **User-Friendly Features**
    
    - Use attractive design, color schemes, and familiar features to improve user experience.
        
10. **Security**
    

- Prevent unauthorized access and malware; ensure app is secure and private.
    
## Manifest.XML

### 📄 **AndroidManifest.xml Overview**

- Essential XML file located in the **root directory** of every Android application.
    
- Declares all key components: **Activities, Services, Broadcast Receivers, Content Providers**.
    
- Ensures **security**, managing which app parts are accessible to others.
    

---

### 🔹 **Functions of AndroidManifest.xml**

- Protects application components by enforcing permission rules.
    
- Declares the Android **APIs** used in the app.
    
- Lists **documentation classes** (profiling/debug info removed before publishing).
    
- Defines app structure and behavior for the Android system.
    

### 🔹 **Compilation Process (From Source to APK)**

|File/Tool|Role|
|---|---|
|`.java` file|Java source code|
|`javac`|Compiles `.java` → `.class`|
|`dx`|Converts `.class` → `.dex` (Dalvik bytecode)|
|`aapt`|Packages resources and manifest into `.apk`|
|`.apk` file|Final installable Android application|

---

### 🔹 **Key Elements in AndroidManifest.xml**

1. **`<manifest>`**
    
    - **Root** element.
        
    - Contains the app’s **package name**.
        
2. **`<application>`**
    
    - Declares app-wide settings like:
        
        - `android:icon` → App icon.
            
        - `android:label` → Default name shown to users.
            
        - `android:theme` → Theme for all activities.
            
3. **`<activity>`**
    
    - Declares each screen (Activity) in the app.
        
    - Attributes include:
        
        - `android:name` → Class name of activity.
            
        - `android:label` → Title of the activity.
            
        - `android:theme`, `launchMode` etc.
            
4. **`<intent-filter>`**
    
    - Specifies how the component handles **intents** (e.g., app launches).
        
    - Must contain:
        
        - **`<action>`**: Type of action it handles.
            
        - **`<category>`**: Category like `android.intent.category.LAUNCHER`.
            
```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.myfirstapp">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="My First App"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.MyFirstApp">
        
        <activity android:name=".MainActivity"
            android:label="Home">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

    </application>

</manifest>
```

## Software Stack
![](../../statics/Pasted%20image%2020250505065438.png)

## 📁 1. **`R.java` File**

- The `R.java` file is **auto-generated** by Android's build system.
    
- It contains **resource IDs** for all your XML resources (layouts, strings, drawables, etc.).
    
- You don’t create or modify it directly.
    

📌 Example:  
If you have a layout file: `res/layout/activity_main.xml`  
You access it in code like this:

```java
setContentView(R.layout.activity_main);
```

If you have a string resource: `res/values/strings.xml`

```xml
<string name="app_name">My App</string>
```

Access it in code:

```java
getString(R.string.app_name);
```

---

## 🚫 2. **Hide Title Bar (AppCompat / Fullscreen)**

To hide the title bar from an **Activity**, there are several ways:

#### a) **Programmatically (before setContentView):**

```java
requestWindowFeature(Window.FEATURE_NO_TITLE);
getSupportActionBar().hide(); // If using AppCompat
```

#### b) **In the Manifest:**

```xml
<activity android:name=".MainActivity"
    android:theme="@style/Theme.AppCompat.Light.NoActionBar" />
```

#### c) **For Fullscreen (no status bar or title):**

```java
getWindow().setFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN,
                     WindowManager.LayoutParams.FLAG_FULLSCREEN);
```

Or in the Manifest:

```xml
<activity android:name=".MainActivity"
    android:theme="@android:style/Theme.NoTitleBar.Fullscreen" />
```

---

## 🔄 3. **Screen Orientation**

To lock the screen orientation (e.g., portrait or landscape):

#### a) **In Manifest:**

```xml
<activity android:name=".MainActivity"
    android:screenOrientation="portrait" />
```

Other values:

- `landscape`
    
- `sensor`
    
- `unspecified`
    
- `user`
    

#### b) **Programmatically:**

```java
setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_PORTRAIT);
```

# UNIT 2

Here’s a concise guide to common Android **UI widgets**, including **descriptions**, **XML**, and **Java code** for each:

---

### ✅ 1. **Button**

**Description:** A simple clickable element that performs an action.

```xml
<Button android:id="@+id/myButton" android:text="Click Me" ... />
```

```java
Button btn = findViewById(R.id.myButton);
btn.setOnClickListener(v -> Toast.makeText(this, "Clicked", Toast.LENGTH_SHORT).show());
```

---

### ✅ 2. **Toast & Custom Toast**

**Description:** Small popup messages shown for a short time.

```java
Toast.makeText(this, "Simple Toast", Toast.LENGTH_SHORT).show();
```

**Custom Toast:**

```java
View view = getLayoutInflater().inflate(R.layout.custom_toast, null);
Toast toast = new Toast(this);
toast.setView(view);
toast.show();
```

---

### ✅ 3. **ToggleButton**

**Description:** A button with two states — ON and OFF.

```xml
<ToggleButton android:id="@+id/toggleButton" ... />
```

```java
toggle.setOnCheckedChangeListener((b, isChecked) -> {...});
```

---

### ✅ 4. **Switch**

**Description:** A modern switch with ON/OFF functionality (used in settings).

```xml
<Switch android:id="@+id/switch1" ... />
```

```java
switch1.setOnCheckedChangeListener(...);
```

---

### ✅ 5. **ImageButton**

**Description:** A button that displays an image instead of text.

```xml
<ImageButton android:src="@drawable/ic_launcher" ... />
```

```java
imageButton.setOnClickListener(...);
```

---

### ✅ 6. **CheckBox**

**Description:** A checkbox to select multiple options independently.

```xml
<CheckBox android:id="@+id/checkbox" ... />
```

```java
checkBox.setOnCheckedChangeListener(...);
```

---

### ✅ 7. **AlertDialog**

**Description:** A popup dialog to show alerts or ask confirmation.

```java
new AlertDialog.Builder(this)
    .setTitle("Confirm")
    .setMessage("Are you sure?")
    .setPositiveButton("Yes", null)
    .setNegativeButton("No", null)
    .show();
```

---

### ✅ 8. **Spinner**

**Description:** A dropdown list to select one item.

```xml
<Spinner android:id="@+id/spinner" ... />
```

```java
spinner.setAdapter(new ArrayAdapter<>(...));
```

---

### ✅ 9. **AutoCompleteTextView**

**Description:** Text field that shows suggestions while typing.

```xml
<AutoCompleteTextView android:id="@+id/autoText" ... />
```

```java
autoText.setAdapter(new ArrayAdapter<>(...));
```

---

### ✅ 10. **RatingBar**

**Description:** Allows the user to give a star rating.

```xml
<RatingBar android:id="@+id/ratingBar" ... />
```

```java
ratingBar.setOnRatingBarChangeListener(...);
```

---

### ✅ 11. **DatePicker**

**Description:** Dialog for selecting a date.

```java
new DatePickerDialog(this, (view, y, m, d) -> {...}, 2024, 0, 1).show();
```

---

### ✅ 12. **TimePicker**

**Description:** Dialog for selecting a time.

```java
new TimePickerDialog(this, (v, h, m) -> {...}, 12, 0, true).show();
```

---

### ✅ 13. **ProgressBar**

**Description:** Visual indicator for progress or loading.

```xml
<ProgressBar android:id="@+id/progressBar" ... />
```

```java
progressBar.setVisibility(View.VISIBLE);
```

---

### ✅ 14. **QuickContactBadge**

**Description:** Displays a thumbnail image with a quick contact access.

```xml
<QuickContactBadge android:id="@+id/contactBadge" ... />
```

```java
badge.assignContactUri(Uri.parse("content://contacts/people/1"));
```

---

### ✅ 15. **AnalogClock & DigitalClock**

**Description:** Display analog or digital time (deprecated in newer versions).

```xml
<AnalogClock ... />
<DigitalClock ... />
```

---

### ✅ 16. **Hardware Button (Back Button)**

**Description:** Override physical Back button behavior.

```java
@Override
public void onBackPressed() {
    Toast.makeText(this, "Back pressed!", Toast.LENGTH_SHORT).show();
}
```

---

### ✅ 17. **File Download (DownloadManager)**

**Description:** Downloads files in background and shows in notification.

```java
DownloadManager dm = (DownloadManager) getSystemService(DOWNLOAD_SERVICE);
Uri uri = Uri.parse("https://example.com/file.pdf");
DownloadManager.Request req = new DownloadManager.Request(uri);
req.setNotificationVisibility(DownloadManager.Request.VISIBILITY_VISIBLE_NOTIFY_COMPLETED);
dm.enqueue(req);
```

---

Would you like me to generate this into a **PDF notes file** for easy download and printing?