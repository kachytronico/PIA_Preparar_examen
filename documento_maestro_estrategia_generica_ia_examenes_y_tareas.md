# Documento Maestro — Estrategia Genérica para Resolver Tareas y Exámenes de IA

> **Objetivo del documento**
>
> Este documento define una **estrategia única, reutilizable y genérica** para resolver **tareas y exámenes del módulo de Programación de Inteligencia Artificial** (y otros similares) usando **IA como asistente principal**, manteniendo control humano, rigor técnico y alineación estricta con el enunciado y las tutorías.
>
> Está pensado para:
>
> * Ser copiado tal cual a un repositorio de examen.
> * Servir como **fuente de verdad** para una IA (Gemini, Copilot u otra).
> * Evitar errores típicos (data leakage, malas decisiones, improvisaciones).
> * Guiar el trabajo **paso a paso**, tomando decisiones basadas en resultados reales.

---

## 1. Principios fundamentales (filosofía de trabajo)

1. **El enunciado manda**

   * El texto literal del enunciado es la prioridad máxima.
   * Ninguna mejora técnica puede contradecirlo.

2. **La IA asiste, no sustituye el criterio**

   * La IA propone, ejecuta y documenta.
   * Las decisiones se justifican siempre con resultados observables.

3. **Paso a paso, nunca todo de golpe**

   * Cada bloque se implementa, se ejecuta y se analiza antes de continuar.

4. **Nada se inventa**

   * Si un valor no aparece en el output, se indica explícitamente.
   * No se rellenan conclusiones con números ficticios.

5. **Pensar como el corrector**

   * Cada decisión debe poder defenderse oralmente.
   * El notebook debe leerse como un informe razonado.

---

## 2. Arquitectura general de documentos

La resolución de cualquier tarea o examen se apoya en **cuatro tipos de documentos**, cada uno con un rol claro.

### 2.1 Documento de Enunciado (específico de cada tarea)

* Contiene el texto literal del ejercicio.
* Se pasa íntegro a la IA.
* Define:

  * qué hay que hacer,
  * qué puntúa,
  * qué es obligatorio.

---

### 2.2 Guía Operativa (específica o genérica)

* Traduce el enunciado a acciones técnicas.
* Puede ser:

  * específica de una tarea,
  * o una guía genérica para exámenes.

Incluye:

* orden de trabajo recomendado,
* modelos obligatorios y prohibidos,
* criterios de evaluación,
* decisiones aceptadas por el profesor.

---

### 2.3 Documentación de Estrategia (este documento)

* Define **cómo trabajar con la IA**.
* No depende del contenido de la tarea.
* Se reutiliza en todas las entregas.

---

### 2.4 Documentos auxiliares (reutilizables)

Estos documentos se mantienen estables entre tareas:

* Guía de estilo de redacción.
* Checklist de revisión.
* Guía de depuración.
* Playbook de decisiones técnicas.

---

## 3. Roles de las herramientas de IA

### 3.1 IA principal (Gemini en Colab)

Rol:

* Crear notebooks completos.
* Ejecutar código.
* Leer outputs reales.
* Tomar decisiones basadas en resultados reales.
* Redactar conclusiones finales.

Uso recomendado:

* Exámenes.
* Fases críticas (AED, preprocesado, semisupervisado).

---

### 3.2 IA auxiliar (Copilot en VS Code)

Rol:

* Crear estructura literal del enunciado.
* Rellenar código bajo instrucciones estrictas.
* Mejorar redacción **sin inventar resultados**.

Limitación clave:

* Copilot **no interpreta outputs de notebooks**.

---

## 🔒 Regla anti-bloqueo para entornos interactivos (Colab / Jupyter)

En entornos como Google Colab, la IA puede intentar demostrar que “lee” los documentos
creando celdas automáticas de análisis, impresión de archivos o tareas multi-step.
Esto **NO es deseable en un examen**.

### Normas obligatorias de comportamiento de la IA

1. **No releer documentos desde disco**

   * Asumir que el Documento Maestro, el enunciado y las guías
     ya están presentes en el contexto de la conversación.
   * No imprimir su contenido en el notebook.

2. **Prohibidas celdas de análisis de documentación**

   * No crear bloques tipo:

     * “Analyze Documentation”
     * “Assess Current State”
     * “Generate Status Report”
   * El análisis estratégico debe hacerse **en el chat**, no en el notebook.

