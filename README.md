# Informe y Evaluación de Sesiones Académicas

Este proyecto automatiza dos procesos basados en encuestas de sesiones académicas descargadas de Moodle en formato `.csv`:

1. **Generación del informe para el presentador:** Utilizando el notebook `genera_informe_encuestas.ipynb`, se genera un informe para el presentador de la sesión con los resultados de las encuestas. El informe incluye la evaluación del tema, la presentación, y la sesión en general.

2. **Evaluación y envío de informes personalizados para los alumnos:** Con el notebook `evalua_encuestas.ipynb`, se evalúan las respuestas de los alumnos basadas en criterios predefinidos, se generan informes individuales en formato `.docx`, se convierten a `.pdf`, y se envían automáticamente por correo electrónico a cada alumno con su evaluación personalizada.


## Funcionalidad

1. **Lectura de Encuestas**: El sistema carga un archivo CSV con las respuestas de los participantes y las procesa en un DataFrame.
   
2. **Evaluación de Respuestas**: Las respuestas se evalúan usando GPT-4 según criterios predefinidos. Se asigna una nota y se generan comentarios sobre cada respuesta.

3. **Generación de Informes**: Se crea un informe en formato `.docx` para cada participante usando plantillas. Luego, los archivos se convierten a `.pdf` usando LibreOffice.

4. **Envío de Correos**: Los informes se envían a los participantes con un correo personalizado, que incluye instrucciones para solicitar una revisión de la nota si no están de acuerdo.

## Estructura de los archivos

- **/workspace/reports/:** Aquí se almacenan los informes generados en formato .docx y .pdf.
  
- **/workspace/data/:** Contiene los archivos de las encuestas en formato .csv.
  
- **/workspace/template/:** Contiene las plantillas en formato .docx que se usan para generar los informes.
  
- **evalua_encuestas.ipynb:** Un notebook que automatiza la evaluación de encuestas académicas, generando informes personalizados y enviándolos por correo electrónico.
  
- **genera_informe_encuestas.ipynb:** Un notebook que genera y envía informes personalizados al presentador de la sesión con los resultados de las evaluaciones sobre el tema, el presentador y la sesión en general. 

- README.md: Este archivo de documentación.

## Consideraciones

1. Configura las variables de entorno en un archivo .env:
   
    SMTP_USER=tu_correo@gmail.com

    SMTP_PASSWORD=tu_contraseña

2. Asegúrate de tener LibreOffice instalado para convertir los archivos .docx a .pdf.


