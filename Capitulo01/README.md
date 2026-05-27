# Alcance de proyectos, KPIs de éxito y mejores prácticas en Testing Lifecycle (STLC) asistido por IA para optimización en ambientes complejos.

## 1. Metadatos

| Atributo | Valor |
|---|---|
| **Duración estimada** | 60 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Crear |
| **Módulo** | Módulo 1 — STLC asistido por IA |
| **Laboratorio** | 01-00-01 |
| **Herramientas principales** | Microsoft 365 Copilot Chat, Microsoft Word, Microsoft Excel |

---

## 2. Descripción General

En este laboratorio aplicarás Microsoft 365 Copilot Chat para construir los artefactos fundacionales de un proyecto de testing real: un documento de alcance, un tablero de KPIs, un plan de pruebas estructurado según el STLC y una guía de mejores prácticas para la adopción de IA en QA. El escenario simulado corresponde a la modernización de un sistema ERP corporativo ficticio denominado **"CorpERP 3.0"**, lo que te permitirá practicar prompt engineering avanzado en un contexto de alta complejidad sin exponer datos reales de tu organización. Al finalizar, habrás generado cuatro artefactos de calidad profesional que demuestran el valor de integrar IA conversacional en las fases tempranas del STLC.

---

## 3. Objetivos de Aprendizaje

Al completar este laboratorio serás capaz de:

- [ ] **Definir** el alcance y la estrategia de un proyecto de testing utilizando Copilot Chat para generar marcos de trabajo alineados al STLC en entornos de IT complejos.
- [ ] **Identificar y documentar** KPIs de éxito relevantes para medir la eficiencia del testing asistido por IA, estructurando métricas cuantitativas y cualitativas en un tablero de Excel.
- [ ] **Crear** un plan de pruebas inicial asistido por Copilot que incorpore las fases del STLC con criterios de entrada y salida claramente definidos.
- [ ] **Evaluar** mejores prácticas para integrar herramientas de IA en el ciclo de vida de testing y documentar recomendaciones aplicables al contexto organizacional.
- [ ] **Aplicar** técnicas de prompt engineering iterativo para refinar los artefactos generados y elevar su calidad profesional.

---

## 4. Prerrequisitos

### Conocimiento previo

| Área | Nivel requerido |
|---|---|
| Ciclo de vida de pruebas de software (STLC) y sus fases principales | Básico |
| Concepto de KPIs y su utilidad en gestión de proyectos IT | Básico |
| Uso de Microsoft Word y Excel en entorno Microsoft 365 | Básico |
| Lectura de los materiales teóricos de los temas 1.1 y 1.2 del Módulo 1 | Requerido |
| Conceptos de prompt engineering (contexto, rol, formato de salida) | Introductorio |

### Acceso y licencias

