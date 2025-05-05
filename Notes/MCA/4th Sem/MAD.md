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

# UNIT 3
## Activity

### 📱 **Activity in Android**

- **Activity** is one of the most important components of any Android application.
    
- **Activities** represent the **User Interface (UI) screens** that the user interacts with.
    
- It is similar to the `main()` function in other programming languages — it acts as the **main entry point** for user interaction.
    
- An app can have **multiple activities**, such as a login screen, home screen, settings screen, etc.
    
- All activities must be **declared in the `AndroidManifest.xml`** file, with appropriate attributes (like intent filters, launch mode, etc.).
    

---

### 🔁 **Activity Lifecycle Methods**

Each Activity goes through a set of lifecycle stages. These are:

1. **`onCreate()`** – Called when the activity is first created.
    
2. **`onStart()`** – Called when the activity becomes visible to the user.
    
3. **`onResume()`** – Called when the activity starts interacting with the user.
    
4. **`onPause()`** – Called when another activity is taking focus (but this activity is still partially visible).
    
5. **`onStop()`** – Called when the activity is no longer visible to the user.
    
6. **`onRestart()`** – Called when the activity is coming back to the foreground after being stopped.
    
7. **`onDestroy()`** – Called when the activity is about to be destroyed.
![](../../statics/Pasted%20image%2020250505083409.png)

## Fragment

## 🧩 **Fragments in Android**

### 📌 **Definition**

- A **Fragment** is a reusable portion of the user interface in an Android activity.
    
- Fragments **represent a behavior or a part of the user interface** in an activity.
    
- A fragment **must always be embedded in an activity**, and it cannot live on its own.
    
- Even though it’s hosted inside an activity, it has its **own lifecycle**, closely related to the activity’s lifecycle.
    

---

### 🧠 **Why Use Fragments?**

- Due to various **screen sizes** (phones, tablets, TVs), it’s difficult to manage UIs for each device.
    
- Fragments help build **responsive UIs** by letting you **combine, reuse, and adjust UI components dynamically**.
    

---

### 🔄 **Fragment Lifecycle (Key Methods)**
Sure! Here's an explanation of each **Fragment Lifecycle method** without the code:

---

### 1️⃣ **`onAttach()`**

- **Description**: This method is called when the fragment is **first associated** with its host activity. It's the first lifecycle method in the fragment's lifecycle.
    
- **When it happens**: This happens only once, right after the fragment is added to the activity.
    
- **Usage**: You can use this method to initialize or set up data or objects that need access to the host activity (e.g., communication between the fragment and the activity).
    

---

### 2️⃣ **`onCreate()`**

- **Description**: This method is called when the fragment is **created**.
    
- **When it happens**: It's called after `onAttach()` and before `onCreateView()`.
    
- **Usage**: You can perform initializations, like retrieving arguments, setting up resources, or initializing variables that should only be set once.
    

---

### 3️⃣ **`onCreateView()`**

- **Description**: This method is responsible for **inflating the fragment's layout**, which is essentially creating the UI.
    
- **When it happens**: It's called when the fragment's view needs to be created, right before the fragment's UI is displayed.
    
- **Usage**: Typically, this method inflates the XML layout file and sets it as the fragment's content view.
    

---

### 4️⃣ **`onActivityCreated()`**

- **Description**: Called when the **host activity’s `onCreate()` method** has finished, and the activity’s view is ready.
    
- **When it happens**: This is called after the fragment's view has been created and the activity's view hierarchy is set up.
    
- **Usage**: This is used to perform any additional setup that requires both the activity and fragment's views to be available.
    

---

### 5️⃣ **`onStart()`**

- **Description**: This method is called when the fragment becomes **visible** to the user but isn’t yet interactive.
    
- **When it happens**: It’s called after `onCreateView()` and before `onResume()`.
    
- **Usage**: You can use this method to start animations, register listeners, or initialize any resources that should be active when the fragment is visible.
    

---

### 6️⃣ **`onResume()`**

- **Description**: This method is called when the fragment is in the **foreground** and ready for user interaction.
    
- **When it happens**: It’s called after `onStart()`.
    
- **Usage**: This is where you can resume tasks such as network requests, start animations, or refresh UI elements that are active and visible.
    

---

### 7️⃣ **`onPause()`**

- **Description**: This method is called when the fragment is no longer **actively interacting** with the user but is still visible.
    
- **When it happens**: It is called before `onStop()` when the fragment is about to be hidden.
    
- **Usage**: Typically used to **pause ongoing tasks**, save data, or stop animations that should not continue when the fragment is not in focus.
    

---

### 8️⃣ **`onStop()`**

- **Description**: This method is called when the fragment is no longer **visible** to the user.
    
- **When it happens**: It happens after `onPause()` when the fragment is completely off-screen.
    
