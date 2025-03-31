
---

### Legal Disclaimer
The project is open-source, but certain restrictions apply. The **"amon"** code is proprietary, and as such, it cannot be modified, redistributed, or used outside of its original context. By using this software, you agree to **not alter or distribute** the code's functionality. Violating these terms may result in legal action.

---

### Project Structure
```
/amon-r
│
├── /assets
│   ├── /static
│   │   ├── images/
│   │   └── styles/
│   └── /scripts
│       └── tale.js
│
├── /config
│   └── config.json
│
├── /src
│   ├── /handlers
│   │   ├── register.py
│   │   └── handle.py
│   └── /utils
│       └── helpers.py
│
└── README.md
```

---

### Installation & Conversion to `.exe`

#### 1. **Install Dependencies**
   To use PyInstaller and convert your Python project into an `.exe` file, make sure you have Python installed. You will also need `PyInstaller` to package the project.

   Open the Command Prompt (`cmd`) and install the required dependencies:
   ```bash
   pip install pyinstaller
   ```

#### 2. **Prepare the Codebase**
   Ensure that your project directory is organized as described above. Pay special attention to the `config.json` file and ensure it is correctly set up, as it's likely essential for the application’s configuration.

#### 3. **Create the Executable with PyInstaller**
   Navigate to the root folder of your project in the command prompt.

   ```bash
   cd path\to\amon-r
   ```

   Then, use PyInstaller to generate the `.exe` file. The general command to package your app would look like this:
   ```bash
   pyinstaller --onefile --windowed src/handlers/register.py
   ```
   
   - `--onefile` creates a single `.exe` file.
   - `--windowed` prevents opening a terminal window when running the `.exe` (useful for GUI applications).

   Replace `src/handlers/register.py` with the Python entry point of your app. If it's a different file, specify that instead.

#### 4. **Output Files**
   After running the above command, PyInstaller will create a new directory, `dist`, where the `.exe` file will be stored. The `.exe` file will be named `register.exe` (or whatever you named the input Python file).

   You can now find the compiled executable in:
   ```bash
   dist\register.exe
   ```

#### 5. **Additional Options (Optional)**
   You may want to include additional files, like images or configuration files, that are referenced by the code. You can do this using the `--add-data` option.

   For example, if you need to include assets like images and config files, run:
   ```bash
   pyinstaller --onefile --windowed --add-data "assets/static/images;assets/static/images" --add-data "config/config.json;config/config.json" src/handlers/register.py
   ```

   This will package those files alongside the `.exe`. Ensure you use the correct path to assets.

#### 6. **Running the Executable**
   Once PyInstaller has finished the process, navigate to the `dist` folder and run the generated `.exe` to test it.

   ```bash
   cd dist
   register.exe
   ```

#### 7. **Distribute the Executable**
   After creating the `.exe`, you can distribute it without sharing the source code, keeping it aligned with the legal constraints of your project.
