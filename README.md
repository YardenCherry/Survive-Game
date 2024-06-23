# Survive Game

### Introduction
SurviveGame is a mobile game developed as part of a mobile security course. The objective of the game is to navigate through various levels to find the way to survive and reach your city. The player must enter a specific ID when starting the game, which influences the gameplay and the steps needed to complete each level.

### Initial Setup:
- **Decompile the APK:**
  - Use online tools to convert the APK file back to source code and readable resources.

### Review Decompiled Code:
- Analyze the extracted Java files and resources to understand the structure and logic of the application.
  Key components examined include:
  
  1. **Manifest File:**
      -  Provided essential app information and permissions.
    
  2. **Source Code:**
      - Explored Java files for main activities and game logic
      - Identify files related to user input (ID entry) and the game logic to "find the way to survive and reach your city."

  3. **Resources:**
       Examined XML layout files, images, and value resources
      - `res/layout`: XML layout files that define the UI components.
      - `res/drawable`: Images and other drawable resources.
      - `res/values`: XML files defining strings, colors, and styles.

  The `AndroidManifest.xml` file provides essential insights into the application's structure and crucial elements:

- **Package Name:** `com.example.survivegame`
- **SDK Versions:**
  - `minSdkVersion`: 24
  - `targetSdkVersion`: 30
- **Permissions:** The app requires internet access (`android.permission.INTERNET`).

Key Activities:
- `com.example.survivegame.Activity_Game`: Likely manages the core gameplay mechanics and user interface, designed for portrait orientation.
- `com.example.survivegame.Activity_Menu`: Serves as the primary entry point (launcher activity), also configured for portrait orientation.

Next steps involve:
- Reviewing `Activity_Menu` for handling initial ID input.
- Exploring `Activity_Game` for implementing game logic and user interactions.
- Inspecting resources like `res/layout` for UI components and `res/values` for defining strings, colors, and styles.
### Identify and Fix Bugs:
#### `Activity_Game.java`
1. **Update Toast Messages:**
     
   To:
    ```java
    Toast.makeText(this, "Survived in " + state, Toast.LENGTH_SHORT).show();
    } else {
    Toast.makeText(this, "You Failed ", Toast.LENGTH_SHORT).show();
   ```
   
3. **Update Integer Parsing:**
 
    To:
    ```java
        iArr[i] = Integer.parseInt(String.valueOf(id.charAt(i))) % 4;
     ```


### Implementation of Required Adjustments:
Enhanced the toast message display duration to improve user interaction.
Streamlined the process of parsing integers for greater clarity and efficiency.

### Testing and Verification:
Executed the application on both emulator and physical devices to validate the modifications.
Confirmed that the game mechanics function correctly and that the appropriate toast messages are displayed upon successful execution.

#### Example ID and Steps:
1. **Enter a valid ID:**
    - Example ID: "318774932"
    - Derived Steps:
       - The `steps` array will be derived as follows:
          - Character at index 0 ('3') -> 3 % 4 = 3 (Down)
          - Character at index 1 ('1') -> 1 % 4 = 1 (Right)
          - Character at index 2 ('8') -> 8 % 4 = 0 (Left)
          - Character at index 3 ('7') -> 7 % 4 = 3 (Down)
          - Character at index 4 ('7') -> 7 % 4 = 3 (Down)
          - Character at index 5 ('4') -> 4 % 4 = 0 (Left)
          - Character at index 6 ('9') -> 9 % 4 = 1 (Right)
          - Character at index 7 ('3') -> 3 % 4 = 3 (Down)
          - Character at index 8 ('2') -> 2 % 4 = 2 (Up)
2. **Follow the steps:** 
   - Press the buttons in the correct order as derived from the ID.


### Watch me: 


https://github.com/YardenCherry/Survive-Game/assets/155112044/20abd434-e144-4f6f-89a9-3a7ce1a39764


