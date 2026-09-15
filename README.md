# 🏢 BackOffice - Sistema de Agentes IA Automatizados

Sistema de gestión organizacional automatizado con agentes Claude Code que funcionan 24/7 en la nube.

## 📊 Estructura Organizacional

### Gerencia General
- **Reporte consolidado**: 8:00 AM (Chile)
- **Email + Google Calendar**

### 📢 Marketing (Gerente + 3 Trabajadores)
- Community Manager
- Analista de Competencia  
- Coordinador de Marketing

### 💰 Ventas (Gerente + 3 Trabajadores)
- Ejecutivo de Prospección
- Analista de Pipeline
- Coordinador de Seguimiento

### 💻 Desarrollo (Gerente + 3 Trabajadores)
- Analista de Bugs
- Revisor de Features
- Coordinador Técnico

### ⚙️ Operaciones (Gerente + 3 Trabajadores)
- Analista de Sistemas
- Monitor de Incidentes
- Coordinador de Métricas

## 🔄 Flujo de Trabajo Automático

### 6:00 AM - Trabajadores
Cada agente trabajador ejecuta sus análisis y genera reportes en:
```
/reportes/{departamento}/{rol}/YYYY-MM-DD.md
```

### 7:00 AM - Gerentes
Gerentes de área consolidan reportes de su equipo en:
```
/reportes/gerentes/{departamento}/YYYY-MM-DD.md
```

### 8:00 AM - Gerencia General
Reporte final consolidado enviado por email y calendario:
```
/reportes/gerencia-general/YYYY-MM-DD.md
```

## ✨ Tareas Puntuales

Además del flujo automático, se pueden asignar tareas específicas mediante:

### Via Dashboard
1. Abrir dashboard de monitoreo
2. Tab "Asignar Tareas"
3. Seleccionar departamento, agente y prioridad
4. El agente ejecuta la tarea en su próxima corrida

### Via Archivo JSON
Crear archivo en:
```
/tareas/{departamento}/{agente}/pendientes/{tarea-id}.json
```

Formato:
```json
{
  "id": "unique-id",
  "tipo": "puntual",
  "prioridad": "urgente|alta|normal",
  "descripcion": "Analizar competencia X en zona Y",
  "asignado_por": "gerente-{departamento}",
  "fecha_asignacion": "2026-09-14T20:00:00Z",
  "estado": "pendiente"
}
```

El agente mueve el archivo a `/completadas/` al terminar.

## 📁 Estructura del Repositorio

```
agentes-org/
├── tareas/                    # Sistema de tareas
│   ├── marketing/
│   │   ├── community-manager/
│   │   │   ├── pendientes/   # Tareas por ejecutar
│   │   │   └── completadas/  # Tareas finalizadas
│   │   ├── analista-competencia/
│   │   └── coordinador-marketing/
│   ├── ventas/
│   ├── desarrollo/
│   └── operaciones/
├── reportes/                  # Reportes generados
│   ├── marketing/
│   ├── ventas/
│   ├── desarrollo/
│   ├── operaciones/
│   ├── gerentes/             # Reportes consolidados por gerente
│   └── gerencia-general/     # Reporte final diario
└── dashboard/                # Estado en tiempo real
    └── estado-agentes.json   # Estado actual de cada agente
```

## 🎯 Dashboard de Monitoreo

URL: https://claude.ai/artifact/6nn1UToZSNW1gaRVoR7uzk

Funciones:
- ✅ Ver organigrama completo en tiempo real
- ✅ Asignar tareas puntuales a cualquier agente
- ✅ Monitorear actividad y estado de agentes
- ✅ Ver reportes recientes por departamento
- ✅ Métricas consolidadas

## ⚙️ Configuración de Agentes

Cada agente cloud está configurado con:
- **Schedule**: Cron expression en UTC
- **Repository**: Este repositorio (agentes-org)
- **MCP Connectors**: Gmail + Google Calendar
- **Environment**: Anthropic Cloud
- **Model**: Claude Sonnet 5

## 📝 Próximos Pasos

1. ✅ Crear repositorio y estructura
2. ⏳ Crear agentes cloud (17 total)
3. ⏳ Configurar schedules automáticos
4. ⏳ Probar flujo completo

---

**Creado**: 2026-09-14  
**Owner**: hernanazocar  
**Repo**: https://github.com/hernanazocar/agentes-org
