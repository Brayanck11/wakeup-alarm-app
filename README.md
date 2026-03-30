# ⏰ WAKE UP v6 — App de Alarma Inteligente

App de alarma con retos para despertarse, ciclo de sueño, logros y más.

---

## 📱 Cómo compilar el APK (paso a paso)

### Requisitos previos
- Cuenta en [GitHub](https://github.com) (gratis)
- [Git](https://git-scm.com/downloads) instalado en tu PC
- [Node.js 20+](https://nodejs.org) instalado

---

### PASO 1 — Crear repositorio en GitHub

1. Ve a [github.com](https://github.com) e inicia sesión
2. Haz clic en **"New repository"** (botón verde)
3. Nombre: `wakeup-alarm-app`
4. Selecciona **"Public"** (para usar Actions gratis)
5. Haz clic en **"Create repository"**

---

### PASO 2 — Subir el proyecto

Abre una terminal en la carpeta del proyecto y ejecuta:

```bash
# Inicializar git
git init
git add .
git commit -m "WAKE UP v6 - Initial commit"

# Conectar con GitHub (reemplaza TU_USUARIO con tu usuario de GitHub)
git remote add origin https://github.com/TU_USUARIO/wakeup-alarm-app.git
git branch -M main
git push -u origin main
```

---

### PASO 3 — Agregar el proyecto Android (una sola vez)

Después del primer push, ejecuta localmente:

```bash
# Instalar dependencias
npm install

# Agregar plataforma Android
npx cap add android

# Sincronizar
npx cap sync android

# Subir los archivos Android generados
git add android/
git commit -m "Add Android platform"
git push
```

---

### PASO 4 — El APK se compila automáticamente

1. Ve a tu repositorio en GitHub
2. Haz clic en la pestaña **"Actions"**
3. Verás el workflow **"Build APK - WAKE UP"** ejecutándose
4. Espera ~5-8 minutos
5. Cuando termine (✅ verde), haz clic en el workflow
6. En la sección **"Artifacts"**, descarga **"WAKEUP-v6-debug"**
7. Descomprime el ZIP → tendrás el archivo `app-debug.apk`

---

### PASO 5 — Instalar en tu Android

1. Copia el `app-debug.apk` a tu celular (por USB, WhatsApp, Drive, etc.)
2. En tu Android: **Ajustes → Seguridad → Fuentes desconocidas** → Activar
3. Abre el archivo APK desde el administrador de archivos
4. Toca **"Instalar"**
5. ¡Listo! La app aparecerá como **"WAKE UP"** en tu pantalla de inicio

---

## 🔄 Actualizar la app

Cada vez que modifiques `www/index.html` y hagas push, GitHub Actions
compilará automáticamente un nuevo APK.

```bash
# Después de modificar el HTML
git add .
git commit -m "Actualización: descripción del cambio"
git push
```

---

## ✨ Características incluidas

- ⏰ Múltiples alarmas con color, repetición y encadenamiento
- 🎮 11 retos: Matemáticas, Ecuación X, Secuencia, Agitar, Escribir,
  Memoria visual, Sudoku, Anagrama, Cultura general, Trivia IA
- 🎺 5 sonidos incluida Diana Militar (Reveille)
- 🌅 Volumen gradual
- 📌 Alarmas favoritas fijadas
- ⛓ Alarmas en cadena
- 🌙 Ciclo de sueño completo con sonidos ambientales
- 📓 Diario de sueño con estado de ánimo
- 💊 Rutina matutina con recordatorios
- 📈 Tendencia de sueño 4 semanas
- 🏅 12 logros desbloqueables
- 👤 Perfil de usuario con niveles
- 📊 Estadísticas detalladas

---

## ⚠️ Nota sobre el APK debug vs release

El APK generado es un **APK de debug** — funciona perfectamente para
uso personal. Si quisieras publicarlo en la Play Store necesitarías
firmarlo con un keystore (proceso adicional).

---

## 🛠 Estructura del proyecto

```
wakeup-alarm-app/
├── www/
│   └── index.html          ← La app completa (HTML + CSS + JS)
├── android/                ← Generado por Capacitor (no editar)
├── .github/
│   └── workflows/
│       └── build-apk.yml   ← Configuración de GitHub Actions
├── capacitor.config.json   ← Configuración de Capacitor
├── package.json            ← Dependencias npm
└── README.md               ← Este archivo
```
