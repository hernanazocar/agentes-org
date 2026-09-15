# 🚀 Guía de Configuración - BackOffice

## Estado Actual ✅

### Completado:
- ✅ Repositorio GitHub creado y configurado
- ✅ Estructura completa de carpetas (tareas, reportes, dashboard)
- ✅ 3 Dashboards de monitoreo en tiempo real
- ✅ Documentación completa del sistema
- ✅ Sistema de tareas automáticas y puntuales diseñado

### Pendiente:
- ⏳ Conectar GitHub en claude.ai
- ⏳ Crear 17 agentes cloud (automatizado)
- ⏳ Activar ejecuciones programadas

---

## 📋 Pasos para Activar el Sistema

### Paso 1: Conectar GitHub (REQUERIDO)

**URL:** https://claude.ai/customize/connectors

1. Buscar "GitHub" en la lista de conectores
2. Click en "Connect"
3. Autorizar cuenta: hernanazocar
4. Confirmar permisos de acceso

**¿Por qué es necesario?**  
Los agentes cloud necesitan acceso al repositorio para:
- Leer tareas pendientes
- Escribir reportes generados
- Actualizar estado del sistema
- Coordinar entre departamentos

---

### Paso 2: Creación Automática de Agentes

Una vez conectado GitHub, volver a la sesión de Claude Code y escribir: **"listo"**

Claude creará automáticamente:

#### 📊 12 Agentes Trabajadores (6:00 AM Chile / 9:00 UTC)

**Marketing:**
1. Community Manager - Análisis RRSS
2. Analista de Competencia - Monitoreo competidores  
3. Coordinador Marketing - Propuestas y estrategia

**Ventas:**
4. Ejecutivo Prospección - Leads nuevos
5. Analista Pipeline - Estado funnel de ventas
6. Coordinador Seguimiento - Follow-ups y reuniones

**Desarrollo:**
7. Analista Bugs - Issues y priorización
8. Revisor Features - Pull requests y code reviews
9. Coordinador Técnico - Roadmap y deuda técnica

**Operaciones:**
10. Analista Sistemas - Uptime y performance
11. Monitor Incidentes - Alertas y postmortems
12. Coordinador Métricas - KPIs operacionales

#### 👔 4 Agentes Gerentes (7:00 AM Chile / 10:00 UTC)

13. Gerente Marketing - Consolida 3 reportes
14. Gerente Ventas - Consolida 3 reportes
15. Gerente Desarrollo - Consolida 3 reportes
16. Gerente Operaciones - Consolida 3 reportes

#### 🎯 1 Agente Gerencia General (8:00 AM Chile / 11:00 UTC)

17. Director Ejecutivo - Consolida 4 reportes gerenciales
    - Envía email a: hernaneduardo.azocar@gmail.com
    - Agenda evento en Google Calendar
    - Genera reporte final en repositorio

---

## 🎛️ Configuración de Cada Agente

**Características comunes:**
- **Modelo:** Claude Sonnet 5
- **Repositorio:** https://github.com/hernanazocar/agentes-org
- **Conectores MCP:** Gmail + Google Calendar
- **Environment:** Anthropic Cloud (24/7)
- **Horario:** Lunes a Viernes
- **Zona horaria base:** UTC (convertido desde Chile)

**Capacidades:**
- ✅ Tareas automáticas diarias
- ✅ Tareas puntuales on-demand
- ✅ Coordinación entre equipos
- ✅ Notificaciones por email
- ✅ Integración con calendario

---

## 📁 Flujo de Trabajo Diario

### 6:00 AM Chile (9:00 UTC) - Trabajadores

Cada agente trabajador:
1. Revisa `tareas/{dept}/{rol}/pendientes/` para tareas puntuales
2. Ejecuta tareas urgentes primero
3. Realiza análisis automático de su área
4. Genera reporte markdown en `reportes/{dept}/{rol}/YYYY-MM-DD.md`
5. Mueve tareas completadas a `/completadas/`
6. Actualiza `dashboard/estado-agentes.json`

### 7:00 AM Chile (10:00 UTC) - Gerentes