- **Usage**: You should release resources, unregister listeners, or save persistent state in this method.
    

---

### 9️⃣ **`onDestroyView()`**

- **Description**: This method is called when the **fragment's view** is about to be destroyed.
    
- **When it happens**: It is called before the fragment is fully destroyed, and it gives you a chance to clean up the fragment’s view-related resources.
    
- **Usage**: Use this to release references to views, stop animations, or clean up view-related resources that are no longer needed.
    

---

### 🔟 **`onDestroy()`**

- **Description**: This method is called when the **fragment is being destroyed**.
    
- **When it happens**: It happens after `onDestroyView()` and before the fragment is fully removed from memory.
    
- **Usage**: You can clean up any remaining resources, finalize operations, or remove any references in this method.
    

---

### 1️⃣1️⃣ **`onDetach()`**

- **Description**: This method is called when the fragment is **detached** from its host activity.
    
- **When it happens**: It’s called when the fragment is no longer connected to the activity and after the fragment’s `onDestroy()` has been called.
    
- **Usage**: You can use this method to perform any final cleanup related to the activity or any lingering resources associated with the fragment.

### 📚 **Types of Fragments**

- **DialogFragment** – Used to show a dialog window floating on top of the activity.
    
- **ListFragment** – Displays a list of items in a fragment.
    
- **PreferenceFragment** – Manages application preferences using UI from XML.
    

---

### 🔧 **Core Fragment Classes**

|Class|Description|
|---|---|
|`FragmentActivity`|Base class for activities that use fragments.|
|`Fragment`|Base class for all fragment components.|
|`FragmentManager`|Manages fragment operations inside an activity.|
|`FragmentTransaction`|Used to perform operations like **add**, **replace**, **remove** fragments.|

---

### ⭐ **Advantages of Fragments**

1. **Reusability** – Reuse the same UI and logic in multiple activities.
    
2. **Modularity** – Design small components instead of large activities.
    
3. **Support for Multiple Screens** – Adjust layout for phone, tablet, TV, or orientation.
    
4. **Better Lifecycle Management** – Fragments manage their own lifecycle in coordination with the parent activity.
    

---

### 📱 **Real-World Use Cases**

- **Responsive layouts** (e.g., two-pane mode in tablets).
    
- **Dynamic UI updates** (e.g., loading different fragments on button click).
    
- **Reusing components** (e.g., a product list fragment used in multiple screens).
    
- **Dialog boxes**, **settings screens**, etc.

### Fragment Example

#### **Fragment XML Layout (fragment_my.xml)**

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    
    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello from My Fragment!" />
</LinearLayout>
```

#### **Activity Class (MainActivity.java)**

```java
public class MainActivity extends AppCompatActivity {
    
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Add the fragment dynamically
        if (savedInstanceState == null) {
            FragmentTransaction transaction = getSupportFragmentManager().beginTransaction();
            transaction.replace(R.id.fragment_container, new MyFragment());
            transaction.commit();
        }
    }
}
```

#### **Activity Layout (activity_main.xml)**

```xml
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/fragment_container"
    android:layout_width="match_parent"
    android:layout_height="match_parent" />
```

---

### Dynamic Fragment

A **Dynamic Fragment** is a fragment that is added, replaced, or removed during runtime. This allows for more flexibility, especially in cases where you need to change the UI based on user actions or device configurations.

The key here is that fragments are managed using a `FragmentTransaction` to dynamically manipulate fragments in the activity.

#### **Note**:

- **FragmentTransaction**: This is used to perform the actual fragment changes, like adding, replacing, or removing fragments.
    
- **Back Stack**: By using `addToBackStack()`, you allow the user to press the back button and navigate back to the previous fragment.
    

### Advantages of Dynamic Fragments:

1. **UI Flexibility**: You can change the UI at runtime based on the user's interactions or device configuration.
    
2. **Reusable Components**: You can reuse fragments across multiple activities, making it easier to maintain and update the UI.
    
3. **Efficient Memory Use**: You can load fragments only when needed, saving memory and improving performance.


## Intent

### ✅ **1. Sending Intent from FirstActivity.java**
```java
// FirstActivity.java
Intent intent = new Intent(FirstActivity.this, SecondActivity.class);
intent.putExtra("username", "JohnDoe");  // Passing data with key "username"
startActivity(intent);
```

### ✅ **2. Receiving Intent in SecondActivity.java**

```java
// SecondActivity.java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_second);

    // Receiving data
    Intent intent = getIntent();
    String receivedUsername = intent.getStringExtra("username");

    TextView textView = findViewById(R.id.textView);
    textView.setText("Welcome, " + receivedUsername);
}
```

### ✅ **3. Layout file for SecondActivity (activity_second.xml)**

```xml
<!-- res/layout/activity_second.xml -->
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center">

    <TextView
        android:id="@+id/textView"
        android:textSize="20sp"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />
</LinearLayout>
```

---

Would you like an example with `startActivityForResult()` and result passing as well?
Intent is one of the most important and most used app components of an android application. 

Using Intents, you can call to other app components or to other activity or also call other applications on your mobile phone. 

It is used to passing information from one activity to another activity that means it is data carrier through object.

### ✅ **Definition**

- `Intent` is one of the **most essential components** in Android used to start **activities**, **services**, or **broadcast receivers**.
    
- It is a **messaging object** that facilitates communication between **components**.
    
- It can be used to:
    
    - Start a new **Activity**.
        
    - Start a **Service**.
        
    - Deliver a **Broadcast**.
        
    - Interact with other applications (like Camera, Email, Browser, etc.).
        
- It can also **carry data** between activities using key-value pairs via `putExtra()` and `getStringExtra()`.

## 🔄 **Types of Intents**

### 1. 📘 **Explicit Intent**

- Used when **calling a specific component**, such as starting a known Activity or Service in your own app.
    
- You **explicitly specify** the target component’s class name.
    

**Syntax:**

```java
Intent intent = new Intent(getApplicationContext(), SecondActivity.class);
startActivity(intent);
```

### 2. 🌐 **Implicit Intent**

- Used when the **target component is not specified explicitly**.
    
- Android will match the **action** with **registered components** (via Intent Filters in Manifest).
    
- Examples:
    
    - Open browser
        
    - Open dialer
        
    - Send email
        
    - Open map
        

**Syntax:**

```java
Intent intent = new Intent(Intent.ACTION_VIEW);
intent.setData(Uri.parse("https://www.google.com"));
startActivity(intent);
```

---

## 🔀 **Intent Use Case Example**

### 💡 Scenario:

- You have an app with **two activities**:
    
    - **FirstActivity** has a button.
        
    - On button click, it uses:
        
        - **Explicit Intent** to move to **SecondActivity**.
            
        - **SecondActivity** uses **two fragments**.
            
        - A **button in SecondActivity** opens a web page via an **Implicit Intent**.
            

### ✅ Steps Covered:

1. Start **SecondActivity** from **FirstActivity** using **Explicit Intent**.
    
2. Open a **web page** from **SecondActivity** using **Implicit Intent**.
    
3. Show **two fragments** in SecondActivity.
    

---

## 🎯 **Summary Points for Exam**

| Feature         | Description                                                                      |
| --------------- | -------------------------------------------------------------------------------- |
| Intent          | Android component to launch other components like Activities or Services.        |
| Data Carrier    | Carries data from one component to another using `putExtra()` and `getExtra()`   |
| Explicit Intent | Directly calls a component using class name.                                     |
| Implicit Intent | Declares a general action to be handled by any app that can perform it.          |
| Use Cases       | Start Activity, Open Browser, Make Call, Send Email, Share Data, etc.            |
| Intent Filters  | Used to declare what actions your app can respond to (in `AndroidManifest.xml`). |

## Android Menu

Menus in Android are an essential component of the **user interface**. They allow users to interact with the application and perform **actions directly** from a centralized location without navigating deeply into the app.

Menus are commonly used in apps to provide access to **commands**, **settings**, **actions**, or **features** in a structured and user-friendly way.

---

### 🧾 **Why Menus Are Important**

- Provide a **familiar UI experience** for users.
    
- Allow quick access to key features.
    
- Help maintain **clean layouts** by placing secondary actions outside of the main UI.
    
- Enhance user productivity and application navigation.
    

---

## 📑 **Types of Menus in Android**

Android supports **three main types** of menus, each used in different scenarios:

---

### 1️⃣ **Options Menu**

**Definition**:  
The **Options Menu** is the primary collection of menu items for an activity. It is typically displayed when the user taps on the **three vertical dots** in the top-right corner (overflow menu) or presses the **menu button** on older devices.

**Use Case**:  
Used for **global actions** like Settings, Search, About, Logout, etc., which are relevant across the whole activity or app.

**Key Method**:

- `onCreateOptionsMenu(Menu menu)` – to inflate the menu layout from XML.
    
- `onOptionsItemSelected(MenuItem item)` – to handle clicks on menu items.
    

**Menu XML Example**:

```xml
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:id="@+id/menu_settings"
          android:title="Settings"
          android:icon="@drawable/ic_settings"
          android:showAsAction="ifRoom" />
