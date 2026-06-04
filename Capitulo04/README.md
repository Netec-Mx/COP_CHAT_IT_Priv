# Creación de bases de conocimiento Inteligentes, soluciones de autoservicio y gestión de casos típicos de Service Desk con IA

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 60 minutos |
| **Complejidad** | Media |
| **Nivel Bloom** | Crear |
| **Módulo** | 4 — Service Desk Inteligente con Microsoft 365 Copilot |
| **Laboratorio ID** | 04-00-01 |
| **Versión del documento** | 1.0 |

---

## 2. Descripción General

En este laboratorio los participantes construirán una solución completa de gestión del conocimiento para Service Desk aplicando Microsoft 365 Copilot como motor de generación, estructuración y análisis de contenido. Siguiendo los principios de la lección 4.1 —autoservicio inteligente, agentes aumentados y orquestación end-to-end— se producirán artefactos concretos: una base de conocimiento en Word, flujos de autoservicio conversacionales, respuestas estandarizadas a casos típicos y un tablero de impacto en Excel. El laboratorio cierra el ciclo del curso conectando la gestión del conocimiento con la transformación operativa del Service Desk, alineado con el marco ITIL v4 y la metodología KCS (Knowledge-Centered Service).

---

## 3. Objetivos de Aprendizaje

Al finalizar este laboratorio, el participante será capaz de:

- [ ] **Construir** una base de conocimiento estructurada en Word con artículos de solución para los 10 casos más frecuentes de Service Desk, utilizando Copilot para generar contenido alineado con la metodología KCS.
- [ ] **Diseñar** flujos de autoservicio conversacionales (árboles de decisión) para los 3 casos más frecuentes, documentando preguntas de diagnóstico, respuestas posibles y acciones recomendadas en cada rama.
- [ ] **Gestionar** y documentar casos típicos de Service Desk generando respuestas estandarizadas, instrucciones técnicas y comunicaciones al usuario final en tono profesional y empático con apoyo de Copilot.
- [ ] **Evaluar** el impacto potencial de la base de conocimiento inteligente en métricas operativas clave (FCR, AHT, CSAT) mediante un tablero de análisis con escenarios en Excel.

---

## 4. Prerrequisitos

### 4.1 Conocimientos Previos

| Área | Nivel requerido |
|---|---|
| Operaciones básicas de Service Desk (tipos de solicitudes, niveles N1/N2) | Básico |
| Concepto de base de conocimiento (KB) y su rol en ITSM | Básico |
| Métricas de Service Desk: FCR, AHT, SLA, CSAT | Básico |
| Uso de Copilot Chat para generación de artefactos técnicos | Intermedio |
| Laboratorios 1, 2 y 3 del curso (o experiencia equivalente) | Completados |
| Revisión de los materiales teóricos de los temas 4.1 y 4.2 | Completada |

### 4.2 Acceso y Licencias

