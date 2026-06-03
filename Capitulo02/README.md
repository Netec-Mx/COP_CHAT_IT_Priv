# Generación de scripts, revisión de código, documentación técnica automatizada y apoyo en procesos de auditoría con Copilot.

## 1. Metadatos

| Atributo | Detalle |
|---|---|
| **Duración estimada** | 90 minutos |
| **Complejidad** | Alta (Hard) |
| **Nivel de Bloom** | Crear |
| **Módulo** | 2 — Automatización del Ciclo de Desarrollo |
| **ID de laboratorio** | 02-00-01 |
| **Idioma de trabajo** | Español (prompts y artefactos) / Inglés (código y comandos) |

---

## 2. Descripción General

Este laboratorio aplica directamente los conceptos de automatización del SDLC vistos en la lección 2.1, llevándolos al plano práctico mediante cuatro escenarios encadenados. Los participantes usarán **Microsoft 365 Copilot Chat** como asistente de desarrollo y auditoría técnica para: generar scripts funcionales en PowerShell y Python orientados a tareas de IT y QA, revisar código con errores intencionales para identificar bugs, vulnerabilidades y malas prácticas, producir documentación técnica completa a partir de los scripts generados, y simular una auditoría técnica de automatización generando checklists, hallazgos y un reporte ejecutivo estructurado. Ningún escenario requiere ejecutar código en un entorno real; todo el trabajo se realiza a nivel de generación, análisis y documentación textual con Copilot.

---

## 3. Objetivos de Aprendizaje

Al finalizar este laboratorio, el participante será capaz de:

- [ ] **Generar** scripts de automatización funcionales en PowerShell y Python usando prompts de ingeniería orientados a código en Copilot Chat.
- [ ] **Revisar** fragmentos de código con errores intencionales mediante Copilot para obtener diagnósticos detallados, versiones corregidas y recomendaciones de seguridad alineadas con estándares como OWASP y CIS Controls.
- [ ] **Automatizar** la creación de documentación técnica (README, especificación de parámetros, guía de uso, notas de mantenimiento) a partir de scripts generados, exportando el resultado a un documento Word.
- [ ] **Simular** un proceso de auditoría técnica de scripts de automatización usando Copilot para producir un checklist de buenas prácticas, identificar no conformidades y redactar un reporte ejecutivo de auditoría.
- [ ] **Aplicar** técnicas de prompt engineering iterativo (follow-up prompts, refinamiento de contexto, instrucciones de formato) para mejorar progresivamente la calidad de los artefactos generados por Copilot.

---

## 4. Prerrequisitos

### Conocimiento previo

| Área | Nivel requerido |
|---|---|
| Uso de Copilot Chat (prompts básicos) | Intermedio — haber completado Lab 01 o equivalente |
| Lectura de código PowerShell / Python | Básico — reconocer variables, funciones, bucles |
| Conceptos de CI/CD y SDLC | Básico — lección 2.1 revisada |
| Documentación técnica (README, docstrings) | Conceptual — saber qué es y para qué sirve |
| Auditoría técnica de software | Conceptual — conocer objetivos y tipos de hallazgos |

### Acceso y herramientas

