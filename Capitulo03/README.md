# Práctica 3: Clasificación automática de tickets, priorización inteligente y análisis de causa raíz (RCA) para la prevención de incidentes

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Alta |
| **Nivel Bloom** | Crear |
| **Módulo** | 3 — Gestión Inteligente de Operaciones y Resiliencia Proactiva |
| **Laboratorio previo requerido** | Lab 01 y Lab 02 (o experiencia equivalente con Copilot Chat) |
| **Herramientas principales** | Microsoft 365 Copilot Chat, Microsoft Excel, Microsoft Word |

---

## 2. Descripción General

En este laboratorio aplicarás los principios de **AIOps y Gestión Inteligente de Operaciones** (Tema 3.1) para construir, paso a paso, un flujo completo de gestión de incidentes asistido por IA. Partirás de un dataset simulado de 20 tickets de soporte técnico y utilizarás Copilot Chat para clasificarlos automáticamente, priorizarlos según criterios de SLA e impacto en negocio, ejecutar un análisis de causa raíz (RCA) estructurado sobre un incidente crítico simulado, y finalmente producir un plan CAPA documentado con métricas de seguimiento.

El laboratorio refleja cómo un copiloto conversacional actúa como "capa cognitiva" sobre los procesos ITSM: enriquece tickets, recomienda prioridades y documenta evidencia de manera estructurada, reduciendo el MTTD y el MTTR tal como se describió en la lección teórica.

---

## 3. Objetivos de Aprendizaje

Al completar este laboratorio, serás capaz de:

- [ ] **Diseñar** prompts avanzados en Copilot Chat para clasificar automáticamente tickets de soporte por categoría, severidad e impacto, documentando los resultados en Excel.
- [ ] **Aplicar** criterios de priorización inteligente asistida por IA para generar una cola de atención ordenada y justificada según SLAs e impacto en negocio.
- [ ] **Ejecutar** un análisis de causa raíz (RCA) completo con metodología de los 5 Porqués y estructura de Ishikawa, documentado en Word con apoyo de Copilot.
- [ ] **Crear** un plan de acciones correctivas y preventivas (CAPA) con responsables, fechas estimadas y KPIs de seguimiento operativo.
- [ ] **Evaluar** la calidad de los artefactos generados por Copilot y refinarlos mediante técnicas de prompt iterativo.

---

## 4. Prerrequisitos

### Conocimiento Previo

| Área | Nivel Requerido |
|---|---|
| Gestión de tickets e ITSM (conceptos ITIL: incidente, problema, cambio) | Básico |
| Definición y uso de SLAs en operaciones de IT | Básico |
| Metodología de los 5 Porqués para análisis de causa raíz | Básico-Intermedio |
| Uso de Copilot Chat (Labs 01 y 02 completados o experiencia equivalente) | Intermedio |
| Microsoft Excel — tablas y formato básico | Básico |
| Microsoft Word — edición y estructura de documentos | Básico |

### Acceso y Licencias