| Recurso | Estado requerido |
|---|---|
| Cuenta corporativa Microsoft 365 con licencia **Copilot activa** | ✅ Verificado |
| Acceso a [copilot.microsoft.com](https://copilot.microsoft.com) | ✅ Funcional |
| Microsoft Word (Online o Desktop) | ✅ Disponible |
| Microsoft Excel (Online o Desktop) | ✅ Disponible |
| OneDrive con espacio disponible (mínimo 100 MB) | ✅ Disponible |

> ⚠️ **IMPORTANTE:** Si al abrir [copilot.microsoft.com](https://copilot.microsoft.com) no aparece el ícono de Copilot con tu cuenta corporativa, detente y contacta al instructor antes de continuar. Sin licencia activa, ninguna actividad es ejecutable.

---

## 5. Entorno de Laboratorio

### 5.2 Software Requerido

| Aplicación | Versión mínima | Uso en el laboratorio |
|---|---|---|
| Microsoft Edge o Google Chrome | 120+ | Acceso a Copilot Chat y Microsoft 365 Online |
| Microsoft 365 Copilot Chat | Actual (SaaS) | Generación de todos los artefactos |
| Microsoft Word (Online/Desktop) | Microsoft 365 actual | Base de conocimiento y documentación de casos |
| Microsoft Excel (Online/Desktop) | Microsoft 365 actual | Tablero de análisis de impacto en métricas |

### 5.3 Configuración Inicial del Entorno

Antes de comenzar las actividades, completa los siguientes pasos de preparación:

**Paso A — Verificar acceso a Copilot:**
1. Abre tu navegador y navega a [https://copilot.microsoft.com](https://copilot.microsoft.com).
2. Inicia sesión con tu cuenta corporativa Microsoft 365.
3. Verifica que aparezca el mensaje de bienvenida con tu nombre y el indicador de **"Trabajo"** (Work) activo en la parte superior.
4. Escribe el siguiente prompt de prueba y confirma que obtienes respuesta coherente:

```
Hola Copilot. Responde siempre en español. 
Confirma que tienes acceso a mi contexto corporativo escribiendo: 
"Listo para el laboratorio de Service Desk."
```

**Paso B — Crear carpeta de trabajo en OneDrive:**
1. Abre [https://onedrive.live.com](https://onedrive.live.com) o el cliente de OneDrive.
2. Crea una carpeta llamada: `Lab04-ServiceDesk-KB`
3. Dentro de esa carpeta, crea dos subcarpetas: `Artefactos` y `Capturas`

**Paso C — Abrir documentos base:**
1. Crea un nuevo documento de **Word** en blanco dentro de `Lab04-ServiceDesk-KB/Artefactos` y nómbralo: `KB-ServiceDesk-[TuNombre].docx`
2. Crea un nuevo libro de **Excel** en blanco en la misma carpeta y nómbralo: `Dashboard-Metricas-[TuNombre].xlsx`
3. Mantén ambos documentos abiertos durante todo el laboratorio.

> 💡 **Recordatorio:** Copilot Chat no guarda el historial de conversaciones de forma permanente. Copia los resultados satisfactorios a tus documentos Word/Excel inmediatamente después de generarlos.

---

## 6. Procedimiento Paso a Paso

El laboratorio está dividido en **4 actividades principales**. 

---

### Actividad 1: Construcción de la Base de Conocimiento (KB)

**Objetivo de la actividad:** Generar un conjunto de artículos de conocimiento estructurados para los 10 casos más frecuentes de Service Desk, aplicando la metodología KCS y el concepto de grounding del contenido corporativo visto en la lección 4.1.

---

#### Paso 1.1 — Generar la estructura maestra de la KB

**Objetivo:** Establecer la plantilla estándar KCS que se usará para todos los artículos de la base de conocimiento.

**Instrucciones:**

1. Abre [https://copilot.microsoft.com](https://copilot.microsoft.com) y asegúrate de estar en modo **"Trabajo"**.
2. Copia y pega el siguiente prompt en Copilot Chat:

```
Actúa como un especialista en ITSM con experiencia en metodología KCS 
(Knowledge-Centered Service) e ITIL v4. 

Crea una plantilla estándar en español para artículos de base de conocimiento 
de Service Desk que incluya los siguientes campos obligatorios:
1. ID del artículo (formato: KB-XXXX)
2. Título descriptivo del problema
3. Categoría y subcategoría
4. Descripción del problema (2-3 oraciones)
5. Síntomas observables (lista con viñetas)
6. Pasos de resolución (numerados, paso a paso)
7. Notas de escalación (cuándo y a quién escalar)
8. Palabras clave para búsqueda (mínimo 5)
9. Propietario del artículo y fecha de revisión
10. Nivel de resolución (N1 / N2 / N3)

Presenta la plantilla en formato Markdown con secciones claramente 
delimitadas. Responde siempre en español.
```

3. Espera la respuesta de Copilot.
4. Si la respuesta está en inglés, añade el siguiente follow-up prompt:

```
Por favor, traduce toda la plantilla al español y mantenla en formato Markdown.
```

**Resultado esperado:** Una plantilla Markdown estructurada con los 10 campos KCS, lista para ser replicada en cada artículo.

---

#### Paso 1.2 — Generar los 10 artículos de conocimiento

**Objetivo:** Crear artículos completos para los 10 casos más frecuentes de Service Desk usando la plantilla KCS generada.

**Instrucciones:**

1. Usando la plantilla del paso anterior como referencia, escribe el siguiente prompt en Copilot Chat:

```
Usando la plantilla KCS que acabas de crear, genera artículos de base de 
conocimiento completos para los siguientes 10 casos frecuentes de Service Desk 
en una empresa corporativa mediana (500-1000 empleados):

1. Restablecimiento de contraseña de Active Directory
2. Problemas de conexión VPN (cliente no puede conectarse)
3. Configuración de correo corporativo en dispositivo móvil (Outlook)
4. Impresora de red no encontrada o sin respuesta
5. Acceso denegado a aplicación corporativa (ERP/CRM)
6. Microsoft Teams no carga o presenta errores de inicio
7. Computadora lenta o con alto consumo de CPU/RAM
8. Solicitud de instalación de software aprobado
9. Problemas con Microsoft 365 (Word/Excel no abre o se cierra)
10. Acceso a SharePoint/OneDrive bloqueado o sin permisos

Para cada artículo:
- Usa la plantilla KCS con todos los campos
- Asigna IDs del KB-0001 al KB-0010
- Incluye mínimo 5 pasos de resolución concretos y accionables
- Especifica claramente cuándo escalar a N2 o N3
- El nivel de resolución debe ser N1 para los casos 1, 2, 3, 4, 6, 7, 8, 9 
  y N2 para los casos 5 y 10
- Tono técnico pero comprensible para agentes N1

Genera los artículos del KB-0001 al KB-0005 primero. 
Responde siempre en español.
```

2. Espera la respuesta y **cópiala inmediatamente** a tu documento Word `KB-ServiceDesk-[TuNombre].docx`.
3. Escribe el siguiente follow-up prompt para los artículos restantes:

```
Excelente. Ahora genera los artículos KB-0006 al KB-0010 con el mismo 
nivel de detalle y usando la misma plantilla KCS. 
Responde siempre en español.
```

4. Copia también estos artículos al documento Word.

5. Usa el siguiente prompt de refinamiento para mejorar cualquier artículo que consideres incompleto:

```
Revisa el artículo KB-0002 (Problemas de conexión VPN) y añade:
- Un paso de diagnóstico inicial para verificar si el problema es 
  de credenciales, conectividad de red o configuración del cliente VPN
- Una nota específica sobre cómo crear el incidente en el sistema ITSM 
  si no se resuelve en N1, incluyendo los campos obligatorios a completar
- Dos palabras clave adicionales relacionadas con troubleshooting de red

Responde siempre en español.
```

**Resultado esperado:** 10 artículos de conocimiento completos en formato KCS, con todos los campos requeridos, guardados en el documento Word.

---

#### Paso 1.3 — Estructurar y dar formato a la KB en Word

**Objetivo:** Organizar los artículos en un documento Word profesional con tabla de contenido y secciones por categoría.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt para obtener la estructura del documento:

```
Crea una página de portada y un índice de contenidos para una Base de 
Conocimiento de Service Desk corporativo que contenga los 10 artículos 
KB-0001 al KB-0010 que generamos.

La portada debe incluir:
- Título: "Base de Conocimiento - Service Desk Corporativo"
- Subtítulo: "Versión 1.0 | Clasificación: Uso Interno"
- Fecha: [mes y año actual]
- Una breve descripción del propósito (2-3 oraciones) basada en 
  metodología KCS e ITIL v4

El índice debe organizar los artículos en estas categorías:
- Gestión de Identidad y Accesos (KB-0001, KB-0005, KB-0010)
- Conectividad y Red (KB-0002, KB-0004)
- Productividad y Aplicaciones Microsoft 365 (KB-0003, KB-0006, KB-0009)
- Hardware y Rendimiento (KB-0007)
- Gestión de Software (KB-0008)

Responde siempre en español.
```

2. Copia el resultado al inicio de tu documento Word.
3. Añade manualmente los artículos generados en los pasos anteriores bajo sus categorías correspondientes.
4. Guarda el documento en OneDrive.

**Resultado esperado:** Documento Word con 10 artículos KCS organizados por categoría.

---

### Actividad 2: Diseño de Flujos de Autoservicio Conversacional

**Objetivo de la actividad:** Diseñar los guiones de flujos de autoservicio conversacionales (árboles de decisión) para los 3 casos más frecuentes, aplicando el concepto de shift-left y detección de intención visto en la lección 4.1.

---

#### Paso 2.1 — Generar el árbol de decisión para el caso de VPN

**Objetivo:** Crear el flujo conversacional completo para el caso de conexión VPN, el más crítico en entornos de trabajo remoto.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Actúa como un arquitecto de experiencia de usuario especializado en 
flujos conversacionales para Service Desk con IA (Virtual Agent).

Diseña un árbol de decisión conversacional completo en español para 
el caso: "El usuario no puede conectarse a la VPN corporativa".

El flujo debe:
1. Comenzar con un saludo empático y la pregunta de diagnóstico inicial
2. Tener al menos 3 niveles de profundidad en el árbol
3. Cubrir estos escenarios de causa raíz:
   a) Credenciales incorrectas o contraseña expirada
   b) Cliente VPN desactualizado o con error de configuración
   c) Problema de conectividad de red local (WiFi/cable)
   d) Bloqueo por política de seguridad (MFA pendiente)
4. Para cada rama, incluir:
   - Pregunta de diagnóstico al usuario (texto exacto del bot)
   - Opciones de respuesta del usuario (Sí/No o múltiple opción)
   - Acción recomendada o instrucción paso a paso
   - Criterio de escalación a agente humano N1
5. Terminar cada rama con: resolución autónoma, escalación a N1, 
   o creación automática de ticket

Presenta el árbol en formato de tabla o diagrama textual con 
indentación para mostrar la jerarquía. Responde siempre en español.
```

2. Copia el resultado al documento Word en una nueva sección llamada **"Sección 2: Flujos de Autoservicio"**.

**Resultado esperado:** Árbol de decisión con al menos 3 niveles, 4 ramas de causa raíz y criterios de escalación claros.

---

#### Paso 2.2 — Generar flujos para restablecimiento de contraseña y Microsoft Teams

**Objetivo:** Completar los flujos de autoservicio para los otros 2 casos prioritarios.

**Instrucciones:**

1. Escribe el siguiente prompt para el caso de contraseñas:

```
Usando el mismo formato del árbol de decisión anterior, diseña el 
flujo conversacional para: "El usuario olvidó su contraseña de 
Active Directory y no puede iniciar sesión".

Considera estos escenarios:
a) Usuario tiene MFA configurado y puede hacer reset autónomo
b) Usuario no tiene MFA y necesita verificación de identidad por agente
c) Cuenta bloqueada por intentos fallidos (requiere desbloqueo manual)
d) Contraseña expirada (puede cambiarla desde pantalla de bloqueo)

