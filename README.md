# 📦 Sistema Punto de Venta (POS)

Sistema de punto de venta con dos aplicaciones conectadas en tiempo real mediante Firebase.

## 🖥️ Apps

| App | Archivo | Uso | Dispositivo |
|-----|---------|-----|-------------|
| **Admin (Madre)** | `pos-admin.html` | Configuración completa + ventas | Laptop/PC |
| **Terminal (Hija)** | `pos-terminal.html` | Solo ventas y tickets | Celular/Tablet |

## 🔧 Configuración de Firebase

### Paso 1: Crear proyecto en Firebase
1. Ve a [https://console.firebase.google.com](https://console.firebase.google.com)
2. Clic en **"Agregar proyecto"**
3. Ponle nombre (ej: "mi-punto-de-venta")
4. Desactiva Google Analytics si no lo necesitas
5. Clic en **"Crear proyecto"**

### Paso 2: Crear app web
1. En tu proyecto, clic en el ícono **</>** (Web)
2. Nombre: "POS" y clic en **"Registrar app"**
3. Copia el bloque `firebaseConfig` que te aparece:
```js
const firebaseConfig = {
  apiKey: "AIza...",
  authDomain: "tu-proyecto.firebaseapp.com",
  projectId: "tu-proyecto",
  storageBucket: "tu-proyecto.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc123"
};
```

### Paso 3: Activar Firestore
1. En el menú izquierdo, ve a **"Firestore Database"**
2. Clic en **"Crear base de datos"**
3. Selecciona **"Iniciar en modo de prueba"** (para desarrollo)
4. Elige tu ubicación más cercana
5. Clic en **"Habilitar"**

### Paso 4: Pegar tu config en las apps
1. Abre `pos-admin.html` y `pos-terminal.html`
2. Busca el bloque `const firebaseConfig = { ... }`
3. Reemplázalo con TU configuración de Firebase

### Paso 5: Listo
- Abre `pos-admin.html` en tu laptop
- Abre `pos-terminal.html` en tu celular
- ¡Todo se sincroniza en tiempo real!

## 🚀 Hosting (opcional)
Para acceder desde cualquier dispositivo:
```bash
npm install -g firebase-tools
firebase login
firebase init hosting
firebase deploy
```

## 📂 Git
```bash
git init
git add .
git commit -m "Sistema POS inicial"
git remote add origin TU_REPO_URL
git push -u origin main
```

## ⚠️ Seguridad
El modo de prueba de Firestore expira en 30 días. Para producción, configura reglas de seguridad en la consola de Firebase.
