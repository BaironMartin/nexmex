# 📋 Instrucciones para Configurar tu Catálogo de Zapatos

## 1. Preparar tu Google Sheet

Crea una hoja de cálculo en Google Sheets con la siguiente estructura en la **primera fila** (encabezados):

| Columna A | Columna B | Columna C | Columna D | Columna E | Columna F | Columna G |
|-----------|-----------|-----------|-----------|-----------|-----------|-----------|
| ID | Nombre | Categoria | Talla | Precio | Stock | Imagen |

### Ejemplo de datos:

```
ID,Nombre,Categoria,Talla,Precio,Stock,Imagen
Z001,Zapato Formal Negro,Formal,40,850.00,15,https://ejemplo.com/zapato1.jpg
Z002,Tenis Deportivos,Deportivo,42,650.00,8,https://ejemplo.com/zapato2.jpg
Z003,Botas de Cuero,Casual,39,1200.00,0,https://ejemplo.com/zapato3.jpg
```

**Notas importantes:**
- **ID**: Identificador único del producto
- **Nombre**: Nombre del zapato
- **Categoria**: Ej: Formal, Deportivo, Casual, Sandalia, etc.
- **Talla**: Número de talla (ej: 38, 39, 40, 41, 42)
- **Precio**: Precio numérico (sin signo $)
- **Stock**: Cantidad disponible (0 = agotado)
- **Imagen**: URL de la imagen (puede ser de Google Drive público, Imgur, o cualquier hosting)

## 2. Publicar como CSV

1. En Google Sheets, ve a **Archivo** → **Compartir** → **Publicar en la web**
2. En el cuadro de diálogo:
   - Selecciona "Todo el documento" en lugar de "Hoja 1"
   - Cambia "Página web" por **"Valores separados por comas (.csv)"**
3. Haz clic en **Publicar**
4. Copia el enlace que te proporcionan

## 3. Configurar el archivo index.html

Abre el archivo `index.html` y busca estas dos líneas al inicio del JavaScript:

```javascript
const SHEET_CSV_URL = 'TU_ENLACE_CSV_AQUI'; 
const WHATSAPP_NUMBER = '5215555555555'; 
```

### Reemplaza:

1. **`TU_ENLACE_CSV_AQUI`**: Pega el enlace CSV que copiaste de Google Sheets
2. **`5215555555555`**: Tu número de WhatsApp con código de país
   - Ejemplo México: `5215512345678`
   - Ejemplo España: `34612345678`
   - Ejemplo Argentina: `5491112345678`
   - **Importante**: Solo números, sin espacios ni símbolos +

## 4. Probar la aplicación

Simplemente abre el archivo `index.html` en tu navegador:

```bash
# Opción 1: Doble clic en el archivo
# Opción 2: Desde terminal
open index.html  # Mac
start index.html  # Windows
xdg-open index.html  # Linux
```

## 5. Características incluidas

✅ **Catálogo visual** con tarjetas de productos  
✅ **Filtros** por categoría y talla  
✅ **Control de stock** en tiempo real  
✅ **Carrito de compras** funcional  
✅ **Botón flotante** del carrito  
✅ **Envío a WhatsApp** con el detalle del pedido  
✅ **Diseño responsive** (funciona en móviles)  
✅ **Sin backend** necesario  

## 6. Personalización

### Cambiar colores:
En la sección `<style>` al inicio, modifica las variables CSS:

```css
:root {
    --primary: #2c3e50;      /* Color principal */
    --accent: #e74c3c;       /* Color de acento */
    --whatsapp: #25D366;     /* Color del botón WhatsApp */
}
```

### Cambiar el nombre de la tienda:
Busca en el HTML:
```html
<h1>👟 Zapatería Estilo</h1>
```
Y cámbialo por tu nombre.

## 7. Actualizar productos

Solo necesitas:
1. Editar tu Google Sheet
2. Los cambios se reflejarán automáticamente al recargar la página (F5)

---

## ⚠️ Solución de problemas

**Error: "Error cargando productos"**
- Verifica que el enlace CSV sea correcto
- Asegúrate de haber publicado la hoja en la web
- Comprueba que los encabezados coincidan exactamente

**El carrito no envía a WhatsApp**
- Verifica que el número tenga el código de país correcto
- Asegúrate de tener productos en el carrito

**Las imágenes no se ven**
- Usa URLs públicas de imágenes
- Puedes subir imágenes a imgur.com o usar Google Photos público