Incluye los mensajes exactos del bot, opciones del usuario y 
acciones automatizadas posibles (reset por self-service portal).
Responde siempre en español.
```

2. Copia el resultado al documento Word.
3. Escribe el siguiente prompt para Microsoft Teams:

```
Diseña el flujo conversacional para: "Microsoft Teams no carga 
o presenta error al iniciar sesión".

Escenarios a cubrir:
a) Problema de caché corrupta del cliente Teams
b) Credenciales de cuenta expiradas o sesión cerrada
c) Problema de red/proxy que bloquea Teams
d) Versión desactualizada del cliente Teams
e) Problema del lado del servicio de Microsoft (outage)

Para el escenario (e), incluye un paso que consulte la página de 
estado de Microsoft 365 (status.office.com) antes de escalar.
Responde siempre en español.
```

4. Copia el resultado al documento Word y guarda el documento.

**Resultado esperado:** Tres flujos de autoservicio completos (VPN, contraseña, Teams) documentados en la sección 2 del documento Word.

---

#### Paso 2.3 — Generar resumen ejecutivo de los flujos

**Objetivo:** Crear un resumen que documente el potencial de reducción de tickets gracias a los flujos de autoservicio.

**Instrucciones:**

1. Escribe el siguiente prompt en Copilot Chat:

```
Basándote en los tres flujos de autoservicio que hemos diseñado 
(VPN, contraseña, Teams), genera un resumen ejecutivo de 1 página que:

1. Estime el porcentaje de casos que podrían resolverse de forma 
   autónoma sin intervención humana para cada flujo (usa rangos 
   basados en benchmarks de industria ITSM)
2. Identifique los 3 principales beneficios operativos de implementar 
   estos flujos en un Service Desk corporativo
3. Liste los 3 prerrequisitos técnicos clave para implementar estos 
   flujos (integración con Active Directory, portal de autoservicio, etc.)
4. Incluya una recomendación sobre qué flujo implementar primero y por qué

Usa un tono ejecutivo, datos concretos y formato estructurado con 
encabezados. Responde siempre en español.
```

2. Copia el resumen al documento Word como subsección final de la Sección 2.

**Resultado esperado:** Resumen ejecutivo de una página con estimaciones de resolución autónoma, beneficios y prerrequisitos técnicos.

---

### Actividad 3: Gestión de Casos Típicos de Service Desk

**Objetivo de la actividad:** Usar Copilot para gestionar 5 casos de soporte con información parcial, generando respuestas estandarizadas, instrucciones técnicas y comunicaciones al usuario final en tono profesional y empático, tal como haría un agente N1 aumentado.

---

#### Paso 3.1 — Procesar casos de soporte con Copilot

**Objetivo:** Simular el rol de un agente N1 aumentado que usa Copilot para gestionar casos con información incompleta del usuario.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt con los 5 casos ficticios:

```
Actúa como un asistente de Service Desk N1 con acceso a la base de 
conocimiento corporativa. Para cada uno de los siguientes 5 casos de 
soporte, genera:

