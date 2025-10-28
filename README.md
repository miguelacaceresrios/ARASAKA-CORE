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
📦 isometrical-network/
├─ 🧠 arasaka-core/
│  ├─ src/
│  │  ├─ api/
│  │  │  ├─ server.js          # Servidor principal (Express)
│  │  │  └─ routes.js          # Endpoints REST
│  │  ├─ db/
│  │  │  ├─ arasaka.db         # Base de datos SQLite
│  │  │  └─ schema.sql         # Definición de tablas
│  │  ├─ logic/
│  │  │  ├─ tasks.js           # Lógica de tareas y XP
│  │  │  ├─ ranking.js         # Cálculo de puntuaciones
│  │  │  └─ projects.js        # Gestión de proyectos
│  │  └─ core.js               # Inicialización del sistema
│  ├─ .env.example
│  └─ README.md
│
├─ 🤖 bots/
│  ├─ hatsune-bot/             # Bot personalizado de usuario
│  │  ├─ src/bot.js
│  │  ├─ .env
│  │  └─ profile.json
│  ├─ reisen-bot/
│  └─ luka-bot/
│
└─ docs/
   ├─ architecture.md
   ├─ api_reference.md
   ├─ changelog.md
   └─ internal_policies.md