| Recurso | Estado requerido |
|---|---|
| Cuenta corporativa Microsoft 365 con licencia **Copilot activa y verificada** | ✅ Activo |
| Acceso a [copilot.microsoft.com](https://copilot.microsoft.com) | ✅ Verificado |
| Acceso a Microsoft Word Online o Desktop (Microsoft 365) | ✅ Disponible |
| Acceso a Microsoft Excel Online o Desktop (Microsoft 365) | ✅ Disponible |
| Almacenamiento en OneDrive con al menos 500 MB disponibles | ✅ Disponible |

> ⚠️ **CRÍTICO:** Si no puedes acceder a Copilot Chat en [copilot.microsoft.com](https://copilot.microsoft.com) con tu cuenta corporativa, detente y contacta a tu instructor **antes** de continuar. Sin esta licencia activa, ninguna actividad de este laboratorio es ejecutable.

---

## 5. Entorno del Laboratorio

### Hardware recomendado

| Componente | Mínimo | Recomendado |
|---|---|---|
| Procesador | Intel Core i5 8ª gen / AMD Ryzen 5 (64-bit) | Intel Core i7 / AMD Ryzen 7 |
| Memoria RAM | 8 GB | 16 GB |
| Almacenamiento libre | 2 GB | 5 GB |
| Resolución de pantalla | 1280×768 | 1920×1080 |
| Conexión a Internet | 10 Mbps | 25 Mbps o superior |

### Software requerido

| Software | Versión mínima | Uso en el laboratorio |
|---|---|---|
| Microsoft Edge o Google Chrome | Edge 120+ / Chrome 120+ | Acceso a Copilot Chat y Microsoft 365 Online |
| Microsoft 365 Copilot Chat | Versión actual (SaaS) | Generación de todos los artefactos |
| Microsoft Word (Online o Desktop) | Microsoft 365 versión actual | Documento de alcance y plan de pruebas |
| Microsoft Excel (Online o Desktop) | Microsoft 365 versión actual | Tablero de KPIs |

### Configuración inicial del entorno

Antes de comenzar los pasos del laboratorio, realiza las siguientes verificaciones:

**Paso 0.1 — Verificar acceso a Copilot Chat**

1. Abre tu navegador (Edge o Chrome) y navega a: `https://copilot.microsoft.com`
2. Inicia sesión con tu cuenta corporativa Microsoft 365.
3. Confirma que aparece la interfaz de Copilot Chat con el indicador de tu organización en la esquina superior derecha.
4. Escribe el siguiente mensaje de prueba y presiona Enter:

```
Hola. Confirma que estás operando en modo de trabajo con mi cuenta corporativa. Responde siempre en español.
```

5. Verifica que la respuesta aparece en español y menciona el contexto de trabajo.

**Paso 0.2 — Crear carpeta de trabajo en OneDrive**

1. Navega a `https://onedrive.live.com` o abre OneDrive desde el lanzador de aplicaciones de Microsoft 365.
2. Crea una nueva carpeta llamada: `Lab-01-00-01-STLC-IA`
3. Esta carpeta almacenará todos los artefactos generados durante el laboratorio.

**Paso 0.3 — Abrir documentos base**

1. En OneDrive, dentro de la carpeta `Lab-01-00-01-STLC-IA`, crea los siguientes documentos en blanco:
   - Un documento Word llamado: `01-Alcance-CorpERP3.docx`
   - Un documento Word llamado: `03-Plan-Pruebas-CorpERP3.docx`
   - Un libro Excel llamado: `02-KPIs-Dashboard-CorpERP3.xlsx`
   - Un documento Word llamado: `04-Guia-MejoresPracticas-IA-Testing.docx`
2. Mantén estas pestañas abiertas durante el laboratorio para copiar los artefactos generados.

> 💡 **Recordatorio:** Copilot Chat no guarda el historial de conversaciones de forma permanente. Copia los resultados satisfactorios a tus documentos inmediatamente después de generarlos.

---

## 6. Pasos del Laboratorio

---

### Paso 1 — Generación del Documento de Alcance del Proyecto de Testing

**Objetivo:** Utilizar Copilot Chat con prompts estructurados para generar un documento de alcance completo para el proyecto de testing de CorpERP 3.0, incluyendo identificación de riesgos y restricciones.

#### Contexto del Escenario

> **Escenario ficticio — CorpERP 3.0:** La empresa ficticia *Corporación Nexus S.A.* está migrando su sistema ERP legado (SAP R/3 on-premise) a una solución ERP cloud-native desarrollada internamente llamada **CorpERP 3.0**. El sistema maneja módulos de: Finanzas (GL, AP, AR), Recursos Humanos (nómina, gestión de personal), Cadena de Suministro (inventario, compras) y Reportería (dashboards, exportación PDF/Excel). El proyecto tiene un plazo de 8 meses, un equipo de 6 QA engineers y debe cumplir con regulaciones de privacidad de datos (GDPR equivalente ficticio). El go-live está planificado para el Q3 del año en curso.

#### Instrucciones

1. Navega a [copilot.microsoft.com](https://copilot.microsoft.com) y asegúrate de estar en una sesión activa.

2. Inicia una nueva conversación haciendo clic en **"Nueva conversación"** (o el icono de lápiz/nuevo chat).

3. Copia y pega el siguiente **Prompt 1.1 — Prompt de contexto y rol:**

```
Actúa como un QA Lead Senior con 10 años de experiencia en proyectos de modernización ERP. 
Voy a darte información sobre un proyecto ficticio llamado CorpERP 3.0 y necesito que me 
ayudes a construir artefactos de testing profesionales. 

Contexto del proyecto:
- Empresa: Corporación Nexus S.A. (ficticia)
- Proyecto: Migración de SAP R/3 on-premise a CorpERP 3.0 cloud-native
- Módulos: Finanzas (GL, AP, AR), Recursos Humanos (nómina), Cadena de Suministro 
  (inventario, compras), Reportería (dashboards, exportación PDF/Excel)
- Equipo QA: 6 engineers
- Plazo: 8 meses
- Restricciones: Cumplimiento regulatorio de privacidad de datos, presupuesto fijo, 
  entorno cloud AWS (ficticio), integración con 3 sistemas externos
- Go-live: Q3 del año en curso

Confirma que entendiste el contexto y espera mi siguiente instrucción. Responde en español.
```

4. Lee la confirmación de Copilot. Luego copia y pega el **Prompt 1.2 — Generación del documento de alcance:**

```
Perfecto. Ahora genera un Documento de Alcance del Proyecto de Testing para CorpERP 3.0 
con la siguiente estructura:

1. INFORMACIÓN GENERAL DEL PROYECTO
   - Nombre, versión, fecha, responsable QA, stakeholders clave

2. ALCANCE DEL TESTING
   - Qué está EN SCOPE (módulos, tipos de prueba, niveles de testing)
   - Qué está FUERA DE SCOPE (con justificación)

3. OBJETIVOS DE CALIDAD
   - 3 objetivos medibles alineados al negocio

4. IDENTIFICACIÓN DE RIESGOS DE TESTING
   - Tabla con: ID de riesgo, descripción, probabilidad (Alta/Media/Baja), 
     impacto (Alto/Medio/Bajo), estrategia de mitigación
   - Incluye mínimo 6 riesgos realistas para un proyecto ERP

5. RESTRICCIONES Y SUPUESTOS
   - Al menos 4 restricciones y 4 supuestos

6. CRITERIOS DE ENTRADA Y SALIDA GENERALES
   - Para el proyecto completo de testing

Usa formato profesional con tablas donde corresponda. Responde en español.
```

5. Revisa la respuesta de Copilot. Identifica al menos **dos áreas** que puedas mejorar o especificar más.

6. Aplica el **Prompt 1.3 — Refinamiento iterativo** (ajusta según lo que observaste):

```
El documento es un buen punto de partida. Por favor, mejora las siguientes secciones:

1. En la tabla de RIESGOS, agrega una columna "Indicador de alerta temprana" para cada 
   riesgo, que permita detectar el riesgo antes de que se materialice.

2. En CRITERIOS DE ENTRADA Y SALIDA, desglosa los criterios por nivel de testing: 
   unitario, integración, sistema y UAT.

3. Agrega una sección final llamada "ESTRATEGIA DE TESTING ASISTIDA POR IA" que describa 
   en qué fases del STLC se utilizará Copilot Chat y qué tipo de artefactos generará, 
   basándote en el mapeo STLC+IA que te compartí en el contexto.

Mantén el formato profesional con tablas. Responde en español.
```

7. Una vez que el documento sea satisfactorio, **copia todo el contenido** generado y pégalo en tu documento Word `01-Alcance-CorpERP3.docx`. Aplica estilos de encabezado (Título 1, Título 2) para estructurar el documento.

8. Guarda el documento en OneDrive.

#### Resultado Esperado

Un documento Word estructurado de aproximadamente 3–5 páginas que contenga:
- Tabla de riesgos con al menos 6 entradas y columna de indicadores de alerta temprana
- Criterios de entrada/salida desglosados por nivel de testing
- Sección de estrategia de testing asistida por IA con mención explícita de las fases STLC

#### Verificación

- [ ] El documento contiene las 7 secciones solicitadas (incluyendo la estrategia IA)
- [ ] La tabla de riesgos tiene al menos 6 filas y 6 columnas (incluyendo indicador de alerta)
- [ ] Los criterios de entrada/salida cubren los 4 niveles de testing
- [ ] El documento está guardado en OneDrive en la carpeta `Lab-01-00-01-STLC-IA`
- [ ] Realizaste al menos un ciclo de refinamiento iterativo (Prompt 1.3 o equivalente)

---

### Paso 2 — Construcción del Tablero de KPIs en Excel

**Objetivo:** Utilizar Copilot Chat para diseñar un conjunto completo de KPIs de eficiencia para el testing asistido por IA, y luego estructurarlos en un tablero de Excel con datos simulados.

#### Instrucciones

1. En Copilot Chat, inicia una **nueva conversación** (esto evita que el contexto anterior interfiera con la tarea de KPIs).

2. Copia y pega el **Prompt 2.1 — Definición de KPIs:**

```
Actúa como un experto en métricas de calidad de software con conocimiento en ISO/IEC 25010 
e IEEE 829. Necesito definir un conjunto completo de KPIs para medir la eficiencia de un 
proyecto de testing asistido por IA (usando Microsoft 365 Copilot) en la modernización del 
ERP ficticio CorpERP 3.0.

Genera una tabla de KPIs con las siguientes columnas:
- ID del KPI
- Nombre del KPI
- Categoría (Calidad del Producto / Eficiencia del Proceso / Eficiencia de la IA / 
  Satisfacción del Usuario)
- Definición / Fórmula de cálculo
- Unidad de medida
- Frecuencia de medición
- Meta objetivo (valor numérico o rango)
- Fuente de datos
- Responsable de medición

Incluye obligatoriamente estos KPIs específicos:
1. Defect Density (defectos por KLOC o por módulo)
2. Test Coverage (cobertura de requisitos y de código)
3. Mean Time to Detect (MTTD)
4. Mean Time to Resolve (MTTR)
5. Test Execution Rate
6. Defect Escape Rate
7. ROI del Testing Asistido por IA
8. AI Suggestion Acceptance Rate (tasa de aceptación de sugerencias de Copilot)
9. Test Case Generation Velocity (con vs. sin IA)
10. First Pass Yield (porcentaje de builds que pasan sin retrabajo)

Agrega 3 KPIs adicionales que consideres relevantes para un proyecto ERP cloud. 
Responde en español con la tabla completa.
```

3. Revisa la tabla generada. Luego copia y pega el **Prompt 2.2 — Estructura del tablero Excel:**

```
Excelente. Ahora necesito que me des instrucciones detalladas para construir un tablero 
de KPIs en Microsoft Excel con los KPIs que definiste. Especifica:

1. ESTRUCTURA DE HOJAS:
   - Nombre de cada hoja y su propósito

2. HOJA "DATOS_KPI": 
   - Estructura de columnas para registrar mediciones semanales durante 8 semanas
   - Incluye datos simulados para las primeras 4 semanas (inventa valores realistas 
     para un proyecto ERP en fase inicial de testing)

3. HOJA "DASHBOARD":
   - Qué gráficos incluir (tipo de gráfico, datos que muestra, título)
   - Qué indicadores visuales usar (semáforos, tendencias)

4. FÓRMULAS CLAVE:
   - Escribe las fórmulas de Excel para calcular: Defect Density, Test Coverage, 
     MTTD y ROI del Testing con IA

Responde en español con el detalle suficiente para que yo pueda construir el tablero.
```

4. Con base en las instrucciones de Copilot, construye el tablero en tu archivo Excel `02-KPIs-Dashboard-CorpERP3.xlsx`:

   a. Crea las hojas indicadas por Copilot (típicamente: `Definiciones_KPI`, `Datos_KPI`, `Dashboard`).
   
   b. En la hoja `Definiciones_KPI`, copia la tabla de KPIs completa del Prompt 2.1.
   
   c. En la hoja `Datos_KPI`, crea la estructura de columnas e ingresa los datos simulados de las 4 semanas.
   
   d. Ingresa las fórmulas indicadas por Copilot para los 4 KPIs calculados.

5. Para la hoja `Dashboard`, usa el **Prompt 2.3 — Datos para visualización:**

```
Dame una tabla de datos simulados adicional para el dashboard que muestre la comparación 
de velocidad de generación de casos de prueba CON Copilot vs SIN Copilot durante 8 semanas. 
Usa valores realistas que muestren una mejora progresiva del 30-40% con IA. 
Formato: tabla con columnas Semana, Casos_Sin_IA, Casos_Con_IA, Porcentaje_Mejora.
Responde en español.
```

6. Copia estos datos en una nueva tabla en la hoja `Dashboard` de Excel e inserta un gráfico de líneas comparativo.

7. Guarda el archivo Excel en OneDrive.

#### Resultado Esperado

Un libro Excel con:
- Hoja `Definiciones_KPI` con tabla completa de 13 KPIs (10 solicitados + 3 adicionales)
- Hoja `Datos_KPI` con datos simulados de 4 semanas y fórmulas calculadas
- Hoja `Dashboard` con al menos un gráfico de comparación Con IA vs Sin IA
- Fórmulas funcionales para Defect Density, Test Coverage, MTTD y ROI

#### Verificación

- [ ] El libro Excel tiene al menos 3 hojas con nombres descriptivos
- [ ] La tabla de KPIs contiene las 10 métricas obligatorias más al menos 3 adicionales
- [ ] Existen datos simulados para al menos 4 semanas en la hoja de datos
- [ ] Al menos una fórmula de cálculo está implementada y funcional
- [ ] El gráfico comparativo Con IA vs Sin IA está presente en el Dashboard
- [ ] El archivo está guardado en OneDrive en la carpeta `Lab-01-00-01-STLC-IA`

---

### Paso 3 — Creación del Plan de Pruebas Estructurado (STLC Completo)

**Objetivo:** Generar un plan de pruebas profesional que cubra todas las fases del STLC con criterios de entrada/salida por fase, utilizando Copilot Chat con prompts encadenados.

#### Instrucciones

1. En Copilot Chat, inicia una **nueva conversación**.

2. Establece el contexto con el **Prompt 3.1 — Contexto y estructura del plan:**

```
Actúa como un QA Manager con experiencia en proyectos ERP y metodologías ágiles. 
Voy a pedirte que construyas un Plan de Pruebas completo para el proyecto ficticio 
CorpERP 3.0 (migración ERP cloud para Corporación Nexus S.A., 8 meses, 6 QA engineers, 
módulos: Finanzas, RRHH, Cadena de Suministro, Reportería).

El plan debe seguir el estándar IEEE 829 adaptado y cubrir las siguientes fases del STLC:
1. Análisis de Requisitos de Prueba
2. Planificación de Pruebas
3. Diseño de Casos de Prueba
4. Preparación de Datos y Entornos
5. Ejecución de Pruebas
6. Reporte y Triage de Defectos
7. Cierre y Mejora Continua

Para CADA fase incluye:
- Objetivo de la fase
- Actividades principales (mínimo 3 por fase)
- Criterios de ENTRADA (qué debe estar listo para iniciar la fase)
- Criterios de SALIDA (qué debe completarse para cerrar la fase)
- Rol de Copilot Chat / IA en esta fase (qué tipo de prompt o asistencia se utilizará)
- Entregables de la fase

Usa formato de tabla para los criterios de entrada/salida. Responde en español.
```

3. Después de recibir la respuesta, aplica el **Prompt 3.2 — Sección de estrategia de riesgos:**

```
El plan va muy bien. Ahora agrega las siguientes secciones complementarias:

SECCIÓN A: ESTRATEGIA DE TESTING POR MÓDULO
Crea una tabla que muestre para cada módulo de CorpERP 3.0 (Finanzas, RRHH, 
Cadena de Suministro, Reportería):
- Nivel de criticidad (Alto/Medio/Bajo)
- Tipos de prueba aplicables (funcional, integración, rendimiento, seguridad, UAT)
- Porcentaje estimado de automatización
- Enfoque de IA (qué usará Copilot en ese módulo)

SECCIÓN B: MATRIZ DE TRAZABILIDAD (EJEMPLO)
Genera un ejemplo de matriz de trazabilidad con 5 requisitos ficticios del módulo 
de Finanzas, mostrando su relación con casos de prueba (IDs ficticios) y el estado 
de cobertura.

SECCIÓN C: CRONOGRAMA DE ALTO NIVEL
Tabla con las 8 semanas del proyecto, las fases STLC activas por semana y los hitos 
de entrega principales.

Responde en español con formato profesional.
```

4. Aplica el **Prompt 3.3 — Criterios de aceptación y definición de "done":**

```
Para completar el plan, necesito:

1. DEFINICIÓN DE "DONE" PARA TESTING: Define qué significa que un módulo está 
   "listo para go-live" desde la perspectiva de QA. Incluye criterios cuantitativos 
   (porcentajes, umbrales) y cualitativos.

2. PLAN DE COMUNICACIÓN DE DEFECTOS: Describe cómo se reportarán los defectos, 
   qué niveles de severidad se usarán (con definición de cada uno) y cuál es el 
   SLA de resolución por nivel.

3. POLÍTICA DE RETESTING Y REGRESIÓN: Cuándo se hace retesting, cuándo se ejecuta 
   regresión completa vs. regresión mínima asistida por IA.

Responde en español con formato de documento profesional.
```

5. Consolida las tres respuestas en tu documento Word `03-Plan-Pruebas-CorpERP3.docx`. Aplica estilos de encabezado para estructurar las secciones. Asegúrate de que el documento tenga una página de portada con: nombre del proyecto, versión (v1.0), fecha y nombre del autor (puedes usar un nombre ficticio).

6. Guarda el documento en OneDrive.

#### Resultado Esperado

Un documento Word de plan de pruebas de aproximadamente 6–10 páginas que contenga:
- Las 7 fases del STLC con criterios de entrada/salida en tabla
- Estrategia de testing por módulo (tabla con 4 módulos)
- Ejemplo de matriz de trazabilidad (5 requisitos)
- Cronograma de 8 semanas
- Definición de "done", plan de comunicación de defectos y política de regresión

#### Verificación

- [ ] El documento cubre las 7 fases del STLC
- [ ] Cada fase tiene criterios de entrada Y salida en formato tabla
- [ ] Cada fase incluye el rol explícito de Copilot/IA
- [ ] La sección de estrategia por módulo cubre los 4 módulos de CorpERP 3.0
- [ ] Existe una definición de "done" con criterios cuantitativos
- [ ] El documento tiene portada con metadatos del proyecto
- [ ] Archivo guardado en OneDrive en la carpeta `Lab-01-00-01-STLC-IA`

---

### Paso 4 — Guía de Mejores Prácticas para Adopción de IA en Testing

**Objetivo:** Generar una guía de mejores prácticas aplicable al contexto organizacional, que sintetice las lecciones aprendidas del laboratorio y las recomendaciones del STLC asistido por IA.

#### Instrucciones

1. En Copilot Chat, inicia una **nueva conversación**.

2. Usa el **Prompt 4.1 — Generación de la guía de mejores prácticas:**

```
Actúa como un consultor experto en transformación digital y calidad de software. 
Necesito una Guía de Mejores Prácticas para la Adopción de IA (específicamente 
Microsoft 365 Copilot Chat) en el ciclo de vida de testing de software (STLC) 
en organizaciones corporativas medianas y grandes.

La guía debe incluir:

1. INTRODUCCIÓN: Por qué integrar IA en el STLC (beneficios cuantificables y cualitativos)

2. PRINCIPIOS FUNDAMENTALES (mínimo 5):
   - Cada principio con nombre, descripción y ejemplo práctico de aplicación

3. MEJORES PRÁCTICAS POR FASE STLC:
   Para cada fase (Análisis, Planificación, Diseño, Datos/Entornos, Ejecución, 
   Reporte/Triage, Cierre), lista 3 mejores prácticas específicas para el uso de 
   Copilot Chat, con la práctica, el beneficio esperado y el riesgo a evitar.

4. ANTIPATRONES A EVITAR (mínimo 5):
   Qué NO hacer cuando se usa IA en testing, con descripción del problema y 
   la consecuencia negativa.

5. FRAMEWORK DE GOBERNANZA:
   - Políticas de trazabilidad de artefactos generados por IA
   - Proceso de revisión y aprobación humana
   - Métricas de calidad de la IA (acceptance rate, defectos escapados)

6. PLANTILLAS DE PROMPTS RECOMENDADAS:
   Proporciona 5 prompts plantilla (con variables en [CORCHETES]) para las fases 
   más críticas del STLC.

Responde en español con formato de guía profesional.
```

3. Una vez recibida la respuesta, aplica el **Prompt 4.2 — Sección de madurez y roadmap:**

```
Agrega dos secciones finales a la guía:

SECCIÓN: MODELO DE MADUREZ DE IA EN TESTING
Crea un modelo de madurez de 4 niveles para la adopción de IA en testing:
- Nivel 1: Inicial (descripción, características, indicadores)
- Nivel 2: En desarrollo (descripción, características, indicadores)
- Nivel 3: Definido (descripción, características, indicadores)
- Nivel 4: Optimizado (descripción, características, indicadores)
Para cada nivel incluye qué capacidades de Copilot se utilizan y qué KPIs son típicos.

SECCIÓN: ROADMAP DE ADOPCIÓN (90 DÍAS)
Tabla con hitos para los primeros 90 días de adopción de IA en un equipo de QA:
- Días 1-30: Fundamentos y primeros usos
- Días 31-60: Expansión y métricas
- Días 61-90: Optimización y gobernanza
Para cada período: actividades clave, herramientas, métricas de éxito.

Responde en español.
```

4. Realiza un último ciclo de refinamiento con el **Prompt 4.3 — Personalización y cierre:**

```
Para cerrar la guía, agrega:

1. Una sección "CHECKLIST DE PREPARACIÓN ORGANIZACIONAL" con 10 preguntas que un 
   equipo de QA debe responder antes de adoptar IA en su STLC. Formato de checklist 
   con casillas ([ ] Sí / [ ] No / [ ] En progreso).

2. Un resumen ejecutivo de máximo 200 palabras que pueda compartirse con liderazgo 
   no técnico para justificar la adopción de IA en testing.

Responde en español.
```

5. Consolida las tres respuestas en tu documento Word `04-Guia-MejoresPracticas-IA-Testing.docx`. Aplica formato profesional con tabla de contenidos (puedes usar la función de tabla de contenidos automática de Word basada en los estilos de encabezado).

6. Guarda el documento en OneDrive.

#### Resultado Esperado

Un documento Word de guía de mejores prácticas de aproximadamente 5–8 páginas que contenga:
- 5+ principios fundamentales con ejemplos
- Mejores prácticas por cada fase STLC (3 prácticas × 7 fases = 21 prácticas)
- 5+ antipatrones documentados
- Framework de gobernanza con políticas y métricas
- 5 plantillas de prompts con variables en corchetes
- Modelo de madurez de 4 niveles
- Roadmap de 90 días en tabla
- Checklist de 10 preguntas y resumen ejecutivo

#### Verificación

- [ ] El documento contiene las 8 secciones principales solicitadas
- [ ] Las plantillas de prompts tienen variables en [CORCHETES] y son reutilizables
- [ ] El modelo de madurez tiene 4 niveles con indicadores medibles
- [ ] El checklist tiene exactamente 10 preguntas con opciones Sí/No/En progreso
- [ ] El resumen ejecutivo es comprensible para audiencia no técnica
- [ ] El documento tiene tabla de contenidos
- [ ] Archivo guardado en OneDrive en la carpeta `Lab-01-00-01-STLC-IA`

---

## 7. Validación y Evaluación Final

Al completar los 4 pasos del laboratorio, realiza la siguiente validación integral:

### Lista de verificación final de artefactos

Confirma que tienes los siguientes 4 archivos guardados en tu carpeta `Lab-01-00-01-STLC-IA` en OneDrive:

| Artefacto | Archivo | Criterio de calidad mínimo |
|---|---|---|
| Documento de Alcance | `01-Alcance-CorpERP3.docx` | 7 secciones, tabla de riesgos con 6+ entradas, estrategia IA incluida |
| Tablero de KPIs | `02-KPIs-Dashboard-CorpERP3.xlsx` | 3 hojas, 13+ KPIs definidos, datos simulados 4 semanas, 1+ gráfico |
| Plan de Pruebas | `03-Plan-Pruebas-CorpERP3.docx` | 7 fases STLC, criterios entrada/salida, portada, cronograma 8 semanas |
| Guía de Mejores Prácticas | `04-Guia-MejoresPracticas-IA-Testing.docx` | 8 secciones, 5+ plantillas de prompts, modelo madurez, roadmap 90 días |

### Ejercicio de reflexión (5 minutos)

Abre una nueva conversación en Copilot Chat y usa el siguiente prompt de autoevaluación:

```
Actúa como un evaluador de calidad de artefactos de testing. Voy a describirte los 
artefactos que generé en un laboratorio de STLC asistido por IA y necesito que me 
ayudes a identificar:
1. Qué elementos podrían mejorarse en cada artefacto
2. Qué preguntas debería hacerme para evaluar si los artefactos son adecuados 
   para un proyecto ERP real
3. Cómo mediría el impacto de haber usado IA vs no haberla usado en la generación 
   de estos documentos

Los artefactos que generé son: (1) Documento de alcance con identificación de riesgos, 
(2) Tablero de KPIs con 13 métricas, (3) Plan de pruebas STLC completo, 
(4) Guía de mejores prácticas con modelo de madurez.

Responde en español con análisis crítico constructivo.
```

Documenta las observaciones de Copilot en un archivo de texto o en una nota al final de cualquiera de tus documentos Word. Esta reflexión forma parte de la evaluación del laboratorio.

### Criterios de evaluación del laboratorio

| Criterio | Peso | Indicadores |
|---|---|---|
| **Completitud de artefactos** | 30% | Los 4 artefactos están presentes y contienen todas las secciones solicitadas |
| **Calidad del prompt engineering** | 25% | Evidencia de al menos 2 ciclos de refinamiento iterativo por artefacto |
| **Profundidad técnica** | 25% | Los artefactos demuestran comprensión del STLC, KPIs y mejores prácticas de IA |
| **Aplicabilidad práctica** | 20% | Los artefactos son utilizables en un proyecto real con ajustes mínimos |

---

## 8. Resolución de Problemas

### Problema 1 — Copilot genera respuestas en inglés o cambia de idioma a mitad de la conversación

**Síntomas:**
- Las respuestas de Copilot Chat aparecen total o parcialmente en inglés.
- Al continuar la conversación, el idioma cambia inconsistentemente.
- Las tablas o secciones técnicas aparecen en inglés aunque el texto narrativo esté en español.

**Causa:**
Copilot es un modelo multilingüe que puede cambiar de idioma cuando detecta términos técnicos en inglés en los prompts (como "STLC", "KPI", "ROI") o cuando el contexto de la conversación acumula suficiente texto en inglés para inclinar el modelo hacia ese idioma. Esto es un comportamiento normal del modelo de lenguaje, no un error de configuración.

**Solución:**
1. Agrega la instrucción de idioma **al inicio y al final** de cada prompt: `"Responde siempre en español, incluyendo tablas, encabezados y términos técnicos cuando tengan traducción aceptada."`
2. Si el problema persiste en una conversación larga, inicia una **nueva conversación** y reestablece el contexto con el prompt de rol (Prompt 1.1, 2.1, etc.) incluyendo la instrucción de idioma desde el primer mensaje.
3. Si una respuesta específica está en inglés, usa este follow-up prompt inmediato: `"Traduce tu respuesta anterior al español manteniendo exactamente la misma estructura, tablas y contenido."`
4. Para conversaciones largas, agrega periódicamente el recordatorio: `"Recuerda responder siempre en español."`

---

### Problema 2 — Las respuestas de Copilot son demasiado genéricas o no se alinean al contexto del proyecto CorpERP 3.0

**Síntomas:**
- Copilot genera artefactos con ejemplos de proyectos genéricos (e.g., "sistema de e-commerce", "aplicación web") en lugar de referencias al ERP ficticio.
- Las tablas de riesgos o KPIs contienen valores placeholder como "Módulo X" o "Sistema Y".
- El plan de pruebas no menciona los módulos específicos (Finanzas, RRHH, Cadena de Suministro, Reportería).
- Las respuestas son superficiales, con listas de 2–3 elementos cuando se solicitaron 6+.

**Causa:**
Este problema ocurre cuando el contexto del proyecto no se establece adecuadamente al inicio de la conversación, cuando se inicia una nueva conversación sin reintroducir el contexto, o cuando el prompt no es suficientemente específico en cuanto a la cantidad y detalle requeridos. Copilot no tiene memoria entre conversaciones distintas.

**Solución:**
1. **Siempre** inicia cada nueva conversación con el prompt de contexto completo (similar al Prompt 1.1) antes de hacer solicitudes específicas. No asumas que Copilot recuerda conversaciones anteriores.
2. Sé explícito en la cantidad: en lugar de "lista riesgos", escribe "lista exactamente 6 riesgos específicos para un proyecto de migración ERP cloud con los módulos Finanzas, RRHH, Cadena de Suministro y Reportería".
3. Si la respuesta es genérica, usa este follow-up: `"La respuesta es demasiado genérica. Reescríbela usando exclusivamente el contexto de CorpERP 3.0 (migración ERP cloud para Corporación Nexus S.A.) y menciona explícitamente los módulos Finanzas, RRHH, Cadena de Suministro y Reportería en ejemplos concretos."`
4. Proporciona ejemplos en el prompt: "Por ejemplo, para el módulo de Finanzas, un riesgo sería..." para anclar el nivel de especificidad esperado.
5. Divide prompts muy largos en prompts más pequeños y secuenciales, confirmando que cada respuesta es satisfactoria antes de avanzar.

---

## 9. Limpieza del Entorno

Al finalizar el laboratorio, realiza los siguientes pasos de cierre:

### Guardar y organizar artefactos finales

1. Verifica que los 4 archivos estén guardados en OneDrive en la carpeta `Lab-01-00-01-STLC-IA`:
   - `01-Alcance-CorpERP3.docx`
   - `02-KPIs-Dashboard-CorpERP3.xlsx`
   - `03-Plan-Pruebas-CorpERP3.docx`
   - `04-Guia-MejoresPracticas-IA-Testing.docx`

2. Agrega la fecha de creación al nombre de cada archivo si tu instructor lo requiere:
   - Ejemplo: `01-Alcance-CorpERP3-YYYYMMDD.docx`

3. Comparte la carpeta `Lab-01-00-01-STLC-IA` con tu instructor a través de OneDrive (clic derecho → Compartir → ingresar el correo del instructor con permisos de **solo lectura**).

### Cerrar sesiones de Copilot Chat

1. En [copilot.microsoft.com](https://copilot.microsoft.com), cierra todas las conversaciones abiertas haciendo clic en el ícono de historial y eliminando las conversaciones del laboratorio si contienen información que no deseas conservar.

   > ⚠️ **Recordatorio de privacidad:** Aunque este laboratorio usa datos ficticios, es buena práctica limpiar el historial de Copilot Chat al finalizar sesiones de trabajo.

2. Cierra las pestañas del navegador relacionadas con Copilot Chat.

### Notas sobre retención de artefactos

- Los artefactos generados en este laboratorio (documentos Word y Excel) son **propiedad del participante** y pueden adaptarse para uso real en sus proyectos, siempre que se reemplacen los datos ficticios por información real de sus proyectos.
- Las plantillas de prompts de la Guía de Mejores Prácticas son especialmente valiosas para reutilización futura; considera guardarlas en un repositorio de QA de tu equipo.
- No es necesario eliminar los archivos de OneDrive a menos que tu instructor lo indique; estos artefactos serán referenciados en laboratorios posteriores del curso.

---

## 10. Resumen y Recursos Adicionales

### Lo que lograste en este laboratorio

En este laboratorio de 60 minutos aplicaste Microsoft 365 Copilot Chat para construir **cuatro artefactos profesionales** que demuestran la integración práctica de IA conversacional en las fases tempranas del STLC:

| Artefacto | Habilidad demostrada | Concepto STLC aplicado |
|---|---|---|
| Documento de Alcance | Prompt engineering con rol y contexto | Análisis de requisitos de prueba + identificación de riesgos |
| Tablero de KPIs | Prompts para estructuras tabulares y datos simulados | Métricas de calidad (ISO/IEC 25010, IEEE 829) |
| Plan de Pruebas STLC | Prompts encadenados y refinamiento iterativo | Planificación y diseño de pruebas (7 fases completas) |
| Guía de Mejores Prácticas | Síntesis y estructuración de conocimiento experto | Gobernanza de IA, modelo de madurez, roadmap de adopción |

### Conceptos clave reforzados

- **El STLC moderno es continuo**, no lineal; la IA conversacional añade valor en todas sus fases, desde la comprensión de requisitos hasta el cierre y las lecciones aprendidas.
- **El prompt engineering iterativo** es la habilidad central: el primer resultado de Copilot es un punto de partida, no el producto final. La calidad del artefacto final depende de la capacidad de refinar el prompt.
- **La gobernanza es no negociable**: trazabilidad de artefactos generados por IA, revisión humana obligatoria y métricas de calidad de la IA (acceptance rate, defectos escapados) son pilares de una adopción responsable.
- **Los KPIs de testing con IA** deben incluir tanto métricas tradicionales (Defect Density, Test Coverage, MTTD) como métricas específicas de IA (AI Suggestion Acceptance Rate, Test Case Generation Velocity con/sin IA, ROI del testing asistido).

### Conexión con el siguiente laboratorio

Los artefactos generados en este laboratorio (especialmente el Plan de Pruebas y el Tablero de KPIs) serán utilizados como base en el **Laboratorio 01-00-02**, donde profundizarás en el diseño de casos de prueba asistido por IA y la generación de datos sintéticos de prueba para el proyecto CorpERP 3.0.

### Recursos adicionales recomendados

| Recurso | Tipo | Relevancia |
|---|---|---|
| [ISTQB: AI Testing Certification](https://www.istqb.org/certifications/certified-tester-ai-testing/) | Certificación | Marco de referencia para testing con IA |
| [IEEE 829-2008: Test Documentation Standard](https://standards.ieee.org/standard/829-2008.html) | Estándar | Base para el plan de pruebas generado |
| [ISO/IEC 25010:2023 — Software Quality Model](https://www.iso.org/standard/78176.html) | Estándar | Referencia para los KPIs de calidad del producto |
| [Microsoft Copilot: Documentación oficial](https://learn.microsoft.com/en-us/copilot/microsoft-365/) | Documentación | Capacidades y límites de Microsoft 365 Copilot |
| [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework) | Framework | Gobernanza y gestión de riesgos de IA |
| [Azure DevOps: Test Impact Analysis](https://learn.microsoft.com/azure/devops/pipelines/test/test-impact-analysis) | Documentación técnica | Implementación de TIA en pipelines CI/CD |
| [Software Engineering at Google — Testing](https://abseil.io/resources/swe-book/html/ch11.html) | Libro técnico | Perspectiva de escala en testing de software |

---

> 📝 **Nota final para el instructor:** Este laboratorio está diseñado para ser completado en 60 minutos por un participante con conocimiento básico del STLC. Si el grupo tiene menor experiencia con prompt engineering, se recomienda dedicar los primeros 10 minutos a revisar los prompts del Paso 1 en conjunto antes de que los participantes trabajen de forma independiente. Los artefactos generados variarán entre participantes debido a la naturaleza estocástica del modelo; la evaluación debe centrarse en la estructura, completitud y calidad del proceso de refinamiento, no en replicar una salida exacta.