| Requisito | Estado esperado antes de iniciar |
|---|---|
| Cuenta Microsoft 365 con licencia Copilot activa | ✅ Verificado con el instructor |
| Acceso a [copilot.microsoft.com](https://copilot.microsoft.com) | ✅ Sesión iniciada |
| Microsoft Word (Online o Desktop) | ✅ Disponible en la suite M365 |
| Navegador actualizado (Edge 120+ / Chrome 120+) | ✅ Instalado |
| Visual Studio Code 1.85+ (opcional) | ⬜ Recomendado para visualizar scripts |
| Carpeta de trabajo creada en OneDrive | ✅ `Mis documentos > Lab02-00-01` |

---

## 5. Entorno de Laboratorio

### Configuración inicial del entorno

Antes de comenzar los ejercicios, ejecuta los siguientes pasos de preparación:

**Paso A — Verificar acceso a Copilot Chat**

1. Abre tu navegador y navega a `https://copilot.microsoft.com`.
2. Inicia sesión con tu cuenta corporativa Microsoft 365.
3. Confirma que el chat está disponible y que aparece el selector de modo (Web / Work).
4. Selecciona el modo **Work** para que Copilot tenga contexto de tu organización M365.
5. Escribe el siguiente prompt de verificación:

```
Hola Copilot. Confirma que puedes ayudarme con generación de código PowerShell y Python, revisión de scripts y documentación técnica. Responde siempre en español.
```

**Resultado esperado:** Copilot confirma sus capacidades en español.

**Paso B — Crear documento de trabajo en Word**

1. Ve a `https://office.com` y abre **Word Online**.
2. Crea un documento nuevo y nómbralo: `Lab02-00-01_Artefactos_[TuNombre].docx`.
3. Guárdalo en OneDrive en la carpeta `Lab02-00-01`.
4. Este documento será tu repositorio de artefactos durante todo el laboratorio. Añade el siguiente encabezado inicial:

```
LAB 02-00-01 — Artefactos de Trabajo
Participante: [Tu nombre]
Fecha: [Fecha actual]
---
SECCIÓN 1: Scripts Generados
SECCIÓN 2: Revisión de Código
SECCIÓN 3: Documentación Técnica
SECCIÓN 4: Reporte de Auditoría
```

> ⚠️ **Recordatorio de privacidad:** No ingreses datos reales de tu organización en Copilot Chat. Todos los escenarios de este laboratorio usan datos ficticios.

---

## 6. Desarrollo Paso a Paso

El laboratorio se divide en **cuatro escenarios** encadenados. Cada escenario construye sobre el anterior. Sigue el orden indicado.

---

### Escenario 1: Generación de Scripts de Automatización con Copilot

**Objetivo del escenario:** Usar Copilot Chat con técnicas de prompt engineering para generar scripts funcionales de automatización de IT en PowerShell y Python, aplicando el patrón de prompts iterativos aprendido en la lección 2.1.

---

#### Paso 1.1 — Generar un script PowerShell de verificación de servicios críticos

**Objetivo:** Crear un script PowerShell que verifique el estado de servicios críticos de Windows y genere un reporte en archivo de texto.

**Instrucciones:**

1. En Copilot Chat (modo Work), escribe el siguiente prompt inicial:

```
Actúa como un ingeniero de automatización de IT senior.
Genera un script de PowerShell que realice las siguientes tareas:
1. Verifique el estado de los siguientes servicios de Windows: 'wuauserv', 'WinDefend', 'EventLog', 'Spooler', 'BITS'.
2. Para cada servicio, registre: nombre, estado actual (Running/Stopped), tipo de inicio y si está configurado como automático.
3. Genere un reporte en un archivo de texto llamado 'ServiceReport_[fecha].txt' en la ruta C:\Reports\.
4. Si algún servicio crítico está detenido, muestre una advertencia en consola con color rojo.
5. Incluye manejo de errores con try/catch y comentarios explicativos en cada sección.
Responde siempre en español para las explicaciones, pero el código debe estar en inglés.
```

2. Revisa el script generado. Identifica si incluye: manejo de errores, comentarios, generación de archivo de reporte y alertas de color.

3. Si el script no incluye alguno de estos elementos, usa el siguiente **follow-up prompt** de refinamiento:

```
El script generado es un buen punto de partida. Por favor, mejóralo con los siguientes cambios:
- Agrega una función separada llamada 'Get-ServiceStatus' que encapsule la lógica de verificación.
- Incluye un parámetro de entrada '-OutputPath' para que el usuario pueda especificar la ruta del reporte.
- Agrega una sección de resumen al final del reporte que indique cuántos servicios están activos y cuántos detenidos.
- Asegúrate de que el script sea compatible con PowerShell 5.1 y PowerShell 7.
```

4. Copia el script final generado en tu documento Word bajo **SECCIÓN 1: Scripts Generados**, con la etiqueta `Script 1A — PowerShell Verificación de Servicios`.

**Salida esperada:** Un script PowerShell de aproximadamente 50–80 líneas con funciones definidas, manejo de errores `try/catch`, parámetros de entrada, generación de archivo `.txt` y alertas de consola con `Write-Host -ForegroundColor Red`.

---

#### Paso 1.2 — Generar un script Python de pruebas de conectividad

**Objetivo:** Crear un script Python multiplataforma que realice pruebas de conectividad a una lista de hosts y genere un reporte JSON.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Actúa como un ingeniero de QA y automatización de red.
Genera un script de Python 3.10+ que realice las siguientes tareas:
1. Reciba como argumento de línea de comandos un archivo CSV con dos columnas: 'hostname' y 'port'.
2. Para cada entrada del CSV, intente establecer una conexión TCP al host y puerto especificados con un timeout de 3 segundos.
3. Registre el resultado de cada prueba: hostname, port, estado ('reachable'/'unreachable'), tiempo de respuesta en milisegundos y timestamp.
4. Genere un reporte en formato JSON llamado 'connectivity_report.json'.
5. Muestre un resumen en consola con estadísticas: total de hosts probados, porcentaje de disponibilidad y el host con mayor latencia.
6. Usa las librerías estándar de Python (socket, csv, json, time, argparse, datetime). No uses librerías externas.
7. Incluye docstrings en todas las funciones y manejo de excepciones robusto.
Responde siempre en español para las explicaciones, pero el código en inglés.
```

2. Analiza el script generado. Verifica que use únicamente librerías estándar de Python y que incluya docstrings.

3. Aplica el siguiente prompt de refinamiento orientado a buenas prácticas de CI/CD (conexión con lección 2.1):

```
Excelente. Ahora mejora el script con estas adiciones orientadas a pipelines CI/CD:
- Agrega un argumento '--fail-threshold' que reciba un porcentaje (0-100). Si la disponibilidad total es menor a ese umbral, el script debe terminar con exit code 1 (para que un pipeline CI/CD lo detecte como fallo).
- Agrega logging estructurado usando el módulo 'logging' de Python con nivel configurable via argumento '--log-level'.
- Asegúrate de que el script tenga un bloque 'if __name__ == "__main__"' correcto.
```

4. Copia el script final en tu documento Word bajo **SECCIÓN 1**, con la etiqueta `Script 1B — Python Pruebas de Conectividad`.

**Salida esperada:** Un script Python de aproximadamente 80–120 líneas con `argparse`, manejo de sockets TCP, generación de JSON, logging estructurado, docstrings en cada función y exit codes para integración con pipelines.

---

#### Paso 1.3 — Reflexión sobre prompt engineering

**Objetivo:** Documentar las lecciones aprendidas sobre la técnica de prompts iterativos.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt de meta-reflexión:

```
Basándote en los dos scripts que generamos (PowerShell de verificación de servicios y Python de conectividad), explícame:
1. ¿Qué elementos de un buen prompt para generación de código son más importantes?
2. ¿Qué diferencias hay entre hacer un prompt de una sola vez vs. usar follow-up prompts iterativos?
3. Dame 3 recomendaciones específicas para mejorar prompts de generación de código en el contexto de automatización de IT.
Responde en español con formato de lista numerada.
```

2. Copia la respuesta de Copilot en tu documento Word al final de la **SECCIÓN 1**, con la etiqueta `Reflexión 1C — Lecciones de Prompt Engineering`.

---

### Escenario 2: Revisión de Código Asistida por Copilot

**Objetivo del escenario:** Analizar fragmentos de código con errores intencionales (bugs lógicos, vulnerabilidades de seguridad y malas prácticas) usando Copilot Chat para obtener un diagnóstico detallado y versiones corregidas.

---

#### Paso 2.1 — Revisar un script PowerShell con problemas de seguridad y lógica

**Objetivo:** Identificar y corregir errores en un script PowerShell de gestión de usuarios que contiene vulnerabilidades y bugs intencionales.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt incluyendo el código problemático:

```
Actúa como un experto en seguridad y revisión de código PowerShell con conocimiento de CIS Controls y mejores prácticas de scripting.
Revisa el siguiente script de PowerShell e identifica TODOS los problemas que encuentres, clasificándolos en estas categorías:
- 🔴 CRÍTICO: Vulnerabilidades de seguridad o errores que causan fallos
- 🟡 ADVERTENCIA: Malas prácticas o código no optimizado
- 🟢 SUGERENCIA: Mejoras de legibilidad o mantenibilidad

Para cada problema encontrado, indica:
1. Número de línea aproximado
2. Descripción del problema
3. Por qué es un problema (impacto)
4. Código corregido para esa sección

Aquí está el script a revisar:

```powershell
# Script de gestión de usuarios - v1.0
$password = "Admin123!"
$users = Get-Content "C:\users.txt"

foreach($u in $users){
    $secPass = $password
    New-LocalUser -Name $u -Password $secPass -FullName $u
    Add-LocalGroupMember -Group "Administrators" -Member $u
    Write-Host "User $u created"
}

function Check-Admin {
    $result = Invoke-Expression $args[0]
    return $result
}

$logFile = "C:\log.txt"
Add-Content $logFile "Script executed at $(Get-Date)"

if($users.Count = 0){
    Write-Host "No users found"
}
```

Responde en español con el análisis completo y luego proporciona el script completo corregido.
```

> **Nota:** El bloque de código del script problemático debe ser pegado directamente en el chat. En la práctica, el triple backtick cierra el bloque de código del prompt; escribe el prompt y el código como un solo mensaje en Copilot Chat.

2. Revisa el análisis de Copilot. Verifica que haya identificado al menos los siguientes problemas intencionales:
   - Contraseña en texto plano (`$password = "Admin123!"`)
   - Uso peligroso de `Invoke-Expression` (riesgo de inyección de código)
   - Todos los usuarios se agregan al grupo `Administrators` (escalación de privilegios)
   - Error de asignación en lugar de comparación (`= 0` en lugar de `-eq 0`)
   - La contraseña no se convierte a `SecureString`

3. Si Copilot no identificó alguno de estos problemas, usa el siguiente follow-up prompt:

```
Gracias por el análisis. Noto que no mencionaste [el problema específico que falta]. ¿Puedes revisar específicamente esa línea y explicar el riesgo de seguridad asociado según las mejores prácticas de OWASP o CIS Controls?
```

4. Copia el análisis completo y el script corregido en tu documento Word bajo **SECCIÓN 2: Revisión de Código**, con la etiqueta `Revisión 2A — PowerShell Gestión de Usuarios`.

**Salida esperada:** Un análisis estructurado con al menos 5 problemas identificados (mínimo 2 críticos de seguridad), explicaciones de impacto y un script corregido que use `ConvertTo-SecureString`, elimine `Invoke-Expression`, use `-eq` para comparación y no asigne automáticamente el rol de Administrador.


---

#### Paso 2.2 — Revisar un script Python con errores lógicos y de rendimiento

**Objetivo:** Analizar un script Python de procesamiento de logs con bugs lógicos, ineficiencias de rendimiento y problemas de manejo de excepciones.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt con el código problemático:

```
Actúa como un revisor de código Python senior con experiencia en optimización de rendimiento y buenas prácticas PEP 8.
Analiza el siguiente script Python que procesa archivos de log de un servidor web. Identifica todos los problemas y clasifícalos igual que antes (🔴 CRÍTICO, 🟡 ADVERTENCIA, 🟢 SUGERENCIA).

Para cada problema, explica: qué está mal, cuál es el impacto en rendimiento o seguridad, y cómo corregirlo.

Script a revisar:

import os
import json

def process_logs(log_file):
    errors = []
    warnings = []
    data = open(log_file).read()
    lines = data.split('\n')
    
    for i in range(0, len(lines)):
        line = lines[i]
        if 'ERROR' in line:
            errors.append(line)
        if 'WARNING' in line:
            warnings.append(line)
    
    result = {}
    result['errors'] = errors
    result['warnings'] = warnings
    result['total'] = len(errors) + len(warnings)
    
    output_file = open('output.json', 'w')
    json.dump(result, output_file)
    
    return result

def get_critical_errors(log_file):
    all_errors = []
    data = open(log_file).read()
    for line in data.split('\n'):
        if 'ERROR' in line:
            all_errors.append(line)
    return all_errors

logs_dir = '/var/logs'
for f in os.listdir(logs_dir):
    process_logs(logs_dir + '/' + f)

Al final, proporciona el script completo refactorizado siguiendo PEP 8 y buenas prácticas. Responde en español.
```

2. Verifica que Copilot haya identificado al menos los siguientes problemas intencionales:
   - Archivo abierto sin `with` statement (recurso no liberado correctamente)
   - Código duplicado entre `process_logs` y `get_critical_errors`
   - Uso de `range(0, len(lines))` en lugar de iterar directamente sobre `lines`
   - Concatenación de rutas con `+` en lugar de `os.path.join()`
   - No hay manejo de excepciones para archivos que no existen o no son legibles
   - El archivo de salida siempre se llama `output.json` (sobreescritura en bucle)

3. Copia el análisis y el script refactorizado en tu documento Word bajo **SECCIÓN 2**, con la etiqueta `Revisión 2B — Python Procesamiento de Logs`.

**Salida esperada:** Análisis con al menos 6 problemas identificados y un script refactorizado que use `with open()`, elimine código duplicado con una función auxiliar, use `os.path.join()`, incluya manejo de excepciones y genere archivos de salida con nombres únicos.

**Verificación:**
- [ ] El problema del archivo no cerrado (`open()` sin `with`) fue identificado.
- [ ] La duplicación de código fue detectada como problema de mantenibilidad.
- [ ] El script refactorizado usa `with open(...) as f:` en todos los accesos a archivos.
- [ ] Se usa `os.path.join()` para construir rutas.
- [ ] El script refactorizado incluye al menos un bloque `try/except`.

---

#### Paso 2.3 — Generar un resumen ejecutivo de revisión de código

**Objetivo:** Producir un resumen ejecutivo consolidado de los hallazgos de ambas revisiones, siguiendo el patrón de síntesis de Copilot aplicado en pipelines CI/CD.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Basándote en las dos revisiones de código que realizamos en esta sesión (el script PowerShell de gestión de usuarios y el script Python de procesamiento de logs), genera un resumen ejecutivo de revisión de código con el siguiente formato:

## Resumen Ejecutivo — Revisión de Código
**Fecha:** [fecha actual]
**Revisor:** Microsoft 365 Copilot (asistido por IA)

### Estadísticas Generales
- Total de problemas identificados: [número]
- Problemas críticos: [número]
- Advertencias: [número]
- Sugerencias: [número]

### Top 3 Hallazgos Críticos
[Lista los 3 más importantes con una línea de descripción cada uno]

### Riesgos de Seguridad Identificados
[Párrafo de 3-4 líneas]

### Recomendaciones Prioritarias
[Lista numerada de 5 acciones concretas]

### Próximos Pasos Sugeridos
[Lista de 3 acciones para el equipo de desarrollo]

Responde en español con formato Markdown limpio.
```

2. Copia el resumen ejecutivo en tu documento Word bajo **SECCIÓN 2**, con la etiqueta `Resumen 2C — Resumen Ejecutivo de Revisión de Código`.

---

### Escenario 3: Documentación Técnica Automatizada

**Objetivo del escenario:** Usar Copilot Chat para generar documentación técnica completa y profesional a partir de los scripts creados en el Escenario 1, produciendo artefactos listos para un repositorio corporativo.

**Tiempo estimado:** 20 minutos

---

#### Paso 3.1 — Generar un README completo para el Script PowerShell

**Objetivo:** Crear documentación README profesional para el script de verificación de servicios generado en el Paso 1.1.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Actúa como un technical writer especializado en documentación de scripts de automatización de IT.
Basándote en el script PowerShell de verificación de servicios que generamos anteriormente (que incluye la función Get-ServiceStatus, parámetro -OutputPath, manejo de errores y generación de reporte en .txt), genera un archivo README.md completo y profesional con las siguientes secciones:

# [Nombre del Script]
## Descripción
[Qué hace el script, en 2-3 párrafos]

## Requisitos del Sistema
[Tabla con OS, versión de PowerShell, permisos necesarios]

## Instalación y Configuración
[Pasos numerados]

## Uso
### Sintaxis
[Bloque de código con la sintaxis completa]

### Parámetros
[Tabla con nombre, tipo, obligatorio/opcional, descripción y valor por defecto]

### Ejemplos de Uso
[Al menos 3 ejemplos con descripción de cada uno]

## Estructura del Reporte Generado
[Descripción del formato del archivo .txt de salida]

## Manejo de Errores
[Tabla de errores comunes, causa y solución]

## Notas de Mantenimiento
[Instrucciones para actualizar la lista de servicios monitoreados]

## Historial de Versiones
[Tabla con versión, fecha y cambios - incluir v1.0.0 como versión inicial]

## Autor y Contacto
[Sección genérica con placeholders]

Genera el README completo en formato Markdown. Responde en español para todo el contenido.
```

2. Revisa el README generado. Verifica que todas las secciones solicitadas estén presentes y que los ejemplos de uso sean coherentes con el script generado.

3. Si falta alguna sección, usa un follow-up prompt específico:

```
El README está casi completo. Por favor, agrega la sección de 'Manejo de Errores' con una tabla que incluya al menos 4 errores comunes (como servicio no encontrado, permisos insuficientes, ruta de salida inválida y timeout de consulta) con su causa probable y pasos de resolución.
```

4. Copia el README completo en tu documento Word bajo **SECCIÓN 3: Documentación Técnica**, con la etiqueta `Doc 3A — README Script PowerShell`.

**Salida esperada:** Un README.md con todas las secciones listadas, tabla de parámetros completa, al menos 3 ejemplos de uso con bloques de código y tabla de manejo de errores.

---

#### Paso 3.2 — Generar especificación técnica para el Script Python

**Objetivo:** Crear una especificación técnica detallada del script Python de conectividad, incluyendo docstrings mejorados y una guía de integración con pipelines CI/CD.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Actúa como un arquitecto de software documentando una herramienta de automatización para el equipo de QA y DevOps.
Basándote en el script Python de pruebas de conectividad que generamos (con argparse, socket TCP, reporte JSON, logging estructurado y --fail-threshold para pipelines CI/CD), genera los siguientes artefactos de documentación:

### ARTEFACTO 1: Docstrings mejorados
Genera los docstrings completos en formato Google Style para cada función del script, incluyendo:
- Descripción de la función
- Args: nombre, tipo y descripción de cada parámetro
- Returns: tipo y descripción del valor de retorno
- Raises: excepciones que puede lanzar
- Example: ejemplo de uso de la función

### ARTEFACTO 2: Guía de Integración CI/CD
Genera una sección de documentación de 300-400 palabras que explique cómo integrar este script en un pipeline de GitHub Actions o Azure Pipelines, incluyendo:
- Un ejemplo de step en formato YAML para GitHub Actions
- Cómo interpretar el exit code para marcar el pipeline como fallido
- Cómo almacenar el reporte JSON como artefacto del pipeline
- Recomendaciones de threshold para diferentes entornos (dev/staging/prod)

### ARTEFACTO 3: Ejemplo de archivo CSV de entrada
Genera un archivo CSV de ejemplo con 8 entradas ficticias representando diferentes tipos de hosts (servidores web, bases de datos, APIs, servicios de monitoreo).

Responde en español para las explicaciones, código en inglés.
```

2. Copia los tres artefactos en tu documento Word bajo **SECCIÓN 3**, con la etiqueta `Doc 3B — Especificación Técnica Script Python`.

**Salida esperada:** Tres artefactos distintos: docstrings en Google Style para al menos 3 funciones, una guía de integración CI/CD con ejemplo YAML funcional y un CSV de ejemplo con 8 entradas ficticias.

---

#### Paso 3.3 — Generar una Guía de Instalación Rápida (Quick Start Guide)

**Objetivo:** Producir una guía de inicio rápido que cubra ambos scripts, diseñada para un técnico de IT que los usará por primera vez.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Crea una Guía de Inicio Rápido (Quick Start Guide) para un técnico de IT de nivel intermedio que necesita usar por primera vez los dos scripts que documentamos: el script PowerShell de verificación de servicios y el script Python de pruebas de conectividad.

La guía debe:
- Tener un máximo de 2 páginas (formato compacto)
- Incluir una sección de prerrequisitos rápidos
- Mostrar el comando mínimo para ejecutar cada script con sus parámetros más comunes
- Incluir una tabla de 'Problemas frecuentes y soluciones rápidas' con 3 entradas por script
- Terminar con una sección '¿Qué hacer si algo falla?' con 5 pasos de diagnóstico genéricos
- Usar lenguaje directo y sin tecnicismos innecesarios

Formato: Markdown. Idioma: Español.
```

2. Copia la guía en tu documento Word bajo **SECCIÓN 3**, con la etiqueta `Doc 3C — Quick Start Guide`.

---

### Escenario 4: Apoyo en Procesos de Auditoría Técnica

**Objetivo del escenario:** Simular una auditoría técnica de los scripts de automatización generados, usando Copilot Chat para producir un checklist de buenas prácticas, identificar no conformidades y redactar un reporte ejecutivo de auditoría estructurado.

---

#### Paso 4.1 — Generar un Checklist de Auditoría de Scripts

**Objetivo:** Crear un checklist completo de buenas prácticas para auditar scripts de automatización de IT, basado en estándares reconocidos.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Actúa como un auditor técnico de IT especializado en automatización y seguridad de scripts.
Genera un checklist exhaustivo de auditoría para evaluar scripts de automatización de IT (PowerShell y Python) en un entorno corporativo.

El checklist debe estar organizado en las siguientes categorías y usar el formato [  ] para cada ítem:

### CATEGORÍA 1: Seguridad (mínimo 8 ítems)
Basado en CIS Controls y principios OWASP, incluyendo: gestión de credenciales, principio de mínimo privilegio, validación de entradas, manejo de secretos, logging de seguridad.

### CATEGORÍA 2: Calidad de Código (mínimo 6 ítems)
Incluyendo: estándares de nomenclatura, modularidad, documentación inline, complejidad ciclomática, cobertura de pruebas.

### CATEGORÍA 3: Manejo de Errores y Resiliencia (mínimo 5 ítems)
Incluyendo: manejo de excepciones, logging de errores, mecanismos de retry, validación de prerrequisitos.

### CATEGORÍA 4: Mantenibilidad y Versionado (mínimo 5 ítems)
Incluyendo: control de versiones, compatibilidad de plataforma, dependencias documentadas, proceso de actualización.

### CATEGORÍA 5: Cumplimiento y Trazabilidad (mínimo 4 ítems)
Incluyendo: logging de auditoría, registro de cambios, aprobación de cambios, documentación de impacto.

Para cada ítem del checklist, incluye entre paréntesis la referencia al estándar aplicable cuando sea relevante (ej: CIS Control 3.1, OWASP A02:2021).

Responde en español con formato Markdown.
```

2. Revisa el checklist. Debe tener un mínimo de 28 ítems distribuidos en las 5 categorías.

3. Copia el checklist en tu documento Word bajo **SECCIÓN 4: Reporte de Auditoría**, con la etiqueta `Auditoría 4A — Checklist de Buenas Prácticas`.

**Salida esperada:** Un checklist estructurado en 5 categorías con al menos 28 ítems en total, referencias a estándares (CIS Controls, OWASP) en los ítems relevantes y formato de checkbox `[ ]`.

---

#### Paso 4.2 — Aplicar el Checklist y Registrar No Conformidades

**Objetivo:** Simular la aplicación del checklist a los scripts generados en el Escenario 1 y documentar las no conformidades encontradas.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Ahora simula ser el auditor que aplica el checklist de auditoría que acabamos de crear a los dos scripts que generamos al inicio del laboratorio: el script PowerShell de verificación de servicios y el script Python de pruebas de conectividad.

Para cada script, realiza lo siguiente:
1. Evalúa cada categoría del checklist e indica qué ítems pasan (✅), fallan (❌) o no aplican (N/A).
2. Para los ítems que fallan, proporciona una descripción específica de la no conformidad encontrada.
3. Para cada no conformidad, asigna un nivel de severidad: ALTA, MEDIA o BAJA.
4. Calcula el porcentaje de cumplimiento por categoría y el porcentaje global.

Presenta los resultados en una tabla con las siguientes columnas:
| ID | Ítem del Checklist | Script PS | Script Python | Severidad si falla | Observación |

Al final, incluye una tabla resumen con el porcentaje de cumplimiento por script y por categoría.

Recuerda que los scripts fueron generados con buenas prácticas, pero pueden tener algunas áreas de mejora. Sé objetivo y realista en la evaluación.

Responde en español.
```

2. Revisa los resultados. Si el porcentaje de cumplimiento es del 100% para ambos scripts (lo cual sería irreal), usa el siguiente follow-up:

```
El resultado parece demasiado optimista. En una auditoría real, incluso scripts bien escritos tienen áreas de mejora. Por favor, revisa más críticamente y considera aspectos como: ¿Los scripts tienen pruebas unitarias automatizadas? ¿Están versionados en un repositorio de control de versiones? ¿Existe un proceso formal de aprobación de cambios documentado? ¿Hay integración con un sistema de gestión de secretos (como Azure Key Vault)?
```

3. Copia la tabla de evaluación y el resumen de cumplimiento en tu documento Word bajo **SECCIÓN 4**, con la etiqueta `Auditoría 4B — Evaluación de No Conformidades`.

**Salida esperada:** Una tabla de evaluación con al menos 28 filas (una por ítem del checklist), indicadores de estado (✅/❌/N/A), nivel de severidad para no conformidades y una tabla resumen con porcentajes de cumplimiento por categoría (ningún script debería tener 100% de cumplimiento).

---

#### Paso 4.3 — Redactar el Reporte Ejecutivo de Auditoría

**Objetivo:** Generar un reporte ejecutivo de auditoría formal que consolide todos los hallazgos, siguiendo la estructura de un documento de auditoría técnica profesional.

**Instrucciones:**

1. En Copilot Chat, escribe el siguiente prompt:

```
Actúa como un auditor técnico senior redactando el reporte ejecutivo final de la auditoría de scripts de automatización.
Basándote en el checklist de auditoría y los resultados de evaluación que generamos, redacta un Reporte Ejecutivo de Auditoría Técnica completo con la siguiente estructura:

---
# REPORTE EJECUTIVO DE AUDITORÍA TÉCNICA
## Scripts de Automatización de IT — Ciclo de Desarrollo
**Clasificación:** Uso Interno
**Versión:** 1.0
**Fecha:** [fecha actual]

## 1. Resumen Ejecutivo
[3-4 párrafos: propósito de la auditoría, alcance, metodología utilizada y conclusión principal]

## 2. Alcance y Metodología
[Tabla con: scripts auditados, versiones, fecha de revisión, metodología (checklist basado en CIS Controls y OWASP), herramientas utilizadas]

## 3. Hallazgos por Categoría
[Para cada categoría del checklist: porcentaje de cumplimiento, hallazgos principales, tabla de no conformidades con ID, descripción, severidad y evidencia]

## 4. Análisis de Riesgo
[Tabla de riesgos con: ID de riesgo, descripción, probabilidad (Alta/Media/Baja), impacto (Alto/Medio/Bajo), nivel de riesgo resultante y estado actual]

## 5. Recomendaciones de Remediación
[Lista priorizada de acciones correctivas con: ID, descripción, prioridad, responsable sugerido, plazo estimado y criterio de aceptación]

## 6. Plan de Acción
[Tabla con roadmap de remediación: acciones de corto plazo (0-30 días), mediano plazo (31-90 días) y largo plazo (91-180 días)]

## 7. Conclusiones y Próxima Auditoría
[Párrafo de cierre y fecha sugerida para auditoría de seguimiento]

## 8. Firmas y Aprobaciones
[Tabla de firmas con roles: Auditor Técnico, Responsable de Automatización, Jefe de IT — con campos de nombre, firma y fecha como placeholders]
---

El reporte debe ser formal, profesional y de entre 600-800 palabras de contenido narrativo (excluyendo tablas). Responde en español.
```

2. Revisa el reporte generado. Verifica que tenga todas las secciones y que el tono sea formal y profesional.

3. Aplica el siguiente prompt de refinamiento final:

```
El reporte es muy bueno. Para finalizarlo, por favor:
1. Agrega en la sección de Recomendaciones de Remediación al menos 2 recomendaciones específicas relacionadas con la integración de estos scripts en un pipeline CI/CD (como las que vimos en la lección sobre automatización del SDLC).
2. En la sección de Análisis de Riesgo, agrega un riesgo relacionado con la falta de firma de artefactos (como cosign/Sigstore) para los scripts empaquetados.
3. Agrega una nota al pie que indique que este reporte fue generado con asistencia de Microsoft 365 Copilot y que los hallazgos fueron validados por el equipo auditor.
```

4. Copia el reporte ejecutivo final en tu documento Word bajo **SECCIÓN 4**, con la etiqueta `Auditoría 4C — Reporte Ejecutivo Final`.

**Salida esperada:** Un reporte ejecutivo de auditoría, con 8 secciones completas, tablas de hallazgos, análisis de riesgo con probabilidad/impacto, plan de acción con roadmap por plazos, recomendaciones relacionadas con CI/CD y nota al pie sobre uso de Copilot.

---

#### Paso 4.4 — Guardar y organizar el documento final

**Objetivo:** Consolidar todos los artefactos en el documento Word y prepararlo para entrega.

**Instrucciones:**

1. Regresa a tu documento Word `Lab02-00-01_Artefactos_[TuNombre].docx`.
2. Verifica que las 4 secciones estén completas con todos sus artefactos:
   - SECCIÓN 1: Scripts 1A, 1B y Reflexión 1C
   - SECCIÓN 2: Revisiones 2A, 2B y Resumen 2C
   - SECCIÓN 3: Documentos 3A, 3B y 3C
   - SECCIÓN 4: Auditoría 4A, 4B y 4C
3. Aplica formato consistente: usa **Título 1** para secciones, **Título 2** para sub-artefactos y **Normal** para el contenido.
4. Agrega una **portada** al documento con: título del laboratorio, tu nombre, fecha y el número de artefactos generados.
5. Guarda el documento en OneDrive (Ctrl+S o File > Save).

---

## 7. Validación y Pruebas del Laboratorio

Una vez completados los 4 escenarios, realiza la siguiente validación integral:

### Lista de Verificación Final

| # | Criterio de Validación | Estado |
|---|---|---|
| 1 | Script PowerShell generado con función, parámetros y manejo de errores | ⬜ |
| 2 | Script Python generado con argparse, logging y exit codes para CI/CD | ⬜ |
| 3 | Reflexión de prompt engineering documentada | ⬜ |
| 4 | Revisión de código PowerShell con mínimo 5 problemas identificados | ⬜ |
| 5 | Revisión de código Python con mínimo 6 problemas identificados | ⬜ |
| 6 | Resumen ejecutivo de revisión de código generado | ⬜ |
| 7 | README completo del script PowerShell (mínimo 8 secciones) | ⬜ |
| 8 | Especificación técnica Python con docstrings, YAML CI/CD y CSV de ejemplo | ⬜ |
| 9 | Quick Start Guide para ambos scripts | ⬜ |
| 10 | Checklist de auditoría con mínimo 28 ítems en 5 categorías | ⬜ |
| 11 | Tabla de evaluación de no conformidades con severidades | ⬜ |
| 12 | Reporte ejecutivo de auditoría con 8 secciones completas | ⬜ |
| 13 | Documento Word guardado en OneDrive con portada y formato consistente | ⬜ |

### Prompt de Auto-Evaluación Final

Usa este prompt en Copilot Chat para obtener una evaluación de la calidad de tu trabajo:

```
Actúa como un evaluador de competencias en Microsoft 365 Copilot y prompt engineering.
He completado un laboratorio de 4 escenarios que incluyó: generación de scripts PowerShell y Python, revisión de código con identificación de vulnerabilidades, generación de documentación técnica (README, docstrings, guía CI/CD) y creación de un reporte de auditoría técnica.

Basándote en las mejores prácticas de prompt engineering y los estándares de documentación técnica, evalúa en una escala del 1 al 5 las siguientes competencias y dame recomendaciones específicas para mejorar:

1. Claridad y especificidad de los prompts utilizados
2. Uso efectivo de follow-up prompts para refinar resultados
3. Calidad de los artefactos técnicos generados
4. Aplicación de estándares de seguridad (OWASP/CIS) en la revisión de código
5. Completitud y profesionalismo del reporte de auditoría

Para cada competencia, dame: puntuación estimada (1-5), justificación y una acción concreta de mejora.
Responde en español.
```

Copia la evaluación de Copilot en tu documento Word como **SECCIÓN 5: Auto-Evaluación**.

---

## 8. Resumen y Recursos Adicionales

### Puntos Clave del Laboratorio

Este laboratorio demostró cómo **Microsoft 365 Copilot Chat actúa como un coproductor técnico** en cuatro dimensiones del ciclo de desarrollo:

1. **Generación de código:** Copilot puede producir scripts funcionales de calidad profesional cuando se le proporcionan prompts específicos con contexto, restricciones técnicas claras y criterios de calidad explícitos. La técnica de follow-up prompts iterativos es esencial para refinar los resultados del primer intento.

2. **Revisión de código:** Copilot identifica eficazmente vulnerabilidades de seguridad (credenciales en texto plano, `Invoke-Expression`, escalación de privilegios), bugs lógicos (operadores incorrectos) y malas prácticas (recursos no liberados, código duplicado), especialmente cuando se le instruye a clasificar los hallazgos por severidad y referenciar estándares como OWASP y CIS Controls.

3. **Documentación técnica:** La generación de READMEs, docstrings, guías de integración CI/CD y Quick Start Guides con Copilot reduce drásticamente el tiempo de documentación, produciendo artefactos estructurados y coherentes que se alinean con los estándares de docs-as-code vistos en la lección 2.1.

4. **Auditoría técnica:** Copilot puede actuar como un auditor asistido por IA, generando checklists basados en estándares reconocidos, evaluando código contra esos criterios, identificando no conformidades con severidades y redactando reportes ejecutivos formales, acelerando significativamente el proceso de auditoría.

### Conexión con la Lección 2.1

| Concepto de la Lección 2.1 | Aplicación en este Laboratorio |
|---|---|
| Copilot Chat para generación de artefactos de pipeline | Scripts con exit codes para CI/CD (Paso 1.2) |
| Docs-as-code y documentación automatizada | README, docstrings y guía CI/CD (Escenario 3) |
| SAST y revisión de seguridad | Identificación de vulnerabilidades OWASP (Escenario 2) |
| Puertas de calidad en pipelines | `--fail-threshold` y lógica de exit code 1 (Paso 1.2) |
| Firma de artefactos (cosign/Sigstore) | Riesgo de auditoría por falta de firma (Paso 4.3) |
| Síntesis de PR y resúmenes de cambios | Resumen ejecutivo de revisión de código (Paso 2.3) |

### Recursos Adicionales

| Recurso | URL |
|---|---|
| Microsoft 365 Copilot — Documentación oficial | [https://learn.microsoft.com/en-us/copilot/microsoft-365/](https://learn.microsoft.com/en-us/copilot/microsoft-365/) |
| OWASP Top 10 (2021) | [https://owasp.org/Top10/](https://owasp.org/Top10/) |
| CIS Controls v8 | [https://www.cisecurity.org/controls/v8](https://www.cisecurity.org/controls/v8) |
| PowerShell Best Practices and Style Guide | [https://poshcode.gitbook.io/powershell-practice-and-style/](https://poshcode.gitbook.io/powershell-practice-and-style/) |
| PEP 8 — Guía de estilo Python | [https://peps.python.org/pep-0008/](https://peps.python.org/pep-0008/) |
| Google Python Style Guide (docstrings) | [https://google.github.io/styleguide/pyguide.html](https://google.github.io/styleguide/pyguide.html) |
| Sigstore cosign — Firma de artefactos | [https://docs.sigstore.dev/cosign/overview/](https://docs.sigstore.dev/cosign/overview/) |
| GitHub Actions — Referencia de workflows | [https://docs.github.com/en/actions](https://docs.github.com/en/actions) |

---

> 📝 **Nota final para el instructor:** Este laboratorio genera un documento Word como entregable principal. Se recomienda evaluar la calidad de los artefactos usando la rúbrica del curso, prestando especial atención a: (1) la evidencia de uso de prompts iterativos (no solo el resultado final), (2) la coherencia entre los hallazgos de auditoría y el código revisado, y (3) la integración de conceptos CI/CD de la lección 2.1 en los artefactos de documentación. Los participantes deben compartir el enlace de OneDrive al documento como método de entrega.