A) Respuesta inmediata al usuario (tono empático, profesional, máximo 
   3 oraciones, confirma recepción y explica próximos pasos)
B) Instrucciones técnicas para el agente N1 (pasos concretos de 
   diagnóstico y resolución, referenciando el artículo KB correspondiente)
C) Nota interna del ticket (resumen técnico para el sistema ITSM con 
   campos: categoría, subcategoría, prioridad sugerida, artículo KB 
   referenciado, acción tomada)

CASO 1 - Ticket #INC-2024-001:
Usuario: María González | Departamento: Finanzas | Hora: 09:15
Descripción: "No puedo entrar a mi correo desde esta mañana. 
Me pide contraseña pero dice que está incorrecta. Tengo una 
reunión importante en 30 minutos."

CASO 2 - Ticket #INC-2024-002:
Usuario: Carlos Mendoza | Departamento: Ventas | Hora: 10:30
Descripción: "La impresora del piso 3 no aparece cuando quiero 
imprimir. Antes funcionaba bien. Necesito imprimir una propuesta."

CASO 3 - Ticket #INC-2024-003:
Usuario: Ana Rodríguez | Departamento: RR.HH. | Hora: 11:00
Descripción: "Teams se cierra solo cada vez que intento unirme 
a una videollamada. Tengo una entrevista de trabajo en una hora."

CASO 4 - Ticket #INC-2024-004:
Usuario: Roberto Silva | Departamento: IT | Hora: 14:00
Descripción: "Necesito instalar el software de diseño Visio 
en mi computadora para un proyecto urgente."

CASO 5 - Ticket #INC-2024-005:
Usuario: Laura Jiménez | Departamento: Legal | Hora: 15:30
Descripción: "No tengo acceso a la carpeta compartida de 
contratos en SharePoint. Mis colegas sí pueden entrar."

Responde siempre en español. Sé específico y usa los IDs de 
artículos KB cuando corresponda (KB-0001 a KB-0010).
```

2. Espera la respuesta completa de Copilot.
3. Copia el resultado al documento Word en una nueva sección llamada **"Sección 3: Gestión de Casos"**.

**Resultado esperado:** Para cada uno de los 5 casos: respuesta al usuario, instrucciones técnicas al agente y nota interna del ticket, con referencias a artículos KB.

---

#### Paso 3.2 — Generar plantillas de comunicación estandarizadas

**Objetivo:** Crear plantillas reutilizables para las comunicaciones más frecuentes del Service Desk.

**Instrucciones:**

1. Escribe el siguiente prompt en Copilot Chat:

```
Basándote en los 5 casos que acabamos de gestionar, crea un conjunto 
de 4 plantillas de comunicación estandarizadas para el Service Desk:

PLANTILLA 1: Confirmación de recepción de ticket (genérica)
PLANTILLA 2: Solicitud de información adicional al usuario
PLANTILLA 3: Notificación de resolución y cierre de ticket
PLANTILLA 4: Escalación a nivel N2 con comunicación al usuario

Para cada plantilla:
- Usa variables entre corchetes para personalización: 
  [NOMBRE_USUARIO], [NÚMERO_TICKET], [DESCRIPCIÓN_PROBLEMA], 
  [NOMBRE_AGENTE], [TIEMPO_ESTIMADO]
