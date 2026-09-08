---

## 📌 Descripción de los Nodos

1. **`Telegram Trigger`**
   - **Tipo:** `n8n-nodes-base.telegramTrigger` (v1.5)
   - **Función:** Captura en tiempo real los eventos enviados al bot de Telegram, escuchando tanto mensajes de texto (`message`) como interacciones con botones inline (`callback_query`).

2. **`Es ver reporte?`**
   - **Tipo:** `n8n-nodes-base.if` (v2.2)
   - **Función:** Evalúa la propiedad `$json.callback_query.data`.
     - **Si equivale a `ver_reporte` (True):** Dirige el flujo hacia la lectura y generación del informe.
     - **De lo contrario (False):** Redirige al envío del menú principal con las opciones disponibles.

3. **`Enviar menu`**
   - **Tipo:** `n8n-nodes-base.telegram` (v1.2)
   - **Función:** Responde al usuario en el chat correspondiente enviando un saludo inicial junto a un botón interactivamente estructurado (*Inline Keyboard*) para solicitar el reporte.

4. **`Leer TUTORIAS`**
   - **Tipo:** `n8n-nodes-base.googleSheets` (v4.5)
   - **Función:** Consulta la hoja `TUTORIAS` (`Hoja 1`) en Google Sheets y extrae los registros de solicitudes.

5. **`Contar por materia`**
   - **Tipo:** `n8n-nodes-base.code` (v2)
   - **Función:** Recorre los registros obtenidos, normaliza el nombre de cada materia (asigna `'Sin materia'` en caso de valores vacíos) y calcula las frecuencias de solicitud ordenadas de forma descendente.

6. **`Generar reporte Telegram`**
   - **Tipo:** `n8n-nodes-base.code` (v2)
   - **Función:** Modela el informe final calculando la suma total y aplicando un formato compatible con HTML (negritas, cursivas, viñetas y marca de tiempo con la zona horaria `America/Bogota`).

7. **`Enviar Reporte`**
   - **Tipo:** `n8n-nodes-base.telegram` (v1.2)
   - **Función:** Envía el informe generado al chat desde el cual se presionó el botón interactivo, asegurando la interpretación del formato `HTML`.

---

CAPTURAS DE PANTALLA

1.Nodos nuevos en n8n
<img width="1673" height="537" alt="image" src="https://github.com/user-attachments/assets/e5acabef-b035-4509-89f5-6946a21763ec" />

2.Prueba de éxito en telegram
<img width="1011" height="901" alt="image" src="https://github.com/user-attachments/assets/8c5a0b02-e49f-41ab-af1e-440078085799" />

3.Evidencia Google Sheets
<img width="882" height="269" alt="image" src="https://github.com/user-attachments/assets/bb044e65-544a-464f-8920-e1e9ba3e4e2a" />