</menu>
```

---

### 2️⃣ **Context Menu**

**Definition**:  
The **Context Menu** appears when the user **long-presses** a specific view. It provides **contextual actions** relevant to the item being pressed.

**Use Case**:  
Useful in **list views**, images, or files where users can perform actions like Delete, Share, Edit, etc., on long-press.

**Key Methods**:
- `registerForContextMenu(View view)` – to register a view for the context menu.
- `onCreateContextMenu()` – to inflate context menu items.    
- `onContextItemSelected()` – to handle selected item actions.

### 3️⃣ **Popup Menu**

**Definition**:  
A **Popup Menu** is a **floating list** of menu items anchored to a particular view (e.g., a Button). It appears **below or beside the view** that triggers it.

**Use Case**:  
Used for actions related to a **specific UI element**, especially in **toolbar actions**, **filtering options**, or **drop-down commands**.

**Key Class**:

- `PopupMenu` class – used to show the popup menu programmatically.
    
- `setOnMenuItemClickListener()` – handles item click events.
    

**Advantages**:

- Lightweight
    
- Customizable
    
- Can be used on any view
    

---

## 🧠 Summary Table

|Menu Type|Triggered By|Best Use Case|UI Behavior|
|---|---|---|---|
|**Options Menu**|App bar or menu button|Global app-wide actions|Appears at top or overflow|
|**Context Menu**|Long-press on a view|Item-specific actions in lists/images|Floating on long-press|
|**Popup Menu**|Click on a view/button|Local actions (filters, settings)|Appears next to clicked view|

### 📝 Additional Notes:

- Menu items can be grouped, given icons, and placed conditionally.
    
- Menus improve **accessibility** and **intuitiveness**.
    
- You can dynamically add or remove items using Java/Kotlin.
    
- You can also use **SubMenus** for nested options in any menu.


## ✅ **1. Options Menu (Top-right Menu)**

### ➤ **Step 1: Create menu XML file**

**res/menu/menu_main.xml**

```xml
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/action_settings"
        android:title="Settings"
        android:icon="@drawable/ic_settings"
        android:showAsAction="ifRoom" />
</menu>
```

### ➤ **Step 2: Activity Java Code**

```java
@Override
public boolean onCreateOptionsMenu(Menu menu) {
    getMenuInflater().inflate(R.menu.menu_main, menu);
    return true;
}

@Override
public boolean onOptionsItemSelected(MenuItem item) {
    int id = item.getItemId();
    if (id == R.id.action_settings) {
        Toast.makeText(this, "Settings clicked", Toast.LENGTH_SHORT).show();
        return true;
    }
    return super.onOptionsItemSelected(item);
}
```

---

## ✅ **2. Context Menu (Long-Press Menu)**

### ➤ **Step 1: Register the view**

```java
TextView textView;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    textView = findViewById(R.id.textView);
    registerForContextMenu(textView);
}
```

### ➤ **Step 2: Override context menu methods**

```java
@Override
public void onCreateContextMenu(ContextMenu menu, View v, ContextMenu.ContextMenuInfo menuInfo) {
    super.onCreateContextMenu(menu, v, menuInfo);
    menu.setHeaderTitle("Choose Option");
    menu.add(0, v.getId(), 0, "Edit");
    menu.add(0, v.getId(), 0, "Delete");
}

@Override
public boolean onContextItemSelected(MenuItem item) {
    if (item.getTitle().equals("Edit")) {
        Toast.makeText(this, "Edit Clicked", Toast.LENGTH_SHORT).show();
    } else if (item.getTitle().equals("Delete")) {
        Toast.makeText(this, "Delete Clicked", Toast.LENGTH_SHORT).show();
    }
    return true;
}
```

---

## ✅ **3. Popup Menu (Anchored Menu on Button Click)**

### ➤ **Java Code in Activity**

```java
Button popupButton;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    popupButton = findViewById(R.id.popupButton);
    popupButton.setOnClickListener(v -> {
        PopupMenu menu = new PopupMenu(this, v);
        menu.getMenuInflater().inflate(R.menu.menu_main, menu.getMenu());
        menu.setOnMenuItemClickListener(item -> {
            Toast.makeText(this, "Clicked: " + item.getTitle(), Toast.LENGTH_SHORT).show();
            return true;
        });
        menu.show();
    });
}
```

```xml
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:id="@+id/action_settings"
          android:title="Settings" />
</menu>
```

### ➤ **layout XML (for popup menu example)**

```xml
<Button
    android:id="@+id/popupButton"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Show Popup Menu" />
