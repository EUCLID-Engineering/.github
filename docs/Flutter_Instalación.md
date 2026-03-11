> Para mayor información, consulta la documentación oficial de Flutter: `https://docs.flutter.dev/install/manual`

> Para la instalación de Android Studio y sus SDK Tools consulta: `https://docs.flutter.dev/platform-integration/android/setup`

# 1. Descargar e instalar Flutter SDK

**Descargar Flutter**
- Link: https://storage.googleapis.com/flutter_infra_release/releases/stable/windows/flutter_windows_3.41.4-stable.zip

**Crear carpeta donde se instalará**
- Ir a `C:\` y crear carpeta `Development`

**Extraer Flutter en carpeta creada**
- Extraer el `zip` de Flutter
- Ir a `C:\Development\` y copiar el contenido extraido
- El resultado es la ruta `C:\Development\flutter\`

**Agregar al PATH**
- Escribir en el menu Inicio de windows: `Editar las variables de entorno del sistema` y dar enter
- Click en `Variables de entorno...`
- En el apartado inferior de `Variables del sistema` buscar la variable llamada `Path`, seleccionar y dar click en `Editar`
- Dar click en el botón de `Nuevo` y pegar la ruta `C:\Development\flutter\bin`
- Dar `aceptar` y salir.

**Valida la Instalación**
- En una consola escribe el comando `flutter --version` y `dart --version`

---

# 2. Descargar e instalar Android Studio y SDK

**Ir a pagina para descargar Android Studio**
- Link: https://developer.android.com/studio?hl=es-419

**Instala Android Studio**
- Usa la opción recomendada de instalación

**Despues de instalar Android Studio, instalar SDK Tools**
- **Inicia Android Studio.**
- **Abre el cuadro de diálogo de configuración del SDK Manager:**
  - Si la ventana de "Welcome to Android Studio" está abierta, haz clic en el botón **More Actions** (que está junto a _New Project_ y _Open_) y selecciona **SDK Manager** en el menú desplegable.
  - Si ya tienes un proyecto abierto, ve a **Tools > SDK Manager**.
- **Configura las Plataformas:**
  - Asegúrate de estar en la pestaña **SDK Platforms**.
  - Verifica que la primera entrada con un **API Level de 36** esté seleccionada.
  - Si en la columna _Status_ dice "Update available" o "Not installed":
    - Marca la casilla de esa fila.
    - Haz clic en **Apply**.
  - Cuando aparezca el diálogo _Confirm Change_, haz clic en **OK**.
  - Se abrirá el _SDK Component Installer_ con una barra de progreso. Al terminar, haz clic en **Finish**.
- **Configura las Herramientas (SDK Tools):**
  - Cambia a la pestaña **SDK Tools**.
  - Verifica que las siguientes herramientas estén seleccionadas:
    - **Android SDK Build-Tools**
    - **Android SDK Command-line Tools**
    - **Android Emulator**
    - **Android SDK Platform-Tools**
    - **CMake**
    - **NDK (Side by side)**
  - Si alguna de estas herramientas muestra "Update available" o "Not installed":
    - Marca la casilla correspondiente.
    - Haz clic en **Apply**.
  - Confirma los cambios con **OK**.
  - Espera a que el instalador finalice y haz clic en **Finish**.

---

# 3. Aceptar licencias de android

**Corre el comando:**
```
flutter doctor --android-licenses
```

Te saldrán las licencias e irás aceptando con la letra `Y` y `enter`.

---

# 4. Verificar que todo este correcto

Ejecuta el comando:
```
flutter doctor
```

Corrige si hay errores.