- Tono: profesional, empático, claro y conciso
- Longitud: máximo 150 palabras por plantilla
- Incluye línea de asunto para correo electrónico
- Añade una firma estándar del Service Desk

Responde siempre en español.
```

2. Copia las 4 plantillas al documento Word como subsección de la Sección 3.

**Resultado esperado:** 4 plantillas de comunicación con variables de personalización, línea de asunto y firma estándar.

---

#### Paso 3.3 — Análisis de patrones en los casos

**Objetivo:** Identificar patrones y oportunidades de mejora a partir de los casos gestionados.

**Instrucciones:**

1. Escribe el siguiente prompt en Copilot Chat:

```
Analiza los 5 casos de soporte que gestionamos (INC-2024-001 al 005) 
e identifica:

1. Patrones comunes: ¿Qué casos tienen causas raíz similares?
2. Casos de alta urgencia: ¿Cuáles tienen mayor impacto en productividad 
   y por qué? (considera el contexto del usuario y su departamento)
3. Oportunidades de autoservicio: ¿Cuáles de estos casos podrían 
   haberse resuelto por el propio usuario con la KB adecuada?
4. Recomendaciones de mejora: 3 acciones concretas para reducir 
   la recurrencia de estos casos en el futuro
5. Clasificación por categoría ITIL: Incidente vs. Solicitud de Servicio 
   para cada caso

Presenta el análisis en formato de tabla donde sea posible.
Responde siempre en español.
```

2. Copia el análisis al documento Word y guarda el documento.

**Resultado esperado:** Análisis estructurado con patrones identificados, clasificación ITIL y recomendaciones de mejora.

---

### Actividad 4: Tablero de Análisis de Impacto en Métricas Operativas

**Objetivo de la actividad:** Proyectar el impacto de la base de conocimiento inteligente en las métricas operativas clave del Service Desk (FCR, AHT, CSAT) construyendo un tablero de análisis en Excel con tres escenarios.

---

#### Paso 4.1 — Generar la estructura del tablero de métricas

**Objetivo:** Usar Copilot para diseñar el modelo de datos y las fórmulas del tablero de impacto en Excel.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Actúa como un analista de operaciones ITSM especializado en métricas 
de Service Desk. Diseña un modelo de tablero de análisis de impacto 
para Excel que proyecte el efecto de implementar una base de 
conocimiento inteligente con IA (Copilot) en un Service Desk corporativo.

El tablero debe incluir:

HOJA 1 - "Línea Base" (situación actual SIN KB inteligente):
- Volumen mensual de tickets: 800 tickets/mes
- Distribución por categoría (usa los 10 tipos de KB que creamos)
- Métricas actuales: FCR = 65%, AHT = 18 min, CSAT = 3.2/5, 
  TTR promedio = 4.2 horas, % escalaciones N2 = 35%
- Costo promedio por ticket N1: $8 USD, N2: $22 USD

HOJA 2 - "Proyección de Impacto" con 3 escenarios:
- Conservador: mejora del 10-15% en métricas clave
- Realista: mejora del 20-30% en métricas clave  
- Optimista: mejora del 35-50% en métricas clave

Para cada escenario calcula:
- Nuevo FCR proyectado
- Nuevo AHT proyectado
- Nuevo CSAT proyectado
- Reducción de tickets escalados a N2
- Ahorro mensual estimado en costos operativos (USD)
- Ahorro anual proyectado

HOJA 3 - "KPIs de Adopción":
- % de artículos KB utilizados en resoluciones
- Tasa de resolución autónoma (sin agente)
- NPS del portal de autoservicio
- Tiempo promedio de búsqueda en KB

Genera las fórmulas Excel específicas para las celdas clave 
(usa referencias como B2, C3, etc.) y explica la lógica de cálculo.
Responde siempre en español.
```

2. Copia el resultado al documento Word temporalmente para referencia.

**Resultado esperado:** Modelo completo del tablero con estructura de 3 hojas, datos de línea base, fórmulas Excel y lógica de cálculo para los 3 escenarios.

---

#### Paso 4.2 — Construir el tablero en Excel

**Objetivo:** Implementar el modelo diseñado en el archivo Excel del laboratorio.