```


## 📘 **RelativeLayout in Android**

### 🔹 **Definition:**

RelativeLayout is an XML-based layout manager in Android used to arrange child views in **relative positions** to **each other** or to the **parent layout**.

---

### 🔹 **Key Features:**

- Allows placing views **relative to siblings** (e.g., _left-of_, _below_, _right-of_).
    
- Allows placing views **relative to the parent layout** (e.g., _alignParentTop_, _centerInParent_).
    
- Helps avoid **deeply nested layouts**, improving **performance**.
    
- Ideal for **flat UI design** compared to multiple nested `LinearLayouts`.

### 🔹 **Advantages:**

- High-performance layout.
    
- Reduces view hierarchy depth.
    
- Suitable for **complex UI** that needs positioning flexibility.
    

---

### 🔹 **Common Use Case:**

When designing a screen that requires dynamic positioning of elements such as placing:

- A label above an input field,
    
- A button at the bottom center,
    
- A title centered at the top, etc.
    

---

### 🔹 **Common Attributes of RelativeLayout:**

| Attribute                  | Description                                  |
| -------------------------- | -------------------------------------------- |
| `layout_alignParentLeft`   | Aligns view to the left edge of the parent   |
| `layout_alignParentTop`    | Aligns view to the top edge of the parent    |
| `layout_alignParentRight`  | Aligns view to the right edge of the parent  |
| `layout_alignParentBottom` | Aligns view to the bottom edge of the parent |
| `layout_above`             | Places the view above another view           |
| `layout_below`             | Places the view below another view           |
## 📘 **TableLayout in Android**

### 🔹 **Definition:**

`TableLayout` is a **ViewGroup** in Android used to arrange child views in a **grid-like structure of rows and columns**. It does **not show** borders between cells or columns.

---

### 🔹 **Key Characteristics:**

- Arranges children **horizontally** in a row and **vertically** in multiple rows.
    
- Number of columns = maximum number of child views in any `TableRow`.
    
- Columns are **not explicitly declared**.
    
- Each **`<TableRow>`** represents one **row** in the table.
    
- Each **cell** can hold **only one view** (e.g., `TextView`, `EditText`, `ImageView`, etc.).
    
- **Borders** are not shown by default.
    

---

### 🔹 **Important Points:**

|Feature|Description|
|---|---|
|`TableRow`|Used to define each row inside a `TableLayout`.|
|Stretchable Columns|Columns can expand to occupy remaining space using `android:stretchColumns`.|
|Shrinkable Columns|Columns can shrink to fit within the screen using `android:shrinkColumns`.|
|Width Behavior|Width of children = **match_parent** (set by TableLayout).|
|Height Behavior|Height of children = **wrap_content** (can be specified per view).|

---

### 🔹 **When to Use:**

Use `TableLayout` when:

- You want to arrange data **in a tabular/grid format**.
    
- You need a **form-like UI** with input fields and labels.
    
- You are building simple spreadsheet-like interfaces.
    

---

### 🔹 **Example: Table Layout with 2 Rows and 3 Columns**

```xml
<TableLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:stretchColumns="1">

    <TableRow>
        <TextView
            android:text="Name"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content" />

        <EditText
            android:hint="Enter name"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content" />

        <Button
            android:text="Clear"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content" />
    </TableRow>

    <TableRow>
        <TextView
            android:text="Email"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content" />

        <EditText
            android:hint="Enter email"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content" />

        <Button
            android:text="Send"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content" />
    </TableRow>

</TableLayout>
```

---

### 🔹 **Common Attributes:**

|Attribute|Use|
|---|---|
|`android:stretchColumns`|Specify which columns should stretch to fill extra space (`0,1`)|
|`android:shrinkColumns`|Specify which columns should shrink when needed (`1,2`)|
|`android:collapseColumns`|Hide specific columns (`1`)|
Here are clean and detailed notes on **GridLayout in Android**:

---

## 📘 **GridLayout in Android**

### 🔹 **Definition:**

`GridLayout` is a **layout manager** in Android that places components in a **grid of cells**, similar to a **spreadsheet**. Each cell is defined by **row and column** indexes using `rowSpec` and `columnSpec`.

---

### 🔹 **Key Features:**

|Feature|Description|
|---|---|
|Grid-based Layout|Divides the screen into rectangular **rows and columns**.|
|Non-overlapping Cells|Components are placed in separate cells; **cells do not overlap**.|
|Custom Spacing|Margins (left, top, right, bottom) can control spacing between views.|
|Auto-Margins|`useDefaultMargins="true"` applies automatic margins to child views.|
|Control Placement|Use `layout_row`, `layout_column`, `layout_rowSpan`, and `layout_columnSpan` to place and span views.|

---

### 🔹 **Why Use GridLayout?**

- To organize UI in a **grid format**.
- Good for **calculator apps**, **dashboards**, **data entry forms**, etc.
- Offers **precise control** over view placement compared to Linear or Relative Layout.
### 🔹 **Example: 2x2 Grid with TextViews and Buttons**

```xml
<GridLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:columnCount="2"
    android:rowCount="2"
    android:useDefaultMargins="true"
    android:alignmentMode="alignMargins"
    android:padding="16dp">

    <TextView
        android:text="Name"
        android:layout_row="0"
        android:layout_column="0"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <EditText
        android:hint="Enter name"
        android:layout_row="0"
        android:layout_column="1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <TextView
        android:text="Email"
        android:layout_row="1"
        android:layout_column="0"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

    <EditText
        android:hint="Enter email"
        android:layout_row="1"
        android:layout_column="1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" />

