# Configurando tu Agente de IA Personal con OpenClaw

Despliegue y configuración de un asistente de IA autoalojado en un entorno VPS dedicado, integrado mediante OpenClaw, control de versiones seguro y validación de infraestructura.

---

## 🚀 Arquitectura y Stack Tecnológico

| Componente | Detalle de Implementación |
| :--- | :--- |
| **Infraestructura** | Servidor VPS remoto con acceso seguro mediante clave SSH (`ed25519`) |
| **Orquestador de IA** | OpenClaw (instancia local en entorno de workspace) |
| **Proveedor de Modelos** | LiteLLM (Gateway corporativo integrado) |
| **Control de Versiones** | Git / GitHub (Subida de workspace asegurada por SSH) |

---

## 📋 Proceso de Despliegue y Configuración

El despliegue se ha ejecutado estrictamente en el orden recomendado para evitar errores de infraestructura y dependencias:

1. **Acceso y Validación del Entorno:**
   * Conexión SSH exitosa al VPS remoto.
   * Verificación de recursos del sistema operativo y disponibilidad de red.

2. **Instalación y Configuración de OpenClaw:**
   * Instalación limpia del binario y dependencias en el servidor.
   * Configuración del proveedor **LiteLLM** ingresando la API Key correspondiente.
   * Activación de **hooks** y omisión intencional (según directrices) de Skills y Channel Workflows para fases posteriores.

3. **Personalización del Agente:**
   * Interacción conversacional directa a través del chat local para definir los atributos principales de identidad:
     * **Name:** Kai
     * **Emoji:** 🤖
     * **Greeting:** ¡Hola! Soy Kai, tu asistente personal. ¿En qué puedo ayudarte hoy?
   * Verificación de la correcta persistencia de la identidad en `~/.openclaw/workspace/IDENTITY.md`.

4. **Seguridad y Control de Versiones:**
   * Generación y registro de credenciales SSH dedicadas en GitHub.
   * Inicialización del repositorio git en el workspace (`~/.openclaw/workspace`).
   * Auditoría previa de seguridad para garantizar la exclusión de archivos sensibles (`.env`, `openclaw.json`, credenciales o tokens).
   * Creación del commit inicial y sincronización exitosa con la rama principal del repositorio remoto.

---
## 📸 Evidencias del Proyecto

Las siguientes capturas demuestran el cumplimiento de cada fase del despliegue y configuración:

* **Captura del Repositorio en GitHub:** `workspace/01-captura-repositorio-openclaw-github.png`
* **OpenClaw Instalado y Modelo DeepSeek:** `workspace/02-openclaw-instalado-y-modelo-deepseek.png`
* **LiteLLM Conectado:** `workspace/03-litellm-conectado.png`
* **OpenClaw Instalado (Servidor):** `workspace/04-openclaw-instalado.png`
* **Chat Local con Respuesta Válida:** `workspace/05-chat-local-ia-devuelve-respuesta-valida.png`
* **Personalización Conversacional:** `workspace/06-personalizacion-conversando-con-openclaw.png`
* **Configuración de Clave SSH para Git Push:** `workspace/07-clave-configurada-de-gitpush-al-servidor.png`
---

## ✅ Checklist de Cumplimiento

* [x] OpenClaw correctamente instalado y accesible en el VPS.
* [x] Proveedor LiteLLM configurado y conectado al modelo de IA.
* [x] Verificación de respuesta válida de la IA en el chat local.
* [x] Repositorio remoto creado y sincronizado en GitHub.
* [x] Workspace respaldado (`~/.openclaw/workspace`) subido de forma segura.
* [x] Archivo `.openclaw/workspace/IDENTITY.md` presente con Name, Emoji y Greeting personalizados.
* [x] Personalización realizada mediante interacción conversacional con el agente.
* [x] Autenticación SSH configurada correctamente para operaciones `git push`.
* [x] Historial de commits registrado con el contenido del workspace.
* [x] Ausencia total de archivos sensibles o credenciales en el repositorio público/privado.
* [x] Conexión establecida mediante terminal SSH.
* [x] Secuencia de instalación ejecutada de forma ordenada.

---

## 📦 Referencia de Entrega

* **Repositorio de GitHub:** `https://github.com/mbcastelblanco/openclaw-mbcastelblanco`