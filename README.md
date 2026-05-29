# 📊 Dashboard de Facturación – Calidda

Dashboard interactivo para el análisis de facturación y rendimiento por asesor.  
Diseñado para equipos comerciales que necesitan visualizar KPIs de ventas, tiempo de facturación y productividad individual, con especial énfasis en **días hábiles** y **cierre de facturación mensual**.

![Vista previa del dashboard](https://via.placeholder.com/800x400?text=Dashboard+Preview)

## 🚀 Características principales

- **Carga dinámica de Excel** – Selecciona cualquier archivo `.xlsx` o `.xls` y el dashboard se construye automáticamente.
- **KPIs globales**:
  - Pedidos únicos de venta
  - Facturas únicas emitidas
  - Total facturado (formato compacto: `S/ 2.5K`, `S/ 1.2M`)
  - Porcentaje de facturación a tiempo (≤2 días hábiles, considerando cierre mensual)
- **Análisis por asesor** (bloques colapsables):
  - Wendy de la Cruz, JeanPierre Barreto, Gregory Vilchez, Gianella Quispe, Mayra Salazar, etc.
  - Cada asesor muestra sus propios KPI, top productos y evolución mensual.
- **Reglas de negocio personalizadas**:
  - **Cálculo de días hábiles** (lunes a viernes).
  - **Ajuste por cierre mensual**: si un pedido se crea entre el día 26 y fin de mes, el plazo comienza a contar desde el **primer día del mes siguiente**.
  - **Semáforo de cumplimiento** (verde ≥80%, amarillo 50-80%, rojo <50%).
- **Filtros globales** (rango de fechas, categoría de cliente, tipo de documento).
- **Diseño profesional**:
  - Tarjetas con gradientes y bordes de acento según rendimiento.
  - Gráficos interactivos (Chart.js).
  - Total facturado en formato compacto con detalle completo debajo.
  - Iconos personalizados por asesor.
- **Totalmente actualizable** – Solo vuelve a cargar el archivo Excel o conéctalo a una fuente de datos en la nube (Google Sheets, API).

## 📁 Estructura de datos requerida

El archivo Excel debe contener las siguientes columnas (el dashboard las detecta automáticamente, aunque los nombres pueden tener ligeras variaciones):

| Campo | Descripción | Ejemplo |
|-------|-------------|---------|
| `Autor` | Nombre de usuario del asesor | `C_JBARRETO` |
| `Documento de ventas` | Número de pedido/orden | `1007890717` |
| `Numero Recibo/Numero fac electronica` | Número de factura electrónica | `03-B002-05770115` |
| `Total con IGV` | Monto total facturado | `594.22` |
| `Creado el` | Fecha de creación del pedido | `2026-04-24 00:00:00` |
| `Fecha de Factura` | Fecha de emisión de la factura | `2026-04-24 00:00:00` |
| `Categoria Cuenta contrato` | Tipo de cliente (COMS, RESM, etc.) | `COMS` |
| `Clase doc.ventas` | Tipo de documento | `ZP15` |
| `Descripcion Material` | Descripción del producto/servicio | `Mantenimiento Acometida G6` |

> **Nota**: El dashboard es tolerante a mayúsculas/minúsculas, tildes y espacios. Si alguna columna no se detecta, revisa la consola del navegador.

## 🧩 ¿Cómo usar el dashboard?

1. **Descarga o clona el repositorio**.
2. Abre el archivo `dashboard.html` en cualquier navegador moderno (Chrome, Edge, Firefox).
3. Haz clic en **“Cargar archivo Excel”** y selecciona tu `Base de Facturacion.xlsx`.
4. El dashboard se generará automáticamente. Usa los filtros superiores para acotar fechas, categorías o tipo de documento.
5. Cada asesor tiene un bloque colapsable con sus propios gráficos y KPIs.

> 🔁 **Para actualizar**: Vuelve a cargar un archivo Excel más reciente. Si deseas integración en tiempo real, puedes modificar el script para leer desde una URL pública (Google Sheets) o una API.

## 🛠️ Personalización

Puedes adaptar el dashboard fácilmente:

- **Agregar o cambiar nombres de asesores** – Modifica el objeto `nombreAsesor` y `asesorStyle` en el código.
- **Cambiar días de cierre** – En la función `isInClosingPeriod`, ajusta `>= 26` a la fecha que necesites.
- **Modificar plazo de facturación** – Cambia el número `2` en `addBusinessDays(startDate, 2)` por los días deseados.
- **Colores e iconos** – Edita las clases CSS o los estilos dentro de `asesorStyle`.

## 📦 Tecnologías utilizadas

- HTML5 / CSS3 / JavaScript (ES6)
- [Bootstrap 5](https://getbootstrap.com/) – layout y acordeón
- [Chart.js](https://www.chartjs.org/) – gráficos interactivos
- [SheetJS (XLSX)](https://sheetjs.com/) – lectura de archivos Excel
- [Font Awesome 6](https://fontawesome.com/) – iconografía
- Google Fonts (Inter) – tipografía moderna

## 📈 Posibles mejoras futuras

- Conexión directa a Google Sheets mediante API.
- Exportación de gráficos a PDF o imagen.
- Modo oscuro.
- Comparativa entre asesores (ranking).
- Alertas automáticas cuando el cumplimiento baje de cierto umbral.

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si deseas añadir nuevas funcionalidades o corregir errores:

1. Haz un fork del proyecto.
2. Crea una rama con tu mejora (`git checkout -b feature/nueva-funcionalidad`).
3. Haz commit y push.
4. Abre un Pull Request.

## 📄 Licencia

Este proyecto está bajo la licencia MIT. Puedes usarlo, modificarlo y distribuirlo libremente.

## 👥 Autores y reconocimientos

- **Desarrollador**: Gregory Vilchez
- **Coordinador de negocio**: Antonio Pomalaza
- **Basado en requerimientos del área de facturación de Calidda**.

---

## 📬 Contacto

Si tienes dudas o sugerencias, abre un *issue* en este repositorio o contacta al equipo de desarrollo.

---

**¡Optimiza tu control de facturación con datos reales y toma mejores decisiones!**  