</GridLayout>
```

---

### 🔹 **Common XML Attributes:**

| Attribute                   | Description                                                             |
| --------------------------- | ----------------------------------------------------------------------- |
| `android:columnCount`       | Total number of columns in the grid.                                    |
| `android:rowCount`          | Total number of rows in the grid.                                       |
| `android:layout_row`        | Specifies the row index for the child view.                             |
| `android:layout_column`     | Specifies the column index for the child view.                          |
| `android:layout_rowSpan`    | Span the view across multiple rows.                                     |
| `android:layout_columnSpan` | Span the view across multiple columns.                                  |
| `android:useDefaultMargins` | Adds default spacing between child elements.                            |
| `android:alignmentMode`     | Align children using margins or bounds (`alignMargins`, `alignBounds`). |

---

### 🔹 **Use Cases:**

- **Keypads or calculators**
    
- **Login screens**
    
- **Statistical dashboards**
    
- **Form-like UIs with labels and inputs**


## 📘 **LinearLayout in Android**

### 🔹 **Definition:**

`LinearLayout` is a **view group** in Android that **aligns its child views in a single direction** — either **vertically** or **horizontally**.

---

### 🔹 **Key Characteristics:**

|Feature|Description|
|---|---|
|One-directional layout|Views are arranged in **a row (horizontal)** or **a column (vertical)**.|
|Orientation Control|Controlled using `android:orientation="horizontal"` or `"vertical"`.|
|Weight Distribution|Uses `layout_weight` to proportionally distribute available space.|
|Gravity Support|Supports alignment using `android:gravity` and `layout_gravity`.|

---

### 🔹 **Orientation:**

- `android:orientation="vertical"` → Views stacked top to bottom.
    
- `android:orientation="horizontal"` → Views aligned left to right.
    

---

### 🔹 **Example – Vertical LinearLayout**

```xml
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:text="Username"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

    <EditText
        android:hint="Enter username"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>

    <Button
        android:text="Submit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>

</LinearLayout>
```

---

### 🔹 **Important XML Attributes for LinearLayout:**

|Attribute|Description|
|---|---|
|`android:orientation`|Direction of layout: `"horizontal"` or `"vertical"`.|
|`android:gravity`|Aligns all children inside LinearLayout (e.g., `center`, `top`, `bottom`).|
|`android:layout_gravity`|Aligns an individual child view inside the parent layout.|
|`android:layout_weight`|Distributes remaining space proportionally among children.|
|`android:baselineAligned`|If `false`, disables baseline alignment (used in vertical layouts).|

---

### 🔹 **layout_weight Example (Space Distribution):**

```xml
<LinearLayout
    android:orientation="horizontal"
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <Button
        android:layout_weight="1"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Left" />

    <Button
        android:layout_weight="2"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:text="Right" />

</LinearLayout>
```

Here:
- The first button takes 1 part    
- The second takes 2 parts of the total available width.
### 🔹 **Use Cases:**
- Simple **form-like UIs** (e.g., login/register).
- **Buttons and icons** arranged in a row or column.
- **Navigation bar** or toolbars.


# UNIT 4
## Adapter
![](../../statics/Pasted%20image%2020250505125645.png)
An Adapter object acts as a bridge between an AdapterView and the underlying data for that view. The Adapter provides access to the
data items. The Adapter is also responsible for making a View for each item in the data set.

### 📘 **ArrayAdapter in Android**

#### ✅ **Definition:**

- `ArrayAdapter` is the most commonly used adapter in Android.
    
- It is used when you have a list of **similar data items** like names, cities, phone numbers, etc.
    
- It maps data from an array (or list) to views like **ListView**, **Spinner**, or **GridView**.
    

---

### 🔁 **Basic Use Case:**

When displaying a list of strings (like course names), `ArrayAdapter` binds that array to a `ListView`.

#### 🧩 **Adapter Structure Block Diagram:**

```
Data Source         →         Adapter         →         Adapter View
(ArrayList, etc.)              (ArrayAdapter)             (ListView, Spinner)
```

---

### 🧱 **Constructor Syntax:**

```java
ArrayAdapter(Context context, int resource, int textViewResourceId, T[] objects)
```

|Parameter|Description|
|---|---|
|`context`|Context of current Activity or Fragment (e.g., `this`, `getApplicationContext()`)|
|`resource`|Layout resource ID for list item (e.g., `R.layout.itemLV`)|
|`textViewResourceId`|ID of TextView inside that layout to show text (e.g., `R.id.itemTView`)|
|`objects`|Array or List to display in the ListView|

---

### ✅ **Code Example:**

#### 📌 **Java Code**

```java
String courseList[] = {
    "Python", "C Programming", "Data Structure", 
    "Database", "Java", "Compiler Design", 
    "Android Development", "Operating System"
};