**Instrucciones:**

1. Abre tu archivo `Dashboard-Metricas-[TuNombre].xlsx` en Excel.
2. Crea las 3 hojas con los nombres especificados: `Línea Base`, `Proyección de Impacto`, `KPIs de Adopción`.
3. En la hoja **"Línea Base"**, construye la siguiente estructura:

| Columna A | Columna B | Columna C |
|---|---|---|
| Métrica | Valor Actual | Unidad |
| Volumen mensual de tickets | 800 | tickets/mes |
| First Contact Resolution (FCR) | 65% | porcentaje |
| Average Handle Time (AHT) | 18 | minutos |
| Customer Satisfaction (CSAT) | 3.2 | /5.0 |
| Time to Resolve (TTR) | 4.2 | horas |
| % Escalaciones a N2 | 35% | porcentaje |
| Costo por ticket N1 | 8 | USD |
| Costo por ticket N2 | 22 | USD |

4. En la hoja **"Proyección de Impacto"**, usa las siguientes fórmulas de referencia (ajusta las referencias de celda según tu diseño):

```excel
# Fórmula para FCR proyectado (escenario conservador, +12%):
='Línea Base'!B3 * (1 + 0.12)

# Fórmula para AHT proyectado (reducción 15%):
='Línea Base'!B4 * (1 - 0.15)

# Fórmula para ahorro mensual estimado:
=('Línea Base'!B2 * 'Línea Base'!B11 * 0.35) - 
 ('Línea Base'!B2 * 'Línea Base'!B11 * (B_escalaciones_proyectadas))

# Fórmula para ahorro anual:
=ahorro_mensual * 12
```

5. Regresa a Copilot Chat y escribe el siguiente prompt para obtener el análisis narrativo:

```
Basándote en el tablero de métricas que diseñamos, genera un análisis 
ejecutivo de media página que:

1. Interprete los resultados del escenario REALISTA (mejora 20-30%)
2. Calcule el ROI estimado de implementar la KB inteligente, asumiendo 
   un costo de implementación inicial de $15,000 USD y $2,000 USD 
   mensuales de mantenimiento
3. Identifique la métrica que más impacto tendría en la satisfacción 
   del usuario final y explique por qué
4. Recomiende 2 métricas adicionales para medir el éxito de la KB 
   que no estén en el tablero actual

Usa datos numéricos concretos en tu análisis. 
Responde siempre en español.
```

6. Copia el análisis ejecutivo a la hoja `KPIs de Adopción` en Excel (celda A15) y también al documento Word en una nueva sección llamada **"Sección 4: Análisis de Impacto"**.

**Resultado esperado:** Tablero Excel funcional con 3 hojas, datos de línea base, proyecciones para 3 escenarios y análisis ejecutivo con cálculo de ROI.

---

#### Paso 4.3 — Reflexión final y cierre del laboratorio

**Objetivo:** Consolidar los aprendizajes del laboratorio con una reflexión asistida por Copilot.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt de cierre:

```
Hemos completado un laboratorio completo de construcción de base de 
conocimiento inteligente para Service Desk con Microsoft 365 Copilot.

Hemos creado:
- 10 artículos KCS de base de conocimiento
- 3 flujos de autoservicio conversacionales
- Gestión documentada de 5 casos típicos
- Tablero de análisis de impacto en métricas

Genera una reflexión estructurada de cierre que incluya:

1. Los 3 principios de la lección 4.1 que más se aplicaron en este 
   laboratorio (autoservicio inteligente, agentes aumentados, 
   orquestación end-to-end) con un ejemplo concreto de cada uno

2. Cómo la metodología KCS se complementa con las capacidades de 
   IA de Copilot para mantener la KB actualizada y relevante

3. Los 3 riesgos más importantes de implementar una KB con IA en 
   un Service Desk real y cómo mitigarlos (considera privacidad, 
   alucinaciones del LLM y dependencia tecnológica)

4. Una hoja de ruta de 90 días para implementar esta solución en 
   un Service Desk corporativo real (fases: Piloto, Expansión, 
   Optimización)

Responde siempre en español. Formato: encabezados claros y listas.
```

2. Copia el resultado al documento Word como sección final **"Sección 5: Reflexión y Hoja de Ruta"**.
3. Guarda ambos documentos (Word y Excel) en OneDrive.

