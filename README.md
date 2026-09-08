📌 Descripción de los Nodos

1. **`Cada hora` (Schedule Trigger)**
   - **Tipo:** `n8n-nodes-base.scheduleTrigger`
   - **Función:** Desencadena la ejecución del flujo automáticamente con un intervalo de 1 hora.

2. **`Leer TUTORIAS` (Google Sheets)**
   - **Tipo:** `n8n-nodes-base.googleSheets`
   - **Función:** Obtiene las filas guardadas en la hoja **TUTORIAS** (`Hoja 1`).
   - **Credencial requerida:** OAuth2 para Google Sheets (`googleSheetsOAuth2Api`).

3. **`Contar por materia` (Code)**
   - **Tipo:** `n8n-nodes-base.code`
   - **Función:** Recorre los registros, normaliza el nombre de la materia (asigna `'Sin materia'` si viene vacío) y realiza la agrupación y conteo descendente por cantidad.

4. **`Generar reporte Telegram` (Code)**
   - **Tipo:** `n8n-nodes-base.code`
   - **Función:** Toma los datos contados y construye una plantilla de texto formateada con etiquetas HTML (negritas, cursivas, viñetas) e incluye la fecha y hora de generación (Zona Horaria: `America/Bogota`).

5. **`Send a text message` (Telegram)**
   - **Tipo:** `n8n-nodes-base.telegram`
   - **Función:** Envía el mensaje generado al Chat ID configurado utilizando la API del bot de Telegram en modo `HTML`.

CAPTURAS DE PANTALLA

1.Nodos nuevos en n8n
<img width="1482" height="316" alt="image" src="https://github.com/user-attachments/assets/9288e16d-38d9-435e-907b-8e35b3421909" />

2.Prueba de éxito en telegram
<img width="1014" height="899" alt="image" src="https://github.com/user-attachments/assets/f88940f6-b587-4b3d-8bbd-249983c7eab5" />

3.Evidencia Google Sheets
<img width="882" height="269" alt="image" src="https://github.com/user-attachments/assets/bb044e65-544a-464f-8920-e1e9ba3e4e2a" />





