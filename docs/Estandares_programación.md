# 🛠️ Estándares de Programación
Este documento establece las normas obligatorias de codificación para el Proyecto ARMON-IA. El cumplimiento de estos estándares garantiza la calidad de la "Ingeniería Pura", facilitando la escalabilidad y el mantenimiento del sistema.

## 1. Variables y Constantes (var)
Las variables deben ser nombradas según su propósito, evitando nombres genéricos o abreviaturas confusas.

- Backend (Python/FastAPI): Se utilizará estrictamente `snake_case`.
  - Ejemplo: `stress_threshold`, `biometric_reading_list`.

- Frontend (Dart/Flutter): Se utilizará `lowerCamelCase`.
  - Ejemplo: `currentUserLevel`, `isWatchConnected`.

- Constantes: En ambos entornos se utilizará `UPPER_SNAKE_CASE`.
  - Ejemplo: `MAX_HEART_RATE_LIMIT`, `API_RETRY_ATTEMPTS`.

## 2. Instancias de Objetos (ins_)
Para diferenciar los objetos instanciados de sus clases base o servicios estáticos, seguiremos estas reglas:

Identificación Clara: Las instancias de servicios, clientes de base de datos o modelos de IA deben incluir el nombre del servicio o el prefijo/sufijo de su función.
- Ejemplos:

  - `db_session` (Instancia de la conexión a base de datos).
  - `colibri_agent` (Instancia del orquestador de LangGraph).
  - `auth_provider` (Instancia del gestor de autenticación).

## 3. Clases y Métodos

### 3.1 Clases
Todas las clases deben utilizar PascalCase y representar un sustantivo que describa su responsabilidad única.

- Ejemplo: `BiometricProcessor`, `UserSessionManager`, `StressAnalyzerNode`.

### 3.2 Métodos
Los métodos dentro de una clase deben usar la misma convención de las variables (`snake_case` o `camelCase` según el lenguaje) pero siempre comenzando con un verbo.

- Ejemplo: `calculate_hrv_average()`, `validateSessionToken()`.

## 4. Funciones y Parámetros

### 4.1 Definición de Funciones

- Tipado (Type Hinting): Es obligatorio declarar el tipo de datos de entrada y el tipo de retorno.

- Simplicidad: Si una función requiere más de 3 parámetros, se debe evaluar el uso de un objeto de configuración o un esquema de Pydantic.

### 4.2 Documentación de Parámetros

Cada parámetro debe ser documentado dentro del cuerpo de la función utilizando la nomenclatura de posición.

Formato de Docstring:

```
def analyze_vital_signs(user_id: UUID, heart_rate: float, sleep_quality: int) -> dict:
    """
    Analiza los signos vitales para detectar anomalías de estrés.
    
    # P1 - user_id: Identificador único del usuario para consulta histórica.
    # P2 - heart_rate: Frecuencia cardíaca actual capturada por el sensor.
    # P3 - sleep_quality: Valor entero que representa la profundidad del sueño.
    
    return: Diccionario con el nivel de riesgo y la recomendación generada.
    """
```

## 5. Comentarios y Documentación (C)

El código debe ser auto-explicativo, pero la lógica compleja requiere documentación adicional:

- Comentarios de Bloque: Se utilizan para explicar el razonamiento detrás de algoritmos o flujos de IA (especialmente en los nodos de decisión de `LangGraph`).
- Comentarios de Línea: Breves aclaraciones para pasos no evidentes.

Regla de Idioma:

- Código: Todo el código (variables, clases, métodos, archivos) debe escribirse en Inglés.

- Documentación: Los comentarios, docstrings y explicaciones técnicas deben escribirse en Español para la revisión interna del equipo y de calidad.

## 6. Estándares de Calidad y Prácticas

- Backend: Uso obligatorio de Pydantic para validación de datos y `SQLAlchemy` para la interacción con Supabase.

- Manejo de Errores: Nunca usar `print()` para errores; utilizar `HTTPException` en el `API` y logs estructurados en los servicios de IA.

- IA: En los grafos de estado, el objeto State debe tratarse como inmutable; cada nodo debe devolver una actualización del estado, no modificar el original.