3. **Trabajo estrictamente por fases cortas**

   * En cada interacción:

     * proponer qué fase toca,
     * explicar brevemente qué se va a hacer,
     * **esperar confirmación del usuario**.
   * Ejecutar **solo el bloque actual**, nada más.

4. **Separación clara de roles**

   * El chat → planificación y decisiones.
   * El notebook → código, ejecución y resultados.
   * Nunca mezclar ambos.

### Objetivo de esta regla

* Evitar bloqueos.
* Mantener el notebook limpio y defendible.
* Maximizar control humano durante el examen.

---

## ✍️ Regla de estilo obligatoria para textos generados por la IA

Todo texto Markdown generado por la IA (objetivos, conclusiones, explicaciones) debe cumplir **obligatoriamente**:

1. **Primera persona del singular**

   * Usar “yo”, “he”, “he analizado”, “he decidido”.
   * Prohibido lenguaje impersonal (“se observa”, “se ha realizado”).

2. **Lenguaje humano y natural**

   * Frases variadas, no plantillas repetitivas.
   * Evitar tono académico genérico o robótico.
   * Escribir como si el autor fuera el alumno que defiende su trabajo.

3. **Referencia a resultados concretos**

   * Mencionar shapes, métricas, gráficos o valores observados.
   * Si un valor no está aún disponible, indicarlo explícitamente.

4. **Prohibido texto genérico**

   * No usar frases tipo:

     * “Este análisis permite comprender…”
     * “A continuación se procede a…”
   * Cada texto debe reflejar una decisión o interpretación real.

Si un texto no cumple estas reglas, **debe reescribirse antes de continuar**.

---

## 4. Flujo de trabajo genérico (válido para cualquier tarea)

### Fase 0 — Preparación

Antes del examen o tarea:

* Tener el repositorio preparado.
* Incluir este Documento Maestro.
* Incluir guías auxiliares.

---

### Fase 1 — Arranque con IA

Prompt inicial:

> "Lee todos los documentos del repositorio.
> Vamos a resolver una tarea de Programación de IA.
> Actúa paso a paso y espera confirmación."

---

### Fase 2 — Creación de estructura

Acción:

* Crear el notebook con los títulos **exactos** del enunciado.
* No escribir código todavía.

Objetivo:

* Asegurar que nada obligatorio se olvida.

---

### Fase 3 — Carga de datos (modo examen)

Acción:

* Clonar el repositorio proporcionado.
* Explorar la estructura.
* Descomprimir archivos necesarios.
* Cargar datasets sin hardcodear rutas.

Validación:

* Mostrar shapes y primeras filas.

---

### Fase 4 — Análisis Exploratorio de Datos (AED)

Por cada bloque:

1. Ejecutar código.
2. Analizar outputs.
3. Redactar conclusiones parciales.
4. Decidir acciones posteriores.

Decisiones típicas:

* eliminar o no columnas,
* tratar outliers,
* considerar desbalanceo,
* detectar correlaciones altas.

---

### Fase 5 — Preprocesamiento

Reglas universales:

* Split SIEMPRE antes de fit.
* Fit SOLO con train.
* Transform con valid/test.

Decisiones:

* imputación,
* encoding,
* escalado,
* PCA solo si procede.

---

### Fase 6 — Modelado

Principios:

* Cumplir modelos obligatorios.
* Optimizar sin grids exagerados.
* Evaluar solo en validación hasta el final.

---

### Fase 7 — Técnicas avanzadas

Según tarea:

* Ensembles.
* Aprendizaje semisupervisado.
* Explicaciones de modelos.

Siempre:

* justificar el criterio.

---

### Fase 8 — Revisión final

Acción:

* Pasar checklist completo.
* Revisar alineación con enunciado.
* Confirmar ausencia de errores críticos.

---

## 5. Reglas técnicas universales (líneas rojas)

* ❌ No data leakage.
* ❌ No pseudo-etiquetas en valid/test.
* ❌ No deep learning si no está permitido.
* ❌ No cambiar modelos obligatorios.

---

## 6. Redacción de conclusiones

Principios:

* Basadas solo en outputs reales.
* En primera persona.
* Con datos concretos.
* Interpretativas, no descriptivas.

---

## 7. Objetivo final

El resultado debe ser:

* técnicamente correcto,
* defendible ante corrección,
* coherente,
* claro,
* y reproducible en un examen real.

Este documento es la base para todas las tareas y exámenes futuros.
