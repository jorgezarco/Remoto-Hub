# SoportePro — Plataforma de Soporte Remoto
## IDM Azatlán FC · Instrucciones de Instalación y Uso

---

## 📁 Archivos

| Archivo | Descripción |
|---------|-------------|
| `soporte-agente.html` | Panel del técnico de soporte (tú) |
| `soporte-cliente.html` | Página del usuario que recibe soporte |

---

## 🚀 Instalación en InfinityFree

1. Sube ambos archivos a tu hosting via File Manager o FTP
2. Colócalos en la raíz o en una carpeta: `/soporte/`
3. URLs resultantes:
   - Agente: `http://proyectojfz.infinityfreeapp.com/soporte/soporte-agente.html`
   - Cliente: `http://proyectojfz.infinityfreeapp.com/soporte/soporte-cliente.html`

---

## ⚙️ Flujo de Uso

### Como Agente (tú):
1. Abre `soporte-agente.html` en tu navegador
2. Escribe tu nombre cuando lo pida
3. Crea un nuevo ticket con el botón **+ Nuevo**
4. Haz clic en el ticket → se genera el **link de sesión**
5. Copia el link y envíaselo al cliente (WhatsApp, email, etc.)
6. Espera a que el cliente abra el link y comparta su pantalla
7. La pantalla aparecerá automáticamente en el panel de la izquierda

### Como Cliente:
1. Recibe el link del agente y lo abre en su navegador
2. Llena su nombre y departamento
3. Hace clic en "Iniciar Sesión y Compartir Pantalla"
4. El navegador le pedirá permiso para compartir pantalla
5. El agente ve su pantalla en tiempo real

---

## 💡 Funcionalidades

### Panel Agente:
- ✅ Tickets de soporte con prioridad (Alta/Media/Baja)
- ✅ Vista de pantalla remota en tiempo real
- ✅ Chat bidireccional con el cliente
- ✅ Historial de sesiones cerradas (localStorage)
- ✅ Info del cliente (OS, navegador, resolución)
- ✅ Notas de sesión por ticket
- ✅ Timer de duración de sesión
- ✅ Copiar link de sesión con un clic

### Panel Cliente:
- ✅ Formulario de registro con departamento
- ✅ Compartir pantalla (screen share WebRTC)
- ✅ Vista previa de lo que ve el agente
- ✅ Chat con el agente
- ✅ Botón de pausa/reanudar pantalla
- ✅ Botón de finalizar sesión

---

## ⚠️ Limitaciones Importantes

### ¿Por qué usar HTTPS?
WebRTC y getDisplayMedia **requieren HTTPS** en producción.
InfinityFree NO provee HTTPS gratuito en subdominios propios.

**Soluciones:**
1. **Usar en la misma red local** (funciona en HTTP)
2. **Ngrok** para exponer local con HTTPS gratis
3. **GitHub Pages** — gratis con HTTPS: `usuario.github.io/soporte`
4. **Cloudflare Pages** — gratis con HTTPS

### Señalización
La comunicación de señalización usa `localStorage`.
Esto significa que **agente y cliente deben estar en el mismo navegador/dispositivo** o usar una red compartida.

**Para producción real con usuarios en PCs distintas:**
Necesitarías reemplazar localStorage por un backend de señalización:
- Firebase Realtime Database (gratis hasta cierto límite)
- Un endpoint PHP simple en tu hosting

---

## 🔧 Personalización

### Cambiar nombre de empresa:
En `soporte-agente.html` busca:
```
<div class="topbar-badge">🖥 IDM Azatlán FC</div>
```

### Cambiar departamentos en cliente:
En `soporte-cliente.html` busca las `<option>` dentro de `clientDept`.

### Colores:
Edita las variables CSS `:root` en ambos archivos.

---

## 🗺️ Roadmap — Próximas Fases

| Fase | Feature | Req. |
|------|---------|------|
| 2 | Señalización vía Firebase | HTTPS + Firebase gratis |
| 3 | Control remoto real (mouse/teclado) | Extensión de Chrome |
| 4 | Grabación de sesión | HTTPS + servidor |
| 5 | Dashboard de métricas | Google Sheets backend |

---

**IDM Azatlán FC · Mazatlán, Sinaloa, México**
