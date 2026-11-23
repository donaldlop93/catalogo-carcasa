# Catálogo Digital CARCASA Jinotega

Aplicación web responsiva (*Mobile-First*) y herramienta comercial interactiva desarrollada para **CARCASA Jinotega** (Nicaragua), especializada en la exhibición y cotización de maquinaria agrícola, equipos industriales, motores eléctricos y diésel, generadores, motobombas, herramientas y repuestos.

---

## 🚀 Características Principales

### Vista Pública (Clientes)
- **Portada Compacta:** Acceso inmediato al catálogo de productos sin desplazamientos largos.
- **Búsqueda en Tiempo Real:** Filtro instantáneo por nombre de equipo, marca, modelo, código interno y categoría.
- **Filtrado y Ordenamiento:** Píldoras horizontales de categorías, selectores dinámicos y ordenación alfabética o cronológica.
- **Precios y Monedas:** Soporte para Córdobas (`C$`) y Dólares (`$`). El precio se renderiza en la esquina inferior derecha de la fotografía. Si el producto no tiene precio, la etiqueta se oculta limpiamente.
- **URL Única y Compartible:** Cada equipo genera un enlace con slug amigable (ejemplo: `?producto=motobomba-diesel`).
- **Consulta Directa por WhatsApp:** Botón que genera un mensaje prellenado con los datos técnicos del equipo para atención inmediata con asesores.

### Modo Administrador (Uso Interno)
- **CRUD Completo:** Creación, edición, activación/desactivación y eliminación de equipos y categorías.
- **Generador Automático de Catálogo PDF Editorial (Estilo Canva / Revista):**
  - Generación automática en formato A4 de alta definición (150 DPI).
  - Maquetación de **3 productos por página** con especificaciones técnicas alineadas con líneas divisorias, marca en rojo oscuro, fotografía nítida y precios de referencia.
  - Listón superior rojo tipo marcador con número de página y banner azul marino con el nombre de la categoría y estrellas.
  - Filtro por categoría (catálogo general o por línea como Plantas Eléctricas, Bombas, etc.) y por marca.
  - **Generación automática de enlace web para verlo en línea** (con subida a Supabase Storage para enlace público permanente, o enlace Blob para visualización instantánea).
  - Apertura automática en nueva pestaña y botón para compartir por WhatsApp o descargar directamente el archivo PDF.
- **Generador de Ficha Técnica Individual HD (.PNG):** Renderizado automático mediante HTML5 Canvas en alta resolución (1080px de ancho) con el logotipo oficial de CARCASA Jinotega, fotografía, características técnicas, precio y datos de contacto listos para despacho comercial.
- **Compartir Rápido:**
  - Descarga directa de la ficha en formato `.PNG`.
  - Copiar imagen al portapapeles (`Ctrl+V`) para pegar directamente en WhatsApp Web o Messenger.
  - Envío formateado por WhatsApp Click-to-Chat.
  - Compatibilidad con Web Share API para compartir fichas con imagen desde dispositivos móviles.
- **Gestión de Configuración:** Modificación de números de WhatsApp, teléfono visible, correo, horarios, dirección física y textos institucionales.

---

## 🛠️ Stack Tecnológico

- **Frontend:** HTML5 semántico, Tailwind CSS (utilidades responsivas), JavaScript ES6+ modular, Lucide Icons, Google Font *Inter*.
- **Generación Gráfica:** HTML5 Canvas API en cliente.
- **Backend y Base de Datos (Producción):** Supabase (PostgreSQL, Supabase Auth, Supabase Storage).
- **Despliegue Recomendado:** Vercel / GitHub Pages.

---

## 📁 Estructura del Proyecto

```
CatalogoCarcasa/
├── assets/
│   └── images/
│       └── logo.jpg              # Logotipo oficial de CARCASA Jinotega
├── supabase/
│   └── schema.sql                # Script SQL para tablas, RLS, Storage y semillas
├── index.html                    # Aplicación web completa lista para producción
├── README.md                     # Documentación general
└── ficha-generador-electrico.png # Muestra de ficha técnica generada
```

---

## ⚙️ Configuración y Uso Local

1. Abre `index.html` directamente en tu navegador o utilizando una extensión de servidor local como *Live Server* en VS Code.
2. La aplicación incluye un catálogo predeterminado y almacena cambios en `localStorage` de forma inmediata.
3. Para conectar tu base de datos Supabase en la nube, ingresa al **Panel Admin** -> Pestaña **Conexión Supabase** e introduce tu `SUPABASE_URL` y `SUPABASE_ANON_KEY`.