| Requisito | Estado esperado |
|---|---|
| Cuenta corporativa con licencia **Microsoft 365 Copilot** activa | ✅ Verificado antes del laboratorio |
| Acceso a [copilot.microsoft.com](https://copilot.microsoft.com) | ✅ Funcional |
| Microsoft Excel (Online o Desktop, versión Microsoft 365) | ✅ Disponible |
| Microsoft Word (Online o Desktop, versión Microsoft 365) | ✅ Disponible |
| OneDrive con al menos 100 MB de espacio libre | ✅ Disponible |

> ⚠️ **AVISO CRÍTICO:** Si tu licencia de Microsoft 365 Copilot no está activa, ninguna actividad de este laboratorio es ejecutable. Verifica con tu instructor antes de continuar.

---

## 5. Entorno de Laboratorio

### Software Requerido

| Aplicación | Versión mínima | Uso en este laboratorio |
|---|---|---|
| Microsoft Edge o Chrome | 120+ | Acceso a Copilot Chat y Microsoft 365 Online |
| Microsoft 365 Copilot Chat | Versión actual (SaaS) | Motor principal de IA para todos los bloques |
| Microsoft Excel | Microsoft 365 actual | Tablas de clasificación y tablero CAPA |
| Microsoft Word | Microsoft 365 actual | Documentación del RCA y plan de prevención |

### Preparación del Entorno (antes de iniciar)

Ejecuta los siguientes pasos de configuración antes de comenzar el Bloque 1:

1. Abre tu navegador y navega a [https://copilot.microsoft.com](https://copilot.microsoft.com). Inicia sesión con tu cuenta corporativa.
2. Verifica que en la esquina superior derecha aparezca tu nombre y el indicador de licencia Copilot activa.
3. Abre una nueva pestaña y navega a [https://office.com](https://office.com). Abre **Excel Online** y crea un libro en blanco. Nómbralo: `Lab03-Tickets-Clasificacion.xlsx` y guárdalo en tu OneDrive.
4. Abre otra pestaña y crea un nuevo documento en **Word Online**. Nómbralo: `Lab03-RCA-PlanCAPA.docx` y guárdalo en tu OneDrive.
5. Mantén estas tres pestañas abiertas durante todo el laboratorio: Copilot Chat | Excel | Word.

> 💡 **Consejo:** Si Copilot responde en inglés, añade al final de cada prompt la instrucción: `Responde siempre en español.`

---

## 6. Instrucciones Paso a Paso

El laboratorio se divide en **cuatro bloques** progresivos. Cada bloque construye sobre el anterior.

---

### BLOQUE 1 — Clasificación Automática de Tickets

#### Objetivo del Bloque
Alimentar a Copilot Chat con el dataset simulado de tickets y construir prompts para que los clasifique automáticamente por categoría, severidad y área responsable. Documentar los resultados en Excel.

---

#### Paso 1.1 — Preparar el Dataset de Tickets en Copilot Chat

**Objetivo:** Proporcionar a Copilot el contexto completo del dataset de 20 tickets simulados para que pueda procesarlos en los pasos siguientes.

**Instrucciones:**

1. En Copilot Chat, inicia una **nueva conversación** (botón "Nueva conversación" o el ícono de lápiz).
2. Copia y pega el siguiente prompt completo en el cuadro de chat. Este prompt incluye el dataset y las instrucciones de clasificación:

```
Actúa como un analista experto en ITSM con conocimiento de ITIL v4. 
A continuación te proporciono un dataset de 20 tickets de soporte técnico 
de la empresa ficticia "TechCorp S.A." Necesito que los analices para 
clasificarlos en el siguiente paso. Por ahora, solo confirma que has 
recibido y comprendido los datos, y lista los IDs de los tickets.

DATASET DE TICKETS - TechCorp S.A.:

TKT-001 | Usuario: María García | Sistema: Active Directory | Descripción: No puedo iniciar sesión desde esta mañana, mi contraseña no funciona | Hora reporte: 08:05
TKT-002 | Usuario: Carlos López | Sistema: SAP ERP | Descripción: El módulo de facturación está caído, no podemos emitir facturas a clientes | Hora reporte: 08:12
TKT-003 | Usuario: Ana Torres | Sistema: Laptop Dell | Descripción: Mi laptop no enciende, pantalla negra al presionar el botón de encendido | Hora reporte: 08:20
TKT-004 | Usuario: Pedro Martínez | Sistema: Red Wi-Fi | Descripción: Sin conexión a internet en toda la planta 3, afecta a 45 usuarios | Hora reporte: 08:31
TKT-005 | Usuario: Laura Sánchez | Sistema: Microsoft Teams | Descripción: No puedo unirme a reuniones de video, error de audio | Hora reporte: 08:45
TKT-006 | Usuario: Roberto Díaz | Sistema: Servidor de Archivos | Descripción: Carpeta compartida de proyectos inaccesible, error de permisos | Hora reporte: 09:00
TKT-007 | Usuario: Sofia Herrera | Sistema: Impresora HP LaserJet | Descripción: Impresora del piso 2 no imprime, muestra error de papel atascado | Hora reporte: 09:15
TKT-008 | Usuario: Miguel Ríos | Sistema: VPN Corporativa | Descripción: No puedo conectarme a VPN desde casa, error de certificado | Hora reporte: 09:22
TKT-009 | Usuario: Elena Morales | Sistema: Sistema de Nómina | Descripción: El sistema de nómina no carga los reportes del mes, proceso de pago en riesgo | Hora reporte: 09:30
TKT-010 | Usuario: Juan Vargas | Sistema: Correo Outlook | Descripción: No recibo correos desde hace 2 horas, buzón parece lleno | Hora reporte: 09:45
TKT-011 | Usuario: Carmen Ruiz | Sistema: Active Directory | Descripción: Cuenta de usuario bloqueada, posible intento de acceso no autorizado detectado | Hora reporte: 10:00
TKT-012 | Usuario: Andrés Castro | Sistema: Base de Datos Oracle | Descripción: Consultas lentas en base de datos de producción, tiempo de respuesta >30 segundos | Hora reporte: 10:15
TKT-013 | Usuario: Patricia Leal | Sistema: Monitor Dell 27" | Descripción: Monitor parpadea constantemente, dificulta el trabajo | Hora reporte: 10:30
TKT-014 | Usuario: Fernando Mora | Sistema: Firewall Corporativo | Descripción: Alertas de seguridad inusuales en firewall, posible escaneo de puertos externo | Hora reporte: 10:45
TKT-015 | Usuario: Daniela Vega | Sistema: Aplicación CRM | Descripción: CRM no guarda cambios en registros de clientes, datos se pierden | Hora reporte: 11:00
TKT-016 | Usuario: Ricardo Peña | Sistema: Switch de Red | Descripción: Switch del rack A-03 reporta fallo en módulo de uplink, conectividad degradada | Hora reporte: 11:15
TKT-017 | Usuario: Valentina Cruz | Sistema: Windows 10 | Descripción: PC muy lenta, CPU al 100% constantemente, posible malware | Hora reporte: 11:30
TKT-018 | Usuario: Héctor Fuentes | Sistema: Servidor Web Apache | Descripción: Sitio web corporativo devuelve error 503, clientes externos no pueden acceder | Hora reporte: 11:45
TKT-019 | Usuario: Isabela Ramos | Sistema: Licencias Microsoft | Descripción: Excel no abre, dice que la licencia expiró | Hora reporte: 12:00
TKT-020 | Usuario: Tomás Aguilar | Sistema: Backup Veeam | Descripción: Job de backup nocturno falló, 3 noches consecutivas sin respaldo | Hora reporte: 12:15

Responde siempre en español.
```

3. Presiona **Enter** y espera la respuesta de Copilot.

**Resultado Esperado:**
Copilot debe confirmar que ha recibido los 20 tickets y listar sus IDs (TKT-001 al TKT-020), posiblemente con un breve resumen del contexto.

---

#### Paso 1.2 — Ejecutar la Clasificación Automática

**Objetivo:** Obtener la clasificación completa de los 20 tickets en una tabla estructurada lista para copiar a Excel.

**Instrucciones:**

1. En la **misma conversación** (no inicies una nueva), envía el siguiente prompt de clasificación:

```
Ahora clasifica los 20 tickets del dataset que te proporcioné. 
Para cada ticket genera una tabla con las siguientes columnas:

| ID Ticket | Usuario | Sistema | Categoría | Severidad | Impacto en Negocio | Área Responsable | Justificación (1 línea) |

Usa estos criterios de clasificación:

CATEGORÍA (elige una):
- Hardware: fallas físicas de equipos
- Software: aplicaciones, sistemas operativos, licencias
- Red: conectividad, switches, Wi-Fi, VPN
- Acceso/Identidad: credenciales, permisos, Active Directory
- Seguridad: amenazas, malware, firewall, accesos sospechosos
- Infraestructura: servidores, bases de datos, backups

SEVERIDAD (elige una):
- Crítico: servicio completamente caído, impacto masivo o riesgo de seguridad inmediato
- Alto: degradación significativa, múltiples usuarios afectados o proceso de negocio en riesgo
- Medio: usuario individual afectado, workaround disponible
- Bajo: molestia menor, sin impacto operativo inmediato

IMPACTO EN NEGOCIO (elige uno):
- Crítico: pérdida de ingresos directa o riesgo regulatorio
- Alto: productividad de área completa comprometida
- Medio: productividad individual afectada
- Bajo: impacto cosmético o mínimo

ÁREA RESPONSABLE (elige una):
- N1 - Service Desk
- N2 - Infraestructura
- N2 - Seguridad
- N3 - Desarrollo/Aplicaciones
- N3 - Base de Datos

Presenta la tabla completa con los 20 tickets. Responde siempre en español.
```

2. Espera la respuesta completa de Copilot. Si la tabla se corta, escribe: `Continúa con la tabla desde donde la dejaste.`

**Resultado Esperado:**
Una tabla Markdown con los 20 tickets clasificados, incluyendo categoría, severidad, impacto y área responsable con justificación para cada uno.

---

#### Paso 1.3 — Documentar la Clasificación en Excel

**Objetivo:** Transferir la tabla de clasificación a Excel para su uso en el Bloque 2.

**Instrucciones:**

1. Selecciona y copia toda la tabla generada por Copilot.
2. Cambia a la pestaña de **Excel Online** (`Lab03-Tickets-Clasificacion.xlsx`).
3. Haz clic en la celda **A1** y pega el contenido.
4. Si Excel no formatea la tabla automáticamente, sigue estos pasos manuales:
   - Crea los encabezados en la fila 1: `ID Ticket | Usuario | Sistema | Categoría | Severidad | Impacto en Negocio | Área Responsable | Justificación`
   - Ingresa los datos de cada ticket en las filas 2–21.
5. Selecciona el rango **A1:H21** y aplica formato de tabla: **Insertar → Tabla** (activa "Mi tabla tiene encabezados").
6. Aplica formato condicional a la columna **Severidad**:
   - Crítico → Relleno rojo
   - Alto → Relleno naranja
   - Medio → Relleno amarillo
   - Bajo → Relleno verde
7. Guarda el archivo con **Ctrl+S**.

**Resultado Esperado:**
Una tabla Excel con 20 filas de datos, formateada con colores por severidad, lista para usar como base de priorización.

---

### BLOQUE 2 — Priorización Inteligente de la Cola de Tickets 

#### Objetivo del Bloque
Usar los tickets clasificados para que Copilot genere una cola de atención priorizada con justificación basada en SLAs e impacto en negocio.

---

#### Paso 2.1 — Generar la Cola de Atención Priorizada

**Objetivo:** Obtener de Copilot un ranking ordenado de los 20 tickets con justificación de prioridad y tiempos de respuesta objetivo según SLA.

**Instrucciones:**

1. Regresa a **Copilot Chat** (mantén la misma conversación del Bloque 1).
2. Envía el siguiente prompt:

```
Usando la clasificación que generaste para los 20 tickets de TechCorp S.A., 
genera una cola de atención priorizada. Ordena los tickets del más urgente 
al menos urgente aplicando los siguientes criterios en este orden de peso:

1. SEVERIDAD (Crítico > Alto > Medio > Bajo)
2. IMPACTO EN NEGOCIO (Crítico > Alto > Medio > Bajo)
3. TIEMPO DE REPORTE (más antiguo primero en caso de empate)
4. SLA OBJETIVO según severidad:
   - Crítico: Respuesta en 15 min, Resolución en 4 horas
   - Alto: Respuesta en 30 min, Resolución en 8 horas
   - Medio: Respuesta en 2 horas, Resolución en 24 horas
   - Bajo: Respuesta en 4 horas, Resolución en 72 horas

Genera una tabla con estas columnas:
| Posición | ID Ticket | Usuario | Sistema | Severidad | Impacto | SLA Respuesta | SLA Resolución | Justificación de Prioridad |

Después de la tabla, incluye un párrafo de análisis ejecutivo (máximo 5 líneas) 
que resuma los patrones críticos observados en la cola y las recomendaciones 
inmediatas para el equipo de Service Desk.

Responde siempre en español.
```

3. Espera la respuesta completa.

**Resultado Esperado:**
Una tabla con los 20 tickets ordenados por prioridad (posiciones 1–20), con SLAs asignados y justificación. Seguida de un párrafo de análisis ejecutivo.

---

#### Paso 2.2 — Agregar la Cola Priorizada a Excel

**Objetivo:** Crear una segunda hoja en Excel con el tablero de priorización.

**Instrucciones:**

1. En Excel (`Lab03-Tickets-Clasificacion.xlsx`), haz clic en el botón **"+"** para agregar una nueva hoja. Nómbrala: `Cola_Priorizada`.
2. Copia la tabla de priorización generada por Copilot y pégala en la celda **A1** de la nueva hoja.
3. Formatea como tabla con encabezados.
4. En la celda **J1** escribe: `Estado`. En las celdas J2:J21 escribe `Pendiente` para todos los tickets.
5. Copia el párrafo de análisis ejecutivo a la celda **A23** (debajo de la tabla).
6. Guarda el archivo.

**Resultado Esperado:**
Excel con dos hojas: `Hoja1` (clasificación) y `Cola_Priorizada` (ranking de atención con estado).

---

### BLOQUE 3 — Análisis de Causa Raíz (RCA) con Metodología Estructurada (30 minutos)

#### Objetivo del Bloque
Ejecutar un RCA completo del incidente crítico simulado (caída del sistema de autenticación corporativa) usando la metodología de los 5 Porqués y la estructura del diagrama de Ishikawa, documentado en Word.

---

#### Paso 3.1 — Presentar el Escenario del Incidente Crítico

**Objetivo:** Establecer el contexto completo del incidente para que Copilot pueda asistir en el análisis estructurado.

**Instrucciones:**

1. En Copilot Chat, inicia una **nueva conversación** (este RCA es un análisis independiente).
2. Envía el siguiente prompt para establecer el contexto:

```
Actúa como un analista senior de ITSM y experto en análisis de causa raíz (RCA). 
Voy a trabajar contigo para ejecutar un RCA completo de un incidente crítico 
ocurrido en TechCorp S.A. 

DESCRIPCIÓN DEL INCIDENTE:
- ID Incidente: INC-2024-0847
- Fecha/Hora inicio: Lunes 15 de enero de 2024, 07:58 AM
- Fecha/Hora resolución: Lunes 15 de enero de 2024, 11:42 AM
- Duración total: 3 horas 44 minutos
- Sistema afectado: Active Directory / Sistema de Autenticación Corporativa
- Impacto: 847 usuarios sin acceso a sistemas corporativos durante 3h44min
- Síntoma principal: Usuarios no podían autenticarse en ningún sistema corporativo (Windows login, VPN, Outlook, SAP, Teams)
- Sistemas secundarios afectados: VPN, Correo Outlook, SAP ERP, Microsoft Teams, CRM
- Área geográfica: Todas las oficinas (Ciudad de México, Guadalajara, Monterrey)
- Quién detectó: Múltiples tickets simultáneos en Service Desk (TKT-001 y TKT-011 del dataset anterior fueron los primeros)
- Acciones de resolución tomadas: Reinicio del servicio de AD DS en el controlador de dominio primario DC-PROD-01, failover al controlador secundario DC-PROD-02, restauración de configuración de replicación
- Costo estimado de impacto: $47,500 USD en productividad perdida

CONTEXTO TÉCNICO ADICIONAL:
- La semana anterior se realizó una actualización de Windows Server en DC-PROD-01 (KB5034441)
- El backup del domingo anterior completó con advertencias (no errores)
- Se había modificado una GPO (Group Policy Object) el viernes anterior para reforzar políticas de contraseñas
- El equipo de infraestructura tenía 2 de 5 ingenieros en vacaciones ese día
- El monitoreo alertó 23 minutos DESPUÉS de que comenzaron los primeros tickets de usuarios

Confirma que has recibido el contexto del incidente y que estás listo para 
iniciar el análisis RCA. Responde siempre en español.
```

3. Espera la confirmación de Copilot.

**Resultado Esperado:**
Copilot confirma haber recibido el contexto del incidente INC-2024-0847 y expresa que está listo para iniciar el RCA.

---

#### Paso 3.2 — Ejecutar el Análisis de los 5 Porqués

**Objetivo:** Generar el análisis de los 5 Porqués para identificar la causa raíz del incidente.

**Instrucciones:**

1. En la misma conversación, envía el siguiente prompt:

```
Ejecuta el análisis de los 5 Porqués (5 Whys) para el incidente INC-2024-0847.

El análisis debe seguir esta estructura:

PROBLEMA DECLARADO: [Descripción concisa del síntoma principal]

¿Por qué 1? [Causa inmediata observable]
  → Evidencia que lo soporta: [dato del contexto]

¿Por qué 2? [Causa de la causa anterior]
  → Evidencia que lo soporta: [dato del contexto]

¿Por qué 3? [Causa más profunda]
  → Evidencia que lo soporta: [dato del contexto]

¿Por qué 4? [Causa sistémica o de proceso]
  → Evidencia que lo soporta: [dato del contexto]

¿Por qué 5? [Causa raíz fundamental — falla de proceso, sistema o cultura]
  → Evidencia que lo soporta: [dato del contexto]

CAUSA RAÍZ IDENTIFICADA: [Declaración formal de la causa raíz]

Después del análisis, incluye una sección llamada "Causas Contribuyentes" 
donde listes factores adicionales que, aunque no son la causa raíz, 
contribuyeron a la severidad o duración del incidente.

Basa el análisis estrictamente en el contexto técnico que te proporcioné.
Responde siempre en español.
```

2. Espera la respuesta completa de Copilot.
3. Si el análisis te parece superficial, envía este prompt de refinamiento:

```
El análisis es un buen punto de partida. Por favor profundiza en el "¿Por qué 3?" 
y el "¿Por qué 4?" considerando específicamente: el proceso de gestión de cambios 
(la GPO modificada el viernes), el procedimiento de pruebas post-actualización 
de Windows Server, y la cobertura del monitoreo proactivo. 
Regenera solo esas dos secciones con mayor detalle técnico.
Responde siempre en español.
```

**Resultado Esperado:**
Un análisis de 5 Porqués completo que identifique como causa raíz algo relacionado con: falta de proceso de prueba post-cambio, gestión de cambios deficiente, o ausencia de validación de replicación de AD tras la actualización de Windows Server.

---

#### Paso 3.3 — Generar el Análisis de Ishikawa (Espina de Pescado)

**Objetivo:** Complementar el análisis de los 5 Porqués con la estructura del diagrama de Ishikawa para identificar causas desde múltiples dimensiones.

**Instrucciones:**

1. En la misma conversación, envía el siguiente prompt:

```
Ahora genera un análisis estructurado basado en el diagrama de Ishikawa 
(espina de pescado) para el mismo incidente INC-2024-0847.

Organiza las causas identificadas en las siguientes 6 categorías (las "espinas"):

1. PERSONAS (People): Factores relacionados con el equipo humano
2. PROCESOS (Process): Fallas en procedimientos y metodologías  
3. TECNOLOGÍA (Technology): Fallas o limitaciones técnicas
4. ENTORNO (Environment): Condiciones del entorno operativo
5. MEDICIÓN (Measurement): Problemas con monitoreo y métricas
6. GESTIÓN (Management): Decisiones y políticas organizacionales

Para cada categoría, lista entre 2 y 4 causas específicas identificadas 
en el contexto del incidente. Al final, indica cuáles causas se alinean 
con la causa raíz identificada en el análisis de los 5 Porqués.

Presenta el resultado en formato de tabla para facilitar su documentación:
| Categoría | Causa Identificada | Relación con Causa Raíz |

Responde siempre en español.
```

2. Espera la respuesta.

**Resultado Esperado:**
Una tabla con las 6 categorías de Ishikawa, cada una con 2–4 causas identificadas, y una columna que indica si cada causa está directamente relacionada con la causa raíz o es contribuyente.

---

#### Paso 3.4 — Documentar el RCA en Word

**Objetivo:** Crear el documento formal de RCA en Word con toda la información generada.

**Instrucciones:**

1. Solicita a Copilot el resumen ejecutivo del RCA con este prompt:

```
Genera el resumen ejecutivo del RCA del incidente INC-2024-0847 con 
el siguiente formato para un documento formal:

## RESUMEN EJECUTIVO DEL INCIDENTE
- Descripción del incidente (2-3 líneas)
- Impacto total (usuarios, duración, costo estimado)
- Causa raíz declarada (1 línea)
- Estado de resolución

## LÍNEA DE TIEMPO DEL INCIDENTE
Reconstruye una línea de tiempo estimada con los eventos clave desde 
las 07:58 AM hasta las 11:42 AM, incluyendo: detección, escalado, 
diagnóstico, remediación y cierre. Usa formato de tabla:
| Hora | Evento | Actor |

## HALLAZGOS PRINCIPALES
Lista los 5 hallazgos más importantes del análisis RCA.

Responde siempre en español.
```

2. Copia toda la salida de Copilot (resumen ejecutivo + línea de tiempo + hallazgos).
3. Cambia a la pestaña de **Word Online** (`Lab03-RCA-PlanCAPA.docx`).
4. Estructura el documento con los siguientes títulos de sección:
   - **Título:** `RCA - Incidente INC-2024-0847: Caída del Sistema de Autenticación Corporativa`
   - **Sección 1:** Resumen Ejecutivo del Incidente
   - **Sección 2:** Línea de Tiempo del Incidente
   - **Sección 3:** Análisis de los 5 Porqués
   - **Sección 4:** Análisis de Ishikawa (tabla)
   - **Sección 5:** Hallazgos Principales
   - **Sección 6:** Plan CAPA (se completará en el Bloque 4)
5. Pega el contenido de Copilot en las secciones 1, 2 y 5.
6. Copia el análisis de los 5 Porqués del Paso 3.2 a la Sección 3.
7. Copia la tabla de Ishikawa del Paso 3.3 a la Sección 4.
8. Guarda el documento con **Ctrl+S**.

**Resultado Esperado:**
Un documento Word con 5 de las 6 secciones completas, dejando la Sección 6 (Plan CAPA) para el Bloque 4.

---

### BLOQUE 4 — Plan de Prevención de Incidentes (CAPA) 

#### Objetivo del Bloque
Generar con Copilot un plan CAPA completo basado en los hallazgos del RCA, con acciones correctivas, preventivas, responsables, fechas y KPIs de seguimiento.

---

#### Paso 4.1 — Generar las Acciones Correctivas (Corrective Actions)

**Objetivo:** Obtener acciones concretas para corregir las causas identificadas en el RCA.

**Instrucciones:**

1. Regresa a **Copilot Chat** (mantén la conversación del RCA activa).
2. Envía el siguiente prompt:

```
Basándote en el análisis RCA completo del incidente INC-2024-0847, 
genera el Plan de Acciones Correctivas (Corrective Actions) del framework CAPA.

Las acciones correctivas deben ELIMINAR o REMEDIAR las causas raíz ya identificadas.

Para cada acción correctiva, proporciona:
- ID de acción (CA-001, CA-002, etc.)
- Descripción detallada de la acción
- Causa raíz o contribuyente que atiende
- Responsable (rol, no nombre personal)
- Fecha objetivo de implementación (usa fechas relativas: "Semana 1", "Mes 1", etc.)
- Recursos necesarios
- Criterio de éxito medible

Genera entre 5 y 7 acciones correctivas priorizadas. 
Presenta el resultado en formato de tabla.
Responde siempre en español.
```

3. Espera la respuesta.

**Resultado Esperado:**
Una tabla con 5–7 acciones correctivas, cada una con ID, descripción, responsable, fecha y criterio de éxito.

---

#### Paso 4.2 — Generar las Acciones Preventivas (Preventive Actions)

**Objetivo:** Obtener acciones para prevenir la recurrencia del incidente y de incidentes similares en el futuro.

**Instrucciones:**

1. En la misma conversación, envía el siguiente prompt:

```
Ahora genera el Plan de Acciones Preventivas (Preventive Actions) del framework CAPA 
para el incidente INC-2024-0847.

Las acciones preventivas deben EVITAR que el incidente (o uno similar) vuelva a ocurrir.
Piensa en mejoras sistémicas, de proceso y de cultura organizacional.

Para cada acción preventiva, proporciona:
- ID de acción (PA-001, PA-002, etc.)
- Descripción detallada de la acción
- Riesgo futuro que mitiga
- Responsable (rol)
- Horizonte de implementación (Corto: <1 mes / Medio: 1-3 meses / Largo: 3-6 meses)
- KPI de seguimiento con valor objetivo

Incluye al menos una acción preventiva en cada horizonte temporal.
Genera entre 6 y 8 acciones preventivas.
Presenta el resultado en formato de tabla.
Responde siempre en español.
```

2. Espera la respuesta.

**Resultado Esperado:**
Una tabla con 6–8 acciones preventivas con KPIs medibles distribuidas en los tres horizontes temporales.

---

#### Paso 4.3 — Generar el Dashboard de KPIs de Seguimiento

**Objetivo:** Crear una estructura de métricas para monitorear el progreso del plan CAPA.

**Instrucciones:**

1. En la misma conversación, envía el siguiente prompt:

```
Genera un Dashboard de KPIs de Seguimiento para el Plan CAPA del incidente INC-2024-0847.

El dashboard debe incluir:

1. KPIs OPERATIVOS (métricas de operación que deben mejorar):
   - Nombre del KPI
   - Valor actual (baseline del incidente)
   - Valor objetivo a 30 días
   - Valor objetivo a 90 días
   - Fórmula de cálculo o fuente de datos

2. KPIs DE IMPLEMENTACIÓN CAPA (métricas de avance del plan):
   - Porcentaje de acciones correctivas completadas
   - Porcentaje de acciones preventivas en progreso
   - Número de incidentes similares post-implementación

3. INDICADORES DE ALERTA TEMPRANA (señales de que el riesgo persiste):
   - Lista de 3-5 indicadores que deben monitorearse semanalmente

Presenta los KPIs operativos en formato de tabla.
Responde siempre en español.
```

2. Espera la respuesta.

**Resultado Esperado:**
Un dashboard estructurado con KPIs operativos en tabla (con baseline y objetivos), KPIs de implementación CAPA e indicadores de alerta temprana.

---

#### Paso 4.4 — Completar el Documento Word con el Plan CAPA

**Objetivo:** Integrar el Plan CAPA completo en el documento Word del RCA.

**Instrucciones:**

1. Solicita a Copilot el resumen ejecutivo del Plan CAPA:

```
Genera un párrafo de introducción para la Sección 6 "Plan CAPA" del documento RCA, 
que explique: el propósito del plan, el número total de acciones (correctivas + preventivas), 
el horizonte total de implementación, y el mecanismo de revisión y seguimiento propuesto 
(ej: reunión quincenal de seguimiento, responsable del plan, escalado). 
Máximo 150 palabras. Responde siempre en español.
```

2. Copia el párrafo de introducción.
3. Cambia a **Word Online** y navega a la **Sección 6: Plan CAPA**.
4. Pega el párrafo de introducción.
5. Agrega los siguientes sub-títulos y pega el contenido correspondiente de Copilot:
   - `6.1 Acciones Correctivas` → tabla del Paso 4.1
   - `6.2 Acciones Preventivas` → tabla del Paso 4.2
   - `6.3 Dashboard de KPIs de Seguimiento` → contenido del Paso 4.3
6. Al final del documento, agrega una sección de **Firmas y Aprobaciones** con la siguiente estructura:

```
## 7. Firmas y Aprobaciones

| Rol | Nombre | Firma | Fecha |
|---|---|---|---|
| Responsable del Incidente | | | |
| Gerente de Infraestructura | | | |
| Responsable del Plan CAPA | | | |
| Director de IT | | | |
```

7. Guarda el documento final con **Ctrl+S**.

**Resultado Esperado:**
Un documento Word completo con 7 secciones: Resumen Ejecutivo, Línea de Tiempo, Análisis 5 Porqués, Ishikawa, Hallazgos, Plan CAPA (con 3 sub-secciones) y Firmas.

---

#### Paso 4.5 — Crear el Tablero CAPA en Excel

**Objetivo:** Crear una hoja de seguimiento del Plan CAPA en Excel para facilitar el control de avance.

**Instrucciones:**

1. Regresa a **Excel** (`Lab03-Tickets-Clasificacion.xlsx`).
2. Agrega una nueva hoja llamada `Plan_CAPA`.
3. Crea la siguiente estructura de encabezados en la fila 1:

```
ID Acción | Tipo (CA/PA) | Descripción | Causa que Atiende | Responsable | Fecha Objetivo | Estado | % Avance | KPI de Éxito | Observaciones
```

4. Ingresa todas las acciones correctivas (CA-001 a CA-00X) y preventivas (PA-001 a PA-00X) generadas por Copilot en los Pasos 4.1 y 4.2.
5. En la columna **Estado**, usa estos valores: `No Iniciada | En Progreso | Completada | Bloqueada`.
6. En la columna **% Avance**, ingresa `0%` para todas las acciones (estado inicial).
7. Agrega una segunda tabla debajo (a partir de la fila 25) con los **KPIs del Dashboard** del Paso 4.3, con columnas: `KPI | Baseline | Objetivo 30 días | Objetivo 90 días | Valor Actual | Estado`.
8. Guarda el archivo.

**Resultado Esperado:**
Una hoja Excel con el tablero completo del Plan CAPA, lista para ser usada como herramienta de seguimiento operativo.

---

## 7. Resumen

### Lo que Construiste en este Laboratorio

En 90 minutos aplicaste un flujo completo de **Gestión Inteligente de Operaciones asistida por IA**, produciendo artefactos profesionales de calidad empresarial:

| Bloque | Actividad | Artefacto Producido |
|---|---|---|
| **Bloque 1** | Clasificación automática de 20 tickets | Tabla Excel con categoría, severidad, impacto y área responsable |
| **Bloque 2** | Priorización inteligente con criterios SLA | Cola de atención priorizada con justificación y análisis ejecutivo |
| **Bloque 3** | RCA estructurado (5 Porqués + Ishikawa) | Documento Word con análisis completo del incidente INC-2024-0847 |
| **Bloque 4** | Plan CAPA con KPIs de seguimiento | Tablero Excel + Sección Word con acciones correctivas y preventivas |

### Conceptos Clave Aplicados

- **AIOps en práctica:** Usaste Copilot como "capa cognitiva" sobre procesos ITSM, exactamente como describe la arquitectura de referencia de la lección 3.1.
- **Reducción de MTTD/MTTR:** La clasificación automática y la priorización inteligente son mecanismos directos para reducir el tiempo de detección y resolución de incidentes.
- **Prompt Engineering avanzado:** Aplicaste prompts estructurados con criterios explícitos, refinamiento iterativo y anclaje de contexto para obtener artefactos de calidad profesional.
- **Documentación como activo operativo:** El documento RCA y el Plan CAPA son artefactos reutilizables que alimentan la base de conocimiento (KB) y los runbooks del equipo de IT.
- **Framework CAPA:** Diferenciaste entre acciones correctivas (eliminar causas existentes) y preventivas (evitar recurrencia futura), aplicando KPIs medibles para cada una.

### Conexión con los Temas del Curso

Este laboratorio integra directamente los conceptos de:
- **Tema 3.1 — Gestión Inteligente de Operaciones:** Clasificación NLP de tickets, correlación de incidentes, asistencia en diagnóstico y documentación automática en ITSM.
- **Tema 3.2 — Resiliencia Proactiva:** El Plan CAPA con acciones preventivas y KPIs de seguimiento es la implementación práctica de la resiliencia proactiva: no solo resolver incidentes, sino evitar que ocurran.

### Recursos de Referencia

| Recurso | URL / Referencia |
|---|---|
| ITIL 4 Foundation — Gestión de Incidentes y Problemas | [peoplecert.org/itil-4-foundation](https://www.peoplecert.org/browse-certifications/it-governance-and-service-management/ITIL-1/itil-4-foundation-2565) |
| Google SRE — Gestión de Incidentes | [sre.google/sre-book](https://sre.google/sre-book/) |
| Microsoft Copilot — Documentación oficial | [learn.microsoft.com/copilot](https://learn.microsoft.com/en-us/copilot/) |
| Metodología 5 Porqués — ASQ | [asq.org/quality-resources/five-whys](https://asq.org/quality-resources/five-whys) |
| Diagrama de Ishikawa — ASQ | [asq.org/quality-resources/fishbone](https://asq.org/quality-resources/fishbone) |
| Framework CAPA — ISO 9001 | Referencia a la norma ISO 9001:2015, cláusula 10.2 |

---