**Resultado esperado:** Reflexión estructurada con los 3 principios aplicados, complementariedad KCS-IA, riesgos mitigados y hoja de ruta de 90 días.

---

## 7. Resumen

### Lo que Construiste en este Laboratorio

En 60 minutos, aplicando Microsoft 365 Copilot como motor de generación y análisis, construiste una solución completa de gestión del conocimiento para Service Desk que incluye:

| Artefacto | Descripción | Metodología aplicada |
|---|---|---|
| **Base de Conocimiento** | 10 artículos KCS completos organizados por categoría | KCS, ITIL v4 |
| **Flujos de Autoservicio** | 3 árboles de decisión conversacionales con criterios de escalación | Shift-left, Virtual Agent Design |
| **Gestión de Casos** | 5 casos documentados con respuestas estandarizadas y plantillas | ITIL v4 (Incident Management) |
| **Tablero de Impacto** | Análisis de ROI con 3 escenarios y métricas FCR/AHT/CSAT | Operational Analytics |

### Conexión con los Principios de la Lección 4.1

Este laboratorio puso en práctica los tres pilares de la transformación del Service Desk:

- **Autoservicio inteligente:** Los flujos conversacionales diseñados en la Actividad 2 replican exactamente el patrón de "detección de intención → KB sugerida → acción automatizada" descrito en el Caso 1 de la lección (VPN).
- **Agentes aumentados:** La Actividad 3 simuló el rol del agente N1 aumentado que usa Copilot para resumir, clasificar y responder casos con contexto de KB, tal como el Caso 2 de la lección (agente N2 con latencias).
- **Orquestación end-to-end:** El tablero de métricas (Actividad 4) proporciona la capa de observabilidad necesaria para medir el impacto del sistema, cerrando el ciclo de mejora continua descrito en la arquitectura técnica de la lección.

### Puntos Clave del Laboratorio

1. **La calidad de los prompts determina la calidad de la KB.** Los prompts iterativos y específicos producen artículos más completos y accionables que los prompts genéricos.
2. **KCS + IA = KB viva.** La metodología KCS proporciona la estructura; Copilot acelera la creación y actualización del contenido. La combinación reduce el tiempo de creación de artículos de horas a minutos.
3. **El shift-left tiene valor medible.** El tablero de impacto demostró que incluso en el escenario conservador, la implementación de una KB inteligente genera ROI positivo en menos de 6 meses.
4. **La privacidad y la trazabilidad no son opcionales.** Como se vio en la arquitectura técnica de la lección 4.1, el gobierno (seguridad, auditoría, enmascaramiento de PII) es un componente central, no un añadido posterior.

### Recursos Adicionales

| Recurso | URL | Relevancia |
|---|---|---|
| Microsoft Copilot for Service | [learn.microsoft.com/copilot-overview](https://learn.microsoft.com/en-us/dynamics365/customer-service/copilot-overview) | Capacidades de Copilot en Service Desk |
| KCS Academy — Fundamentals | [kcsacademy.com](https://www.kcsacademy.com) | Metodología KCS para bases de conocimiento |
| ITIL 4 Practice Guide: Service Desk | [axelos.com](https://www.axelos.com/certifications/itil-service-management/itil-4-foundation) | Framework ITIL v4 para Service Desk |
| Azure OpenAI RAG Pattern | [learn.microsoft.com/use-your-data](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/use-your-data) | Arquitectura técnica RAG para KB |
| Microsoft 365 Status | [status.office.com](https://status.office.com) | Referencia para flujo de autoservicio Teams |
| Prompt Engineering Guide | [promptingguide.ai](https://www.promptingguide.ai/es) | Técnicas avanzadas de prompt engineering |

---

> **Felicitaciones.** Has completado el Laboratorio 04-00-01 y con él el ciclo completo del módulo 4. Los artefactos que construiste hoy —la base de conocimiento, los flujos de autoservicio y el tablero de métricas— son entregables reales que pueden adaptarse directamente a un entorno corporativo, representando el valor tangible de integrar IA en las operaciones de Service Desk.

---
*Lab 04-00-01 | Versión 1.0 | Módulo 4: Service Desk Inteligente con Microsoft 365 Copilot*
