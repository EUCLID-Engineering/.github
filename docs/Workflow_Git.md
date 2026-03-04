# Estandares para el flujo de trabajo colaborativo en Git/Github

# 🚩 Reglas

- Nunca programar en rama `main`, esa rama es exclusiva para codigo totalmente funcional y de producción
- Nombres claros en las ramas y commits

# 🛠 Tabla de comandos basicos

| Acción                       | Comando                         |
| ---------------------------- | ------------------------------- |
| **Clonar por primera vez**   | `git clone [URL_DEL_REPO]`      |
| **Ver estado actual**        | `git status`                    |
| **Ver historial**            | `git log --oneline`             |
| **Deshacer cambios locales** | `git restore .`                 |
| **Crear y cambiar de rama**  | `git checkout -b [NOMBRE_RAMA]` |

# Escenarios

## 🚀 Escenario 1: Crear nueva funcionalidad (Feature)
Este es el flujo diario cuando se va a programar algo nuevo

1. Asegurarte de que estas en la rama `main` y la tienes actualizada en tu equipo:

- Comando para posicionarte en la rama `main`
```
git checkout main
```

- Comando para actualizar la rama `main` con los ultimos datos
```
git pull origin main
```

2. Crear una rama para tu tarea:
```
git checkout -b feature/SCRUM-XX-descripcion
```

3. Trabaja y haz commmits locales (pequeños y frecuentes):
```
git add .
git commit -m "feat: Lógica inicial de detección de estrés"
```

4. Sube tu rama a Github:
```
git push origin feature/SCRUM-XX-descripcion
```

5. En Github: Abre un Pull Request (PR). Pidele al Project Manager que revise el código. Si todo está bien, se hace el Merge

## 🔄 Escenario 2: Sincronizar cambios de otros (Evitar conflictos)
Si un compañero subió cambios a `main` mientras tú trabajabas en tu rama, debes traer esos cambios a la tuya para que no haya choques al final.

1. Posicionate en tu rama que estas trabajando
```
git checkout feature/SCRUM-XX-descripcion
```

2. Trae lo nuevo de `main` a tu rama
```
git pull origin main
```

3. Resuelve conflictos (si los hay): Si Git te avisa de archivos duplicados, corrígelos en VS Code, guarda y luego:
```
git add .
git commit -m "fix: resolviendo conflictos con main"
git push origin feature/SCRUM-XX-descripcion
```

## 🆘 Escenario 3: ¡Emergencia! Un error en producción (Hotfix)
Si algo se rompió en la base de datos de Supabase y urge arreglarlo (por ej.)

1. Crea una rama de emergencia desde `main`
```
git checkout main
git checkout -b bugfix/conexion-supabase-caida
```

2. Arregla el código, commit y sube:
```
git add .
git commit -m "fix: corrección de URL de conexión en variables de entorno"
git push origin bugfix/conexion-supabase-caida
```

3. Merge: Se hace el Pull Request, se aprueba y se borra la rama de emergencia

## 🧹 Escenario 4: Limpieza después del trabajo
Una vez que tu Pull Request (PR) fue aceptado y mezclado en `main`, tu rama local ya no sirve

1. Vuelve a `main` y actualiza:
```
git checkout main
git pull origin main
```

2. Borra tu rama local:
```
git branch -d feature/SCRUM-XX-descripcion
```