ArrayAdapter<String> arrayAdapter;
arrayAdapter = new ArrayAdapter<>(
    this,
    R.layout.itemLV,
    R.id.itemTView,
    courseList
);

ListView listView = findViewById(R.id.listView);
listView.setAdapter(arrayAdapter);
```

#### 📌 **itemLV.xml (custom layout for each row):**

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical" 
    android:padding="8dp"
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <TextView
        android:id="@+id/itemTView"
        android:textSize="18sp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
</LinearLayout>
```

---

### 📝 **Tips:**

- Use `ArrayAdapter` when working with **simple layouts**.
    
- Use **Custom Adapter** (extend `BaseAdapter` or `ArrayAdapter`) for more complex item views (e.g., with image, buttons, etc.).
    
- `getApplicationContext()` is used for general context. Use `this` inside an Activity and `getActivity()` in Fragment.

### 📘 **ArrayListAdapter in Android**

#### ✅ What is it?

- **ArrayListAdapter** is a common way to describe using `ArrayAdapter` with an `ArrayList<T>` data source.
    
- It's not a separate class—it's simply `ArrayAdapter<T>` that works with a dynamic list (`ArrayList`), allowing addition and removal of items at runtime.
    

---

### 🧩 **Why Use `ArrayList` Instead of Array?**

- Arrays are fixed in size.
    
- `ArrayList` is **resizable** and allows dynamic updates.
    
- You can easily **add, remove, or modify** items and then notify the adapter.
    

---

### 🧱 **Constructor Syntax:**

```java
ArrayAdapter<T> adapter = new ArrayAdapter<>(
    Context context,
    int resource,
    int textViewResourceId,
    List<T> objects
);
```

---

### ✅ **Example Code:**

#### 📌 Java Code

```java
ArrayList<String> languages = new ArrayList<>();
languages.add("Java");
languages.add("Kotlin");
languages.add("Python");

ArrayAdapter<String> adapter = new ArrayAdapter<>(
    this,
    R.layout.item_layout,
    R.id.textViewItem,
    languages
);

ListView listView = findViewById(R.id.listView);
listView.setAdapter(adapter);

// Add new item dynamically
languages.add("C++");
adapter.notifyDataSetChanged(); // Refresh the ListView
```

---

### 📄 **item_layout.xml**

```xml
<?xml version="1.0" encoding="utf-8"?>
<TextView xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/textViewItem"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:padding="10dp"
    android:textSize="18sp" />
```

---

### 🧠 **Important Methods:**

|Method|Purpose|
|---|---|
|`add(T object)`|Adds a new item to the list|
|`remove(T object)`|Removes an item from the list|
|`clear()`|Removes all items|
|`notifyDataSetChanged()`|Notifies the view to refresh its content|

---

### 📝 **Use Cases:**

- When you need a **dynamic list** (like a to-do app or chat messages).
    
- Simple list items like names, cities, or tasks.
    
- Ideal for use with **ListView**, **Spinner**, or **AutoCompleteTextView**.
    

## 📘 **BaseAdapter in Android**

### ✅ What is `BaseAdapter`?

- `BaseAdapter` is an **abstract class** in Android used when you need to display complex or custom list items in views like **ListView** or **GridView**.
    
- It gives **complete control** over how the items are displayed.
    
- You must **extend this class** and implement its methods
### 🔁 **Why Use `BaseAdapter`?**
- Use `BaseAdapter` when:
    - You need **custom layouts** (e.g., multiple views in one item: image + text).
    - You want more flexibility than `ArrayAdapter`.

---

### 🧱 **Methods to Implement in a Custom Adapter:**

|Method|Purpose|
|---|---|
|`getCount()`|Returns total number of items|
|`getItem(int position)`|Returns the item at the specified position|
|`getItemId(int position)`|Returns item ID for the specified position|
|`getView(int position, View convertView, ViewGroup parent)`|Returns the view for each item|

---

### ✅ **Example: CustomAdapter using BaseAdapter**

#### 📌 Java Code

```java
public class CustomAdapter extends BaseAdapter {

    Context context;
    ArrayList<String> languages;
    LayoutInflater inflater;

    public CustomAdapter(Context context, ArrayList<String> languages) {
        this.context = context;
        this.languages = languages;
        inflater = LayoutInflater.from(context);
    }

    @Override
    public int getCount() {
        return languages.size();
    }

    @Override
    public Object getItem(int position) {
        return languages.get(position);
    }

    @Override
    public long getItemId(int position) {
        return position;
    }

    @Override
    public View getView(int position, View convertView, ViewGroup parent) {
        convertView = inflater.inflate(R.layout.list_item, null);

        TextView textView = convertView.findViewById(R.id.textView);
        textView.setText(languages.get(position));

        return convertView;
    }
}
```

