<!-- ======================================================= -->
<!--                  ISOMETRICAL GAME COMPANY                -->
<!--                DIVISIÓN DE SISTEMAS INTELIGENTES         -->
<!-- ======================================================= -->
<!--                      ARASAKA CORE                        -->
<!-- ======================================================= -->

# ISOMETRICAL | ARASAKA CORE  
**Versión:** 1.0.0 (Alpha)  
**Estado:** En desarrollo activo  
**Autor:** miguelacaceresrios

---

## 1. Descripción General

**ARASAKA CORE** es el sistema de inteligencia central desarrollado por **Isometrical Game Company**.  
Actúa como el núcleo de control y sincronización para la gestión interna de proyectos, tareas y bots personalizados dentro del entorno privado de la organización.

El sistema coordina los proyectos activos, registra tareas, mantiene puntajes globales de productividad y sirve como base de comunicación entre el equipo humano y los bots individuales asociados a cada miembro del equipo.

---

## 2. Objetivos del Sistema

1. Centralizar la gestión de proyectos y tareas de la empresa.  
2. Proveer una capa de comunicación estandarizada para bots personalizados (por empleado).  
3. Mantener un ranking dinámico de desempeño basado en tareas completadas.  
4. Permitir el registro, consulta y actualización de tareas mediante comandos en chat (Discord o Telegram).  
5. Establecer una API modular para conectar bots, paneles o integraciones futuras.

---

## 3. Características Técnicas

| Componente | Descripción |
|-------------|-------------|
| Núcleo de datos | Base de datos central de proyectos, tareas y usuarios. |
| API REST | Comunicación entre bots y el sistema central. |
| WebSocket opcional | Sincronización en tiempo real para eventos o actualizaciones. |
| Módulo de ranking | Calcula puntajes globales por tareas completadas. |
| Integración multi-bot | Cada empleado puede tener su propio bot con identidad personalizada. |
| Canal de proyectos | Espacio donde los bots pueden registrar tareas automáticamente según formato definido. |

---

## 4. Arquitectura del Proyecto

```bash
src/
├─ commands/
│ ├─ alert.js # Enviar mensajes a canales globales
│ ├─ registrar.js # Crear nuevas tareas
│ ├─ tareas.js # Consultar tareas por estado
│ ├─ completar.js # Marcar tareas finalizadas
│ ├─ help.js # Panel de ayuda general
│ └─ ping.js # Prueba de conexión
│
├─ utils/
│ ├─ jsonHandler.js # Manejo seguro de archivos JSON
│ └─ notify.js # Sistema de alertas internas
│
├─ data/
│ ├─ tareas.json
│ ├─ proyectos.json
│ └─ ranking.json
│
├─ index.js # Núcleo principal del bot
└─ deploy-commands.js # Registro de comandos con Discord API
