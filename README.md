# 🍏 LimpiarMac

<p align="center">
  <img src="AppIcon.PNG" alt="LimpiarMac Icon" width="140" height="140">
</p>

<p align="center">
  <b>Aplicación ligera y nativa para macOS diseñada para realizar mantenimiento preventivo, vaciado de archivos temporales y depuración de caché con un solo clic.</b>
</p>

<p align="center">
  <a href="https://trakerdev.github.io"><img src="https://img.shields.io/badge/Desarrollado_por-trakerdev.github.io-blue?style=flat-square" alt="Portfolio"></a>
  <a href="https://www.apple.com/macos/"><img src="https://img.shields.io/badge/macOS-10.13+-black?style=flat-square&logo=apple" alt="macOS"></a>
  <img src="https://img.shields.io/badge/Licencia-MIT-green?style=flat-square" alt="Licencia">
</p>

---

## 📌 ¿Qué es LimpiarMac?

**LimpiarMac** es una utilidad empaquetada como aplicación nativa (`.app`) que ejecuta una rutina segura en segundo plano para liberar espacio en disco y mantener la agilidad del sistema.

### Características principales
* **Splash interactivo:** Muestra una ventana de confirmación detallando qué se limpiará antes de tocar cualquier archivo, con acceso directo al sitio del desarrollador y botón de cancelación inmediata.
* **Proceso silencioso y en segundo plano:** No abre ventanas molestas de Terminal ni consume recursos innecesarios.
* **Retroalimentación completa:** Al finalizar, reproduce un sonido nativo del sistema (`Glass`) y despliega una notificación de macOS indicando que el proceso terminó con éxito.

---

## 🧹 ¿Qué elementos limpia?

| Módulo | Elementos Afectados | Detalle de la limpieza |
| :--- | :--- | :--- |
| **Papelera** | Archivos eliminados | Vacía `~/.Trash` de forma segura. |
| **Caché de Usuario** | Archivos temporales de aplicaciones | Limpia `~/Library/Caches` sin alterar datos de usuario. |
| **Logs del Sistema** | Registros antiguos de aplicaciones | Limpia `~/Library/Logs`. |
| **Temporales Privados** | Archivos temporales del sistema | Purga archivos inactivos de más de 3 días en `$TMPDIR`. |
| **Navegadores Web** | Chrome, Safari, Firefox y Brave | Elimina únicamente la caché web local (no cierra sesiones ni borra contraseñas). |

---

## 📥 Descarga e Instalación

### 1. Descargar la aplicación
Descarga el archivo empaquetado directamente desde este repositorio:
* 👉 **[Descargar LimpiarMac.tar](LimpiarMac.tar)**

### 2. Descomprimir y ubicar
1. Haz doble clic sobre **`LimpiarMac.tar`** para extraer la aplicación **`LimpiarMac.app`**.
2. Arrastra **`LimpiarMac.app`** a tu carpeta de **`Aplicaciones`** (o déjala en tu **`Escritorio`**).

---

## ⚙️ Permisos iniciales en macOS (Solo la primera vez)

Dado que la aplicación se distribuye como un paquete sin firma de desarrollador de Apple, macOS Gatekeeper puede mostrar un aviso de seguridad o impedir su ejecución la primera vez.

Para habilitarla y dejarla lista para usar siempre con doble clic:

1. Abre la aplicación **Terminal** en tu Mac.
2. Copia y ejecuta este comando:
   ```bash
   chmod +x /Applications/LimpiarMac.app/Contents/MacOS/LimpiarMac
   xattr -cr /Applications/LimpiarMac.app