Cada gerente de área:
1. Lee reportes de sus 3 trabajadores
2. Identifica patrones y prioridades
3. Consolida información clave
4. Genera reporte gerencial en `reportes/gerentes/{dept}/YYYY-MM-DD.md`
5. Prepara resumen ejecutivo para gerencia

### 8:00 AM Chile (11:00 UTC) - Gerencia General

Agente director:
1. Lee 4 reportes gerenciales
2. Consolida información crítica
3. Genera reporte ejecutivo final
4. **Envía email** con resumen a hernaneduardo.azocar@gmail.com
5. **Crea evento** en Google Calendar con highlights
6. Guarda en `reportes/gerencia-general/YYYY-MM-DD.md`

---

## 🎯 Sistema de Tareas Puntuales

### Asignar tarea desde Dashboard

1. Abrir: https://claude.ai/artifact/5tRB8mR6Vs9kimAtwDNuTJ
2. Tab "Asignar Tareas" (cuando esté implementado)
3. Seleccionar departamento y agente
4. Escribir descripción
5. Elegir prioridad (normal/alta/urgente)

### Asignar tarea manualmente

Crear archivo: `tareas/{dept}/{agente}/pendientes/{uuid}.json`

```json
{
  "id": "unique-uuid",
  "tipo": "puntual",
  "prioridad": "urgente",
  "descripcion": "Analizar competencia X en mercado Y",
  "asignado_por": "gerencia-general",
  "fecha_asignacion": "2026-09-15T10:00:00Z",
  "estado": "pendiente",
  "deadline": "2026-09-15T18:00:00Z"
}
```

El agente lo ejecutará en su próxima corrida (o inmediatamente si se dispara manualmente).

---

## 📊 Dashboards Disponibles

### 1. Dashboard 3D Ejecutivo (Recomendado)
**URL:** https://claude.ai/artifact/5tRB8mR6Vs9kimAtwDNuTJ

Vista isométrica 3D con:
- Plataformas por departamento
- Agentes visuales en tiempo real
- Panel de tareas y métricas
- Rotación interactiva con mouse

### 2. Dashboard NOC (Monitoreo Técnico)
**URL:** https://claude.ai/artifact/Mb79SMGwHqxKjxBWYibu72

Estilo centro de operaciones:
- Métricas del sistema
- Topología de red
- Feed de actividad
- Estado por departamento

### 3. Dashboard Ejecutivo Original
**URL:** https://claude.ai/artifact/6nn1UToZSNW1gaRVoR7uzk

Vista clásica con:
- Organigrama completo
- Asignación de tareas
- Reportes recientes
- Actividad en tiempo real

---

## 🔧 Troubleshooting

### Problema: Agentes no ejecutan
- Verificar que GitHub esté conectado en claude.ai
- Confirmar que los agentes estén habilitados
- Revisar logs en claude.ai/code/routines

### Problema: No llegan emails
- Verificar conector Gmail en claude.ai
- Confirmar email: hernaneduardo.azocar@gmail.com
- Revisar carpeta spam

### Problema: Tareas no se ejecutan
- Verificar formato JSON correcto
- Confirmar que el archivo esté en `/pendientes/`
- Revisar que el agente esté activo

---

## 📞 Soporte

**Repositorio:** https://github.com/hernanazocar/agentes-org  
**Documentación:** Este archivo  
**Dashboards:** Ver sección "Dashboards Disponibles"

---

## 🚀 Próximos Pasos

1. ✅ Conectar GitHub en claude.ai/customize/connectors
2. ⏳ Volver a Claude Code y escribir "listo"
3. ⏳ Esperar creación automática de 17 agentes
4. ⏳ Verificar primera ejecución mañana 6:00 AM
5. ⏳ Revisar email a las 8:00 AM con reporte consolidado

**Tiempo estimado de configuración:** 5 minutos  
**Tiempo hasta primer reporte:** Próximo día hábil 8:00 AM

---

**Última actualización:** 2026-09-14  
**Versión:** 1.0.0  
**Estado:** Listo para activación
