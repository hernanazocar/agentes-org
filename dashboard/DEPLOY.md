# 🚀 Deploy Dashboard BackOffice a Vercel

## Opción A: Deploy Automático desde GitHub (Recomendado)

### 1. Subir cambios a GitHub

```bash
cd /Users/hernanazocar/agentes-org
git add dashboard/
git commit -m "Add BackOffice dashboard"
git push origin main
```

### 2. Conectar con Vercel

1. Ve a: https://vercel.com/signup
2. Haz login con tu cuenta de GitHub
3. Click en **"Add New Project"**
4. Selecciona el repositorio: `hernanazocar/agentes-org`
5. Configuración:
   - **Framework Preset:** Other
   - **Root Directory:** `dashboard`
   - **Build Command:** (dejar vacío)
   - **Output Directory:** (dejar vacío)
6. Click en **"Deploy"**

### 3. Tu dashboard estará disponible en:
```
https://agentes-org.vercel.app
```

---

## Opción B: Deploy Manual con Vercel CLI

### 1. Instalar Vercel CLI

```bash
npm install -g vercel
```

### 2. Login a Vercel

```bash
vercel login
```

### 3. Deploy

```bash
cd /Users/hernanazocar/agentes-org/dashboard
vercel
```

Sigue las instrucciones:
- Link to existing project? **N**
- What's your project's name? **backoffice-dashboard**
- In which directory is your code located? **.**
- Want to override settings? **N**

### 4. Deploy a Producción

```bash
vercel --prod
```

---

## 🌐 Conectar Dominio Personalizado (backoffice.cl)

### 1. En Vercel Dashboard

1. Ve a tu proyecto en: https://vercel.com/dashboard
2. Click en tu proyecto **backoffice-dashboard**
3. Ve a la pestaña **"Settings"**
4. Click en **"Domains"**
5. Agrega tu dominio: `backoffice.cl`
6. Click en **"Add"**

### 2. Configurar DNS

Vercel te dará instrucciones específicas. Generalmente necesitas:

**Si usas el dominio raíz (backoffice.cl):**
- Tipo: `A`
- Nombre: `@`
- Valor: `76.76.21.21`

**Si usas un subdominio (dashboard.backoffice.cl):**
- Tipo: `CNAME`
- Nombre: `dashboard`
- Valor: `cname.vercel-dns.com`

### 3. Esperar Propagación DNS

- Tiempo: 5 minutos a 48 horas
- Vercel configurará SSL automáticamente

---

## ✅ Resultado Final

Tu dashboard estará disponible en:
- ✅ `https://agentes-org.vercel.app` (automático)
- ✅ `https://backoffice.cl` (después de configurar DNS)

**Actualizaciones:** Cada vez que hagas `git push`, Vercel actualizará automáticamente.

---

## 📞 Soporte

- Vercel Docs: https://vercel.com/docs
- Configurar dominios: https://vercel.com/docs/concepts/projects/domains
