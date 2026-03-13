# 1. Onboarding (Solo la primera vez)

Cuando un compañero nuevo se une, debe seguir estos pasos:

  1. Clonar el repo: `git clone https://github.com/EUCLID-Engineering/armonia-mobile-app.git`
  2. Entrar a la carpeta: `cd armonia-mobile-app`
  3. Descargar dependencias: `flutter pub get`
  - > Este comando lee el `pubspec.yaml` y descarga todas las librerias necesarias en su PC

---

# 2. Rutina diaria

Antes de empezar a escribir una sola linea de código cada día, todos deben de hacer esto:

### A. Sincronizar (Update)

```
git pull origin main
```

> ¿Por qué? Para trabajar siempre sobre la versión más reciente que otros compañeros hayan subido. Si alguien añadió una librería nueva, después del pull deben ejecutar: `flutter pub get.`

### B. Crear una Rama

**NUNCA** trabajar directamente en `main`

```
git checkout -b ....
```

---

# 3. Durante el desarrollo

- **VS Code**: Si ven líneas rojas o azules, pasen el mouse por encima. Flutter es muy estricto con las reglas de estilo (Lints).

- **Guardado rápido**: Usen el "Hot Reload" (guardar con `Ctrl+S`) para ver cambios sin reiniciar la app.

- **Nuevas Librerías**: Si alguien necesita instalar un paquete nuevo (ej: para manejar la cámara), debe avisar al equipo porque todos tendrán que hacer un `flutter pub get` al recibir ese cambio.

---

# 4. Antes de subir el código (Checklist de Calidad)

Antes de hacer un `git push`, el desarrollador debe verificar que su codigo esta "limpio":

1. Analizar el codigo:
```
flutter analyze
```
> Si este comando da errores o warnings, hay que corregirlos antes de subir.  

2. Formatear:
```
dart format .
```
> Esto ordena el código automáticamente según los estándares de Google.

---

# 5. El envío (Push) y Pull Request

**Una vez terminada la tarea:**

1. `git add .`
2. `git commit -m "....."`
3. `git push origin <nombreRama>`

**Paso final de PM**: En GitHub, el desarrollador debe abrir un Pull Request (PR) hacia la rama `main`. Se debe revisar que el código se vea bien antes de darle al botón de "Merge".

---

# 6. Hotfixes

- Si la app se vuelve "loca", errores raros de compilación, etc...
- `flutter clean` (Borra archivos temporales de compilación)
- `flutter pub get` (Vuelve a descargar todo limpio)