---

### 📄 `list_item.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<TextView xmlns:android="http://schemas.android.com/apk/res/android"
    android:id="@+id/textView"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:padding="10dp"
    android:textSize="18sp" />
```

---

### 🧠 **How to use in MainActivity:**

```java
ArrayList<String> languages = new ArrayList<>();
languages.add("Java");
languages.add("Python");
languages.add("C++");

CustomAdapter adapter = new CustomAdapter(this, languages);

ListView listView = findViewById(R.id.listView);
listView.setAdapter(adapter);
```

---

### 📌 **Key Points:**

- `BaseAdapter` gives full control over row design.
    
- You can use it for **images, buttons, multiple views** in a list item.
    
- Ideal for **custom UI**, e.g., chat app, product list, etc.
    
- Better to use **ViewHolder pattern** for performance (to avoid inflating views again and again).
    
| Feature / Aspect         | **ArrayAdapter**                                         | **BaseAdapter**                                                 | **ListAdapter**                                                             |
| ------------------------ | -------------------------------------------------------- | --------------------------------------------------------------- | --------------------------------------------------------------------------- |
| **Definition**           | A concrete adapter used for lists with a single TextView | An abstract class for custom complex list item layouts          | An interface that is usually implemented by `BaseAdapter` or `ArrayAdapter` |
| **Extends / Implements** | Extends `BaseAdapter` and implements `ListAdapter`       | Abstract class (implements `ListAdapter`, `SpinnerAdapter`)     | Interface (not used directly)                                               |
| **Customization**        | Limited – mostly for lists of strings or simple objects  | Full control over layout, multiple views per item               | Provides method structure for managing lists in adapters                    |
| **Use Case**             | Displaying simple lists like strings, numbers            | Creating complex/custom list items (images, buttons, etc.)      | Provides contract for all adapters used with ListViews                      |
| **Requires ViewHolder**  | Optional, but recommended for performance                | Recommended (often used with ViewHolder for better performance) | N/A – being an interface                                                    |
| **Ease of Use**          | Very easy (plug-and-play with small setup)               | More complex and flexible (requires more code)                  | Not used directly by developers                                             |
| **Performance**          | Good for small/simple lists                              | Better for large/complex lists if optimized (with ViewHolder)   | Depends on the implementing class                                           |
| **Typical Use**          | Lists of text items, e.g., contacts, cities              | Chat UI, product listing, custom row design                     | Ensures adapter behaves correctly for ListViews                             |
| **View Types**           | Usually single view type                                 | Supports multiple view types                                    | Depends on the implementation                                               |

## View
A View is a straightforward component of a user interface. Advance viewing components help to display a long list of items in android main activity. The data can be in any form to display. Each viewing components classes having a number function to interact with users. It is in charge of drawing and event handling


### 1. **GridView**

- **Purpose:** Displays items in a two-dimensional, scrollable grid.
    
- **Use Case:** Ideal for image galleries or product thumbnails.
    
- **Behavior:** Scrolls vertically and arranges elements in rows and columns.
    
- **Needs an Adapter:** Typically used with `ArrayAdapter` or `BaseAdapter`.
    

---

### 2. **WebView**

- **Purpose:** Allows display of web pages inside an Android app.
    
- **Use Case:** Load and show external websites or HTML content.
    
- **Behavior:** Acts like a mini-browser inside the app.
    
- **Important Method:** `loadUrl(String url)` is used to load web pages.
    

---

### 3. **ScrollView**

- **Purpose:** Provides a scrollable view for a vertically long layout.
    
- **Use Case:** Wraps large content like forms or long articles.
    
- **Limit:** Can have only one direct child, often a `LinearLayout`.

### 4. **SearchView**
- **Purpose:** Provides a user interface for search operations.
- **Use Case:** Adding search functionality in apps like contact list or product search.
- **Features:** Built-in suggestions, voice search, and text change listener.
### 5. **TabHost**

- **Purpose:** Used to create tabbed navigation in older Android versions.
    
- **Use Case:** Group content under different tabs (e.g., Home, Settings, Profile).
    
- **Structure:** Uses `TabSpec` to define individual tabs.

### 6. **DynamicListView**

- **Purpose:** A `ListView` that allows items to be added/removed at runtime.
    
- **Use Case:** Chat apps, to-do lists, shopping carts.
    
- **Implementation:** Data is updated via Adapter (`notifyDataSetChanged()` method).
### 7. **ExpandableListView**

- **Purpose:** Shows a list with expandable/collapsible groups.
    
- **Use Case:** Categorized menus, FAQs with questions and answers.
    
- **Data Structure:** Uses two-level hierarchy – Group (parent) and Children.