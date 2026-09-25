# Sp_tx
# Traductor de Voz Multilenguaje 🎤🌍

## Descripción
Aplicación web desarrollada con Streamlit que permite la traducción de voz en tiempo real entre múltiples idiomas. Integra reconocimiento de voz, traducción de texto y síntesis de voz, ofreciendo una experiencia completa de traducción con soporte para diferentes acentos.

## Características Principales
- 🎤 Reconocimiento de voz en tiempo real
- 🔄 Traducción entre múltiples idiomas
- 🗣️ Síntesis de voz con diferentes acentos
- 📝 Visualización de texto traducido
- 🌐 Interfaz web intuitiva
- 🎯 Soporte para 6 idiomas principales

## Requisitos Previos
```
- Python 3.7+
- Streamlit
- Bokeh
- gTTS (Google Text-to-Speech)
- googletrans
- Pillow
- streamlit-bokeh-events
```

## Instalación
1. Clona el repositorio
2. Instala las dependencias:
```bash
pip install streamlit bokeh gTTS googletrans==3.1.0a0 Pillow streamlit-bokeh-events
```
3. Asegúrate de tener la imagen 'OIG7.jpg' en el directorio del proyecto

## Idiomas Soportados
- 🇺🇸 Inglés
- 🇪🇸 Español
- 🇧🇩 Bengali
- 🇰🇷 Coreano
- 🇨🇳 Mandarín
- 🇯🇵 Japonés

## Acentos Disponibles
- Defecto (com)
- Español (com.mx)
- Reino Unido (co.uk)
- Estados Unidos (com)
- Canadá (ca)
- Australia (com.au)
- Irlanda (ie)
- Sudáfrica (co.za)

## Uso
1. Inicia la aplicación:
```bash
streamlit run app.py
```

2. Flujo de trabajo:
   - Presiona el botón "Escuchar 🎤"
   - Habla el texto que deseas traducir
   - Selecciona el idioma de entrada
   - Selecciona el idioma de salida
   - Elige el acento deseado
   - Presiona "convertir" para obtener la traducción

## Estructura del Código

### Componentes Principales

1. **Interfaz de Usuario**
```python
st.title("TRADUCTOR.")
st.subheader("Escucho lo que quieres traducir.")
```

2. **Reconocimiento de Voz**
```python
stt_button = Button(label=" Escuchar  🎤", width=300, height=50)
# Integración con WebSpeechRecognition API
```

3. **Sistema de Traducción**
```python
translator = Translator()
text_to_speech(input_language, output_language, text, tld)
```

### Funciones Clave

1. **Traducción y Síntesis de Voz**
```python
def text_to_speech(input_language, output_language, text, tld):
    translation = translator.translate(text, src=input_language, dest=output_language)
    trans_text = translation.text
    tts = gTTS(trans_text, lang=output_language, tld=tld, slow=False)
```

2. **Gestión de Archivos Temporales**
```python
def remove_files(n):
    # Limpia archivos MP3 más antiguos que n días
```

## Gestión de Archivos
- Creación automática de directorio 'temp'
- Almacenamiento temporal de archivos de audio
- Limpieza automática de archivos después de 7 días

## Personalización
1. Idiomas:
   - Añadir nuevos idiomas en los selectbox
   - Configurar códigos de idioma correspondientes

2. Acentos:
   - Modificar lista de acentos disponibles
   - Actualizar TLD según necesidades

## Limitaciones
- Requiere conexión a internet
- Necesita permisos de micrófono
- Dependiente de servicios de Google
- Archivos de audio temporales

## Troubleshooting
1. Problemas de micrófono:
   - Verificar permisos del navegador
   - Comprobar dispositivo de entrada

2. Problemas de traducción:
   - Verificar conexión a internet
   - Comprobar códigos de idioma

## Desarrollo Futuro
- Añadir más idiomas
- Implementar traducción en tiempo real
- Mejorar manejo de errores
- Añadir histórico de traducciones
- Implementar exportación de traducciones

## Seguridad
- No almacena datos permanentemente
- Limpieza automática de archivos temporales
- Sin envío de datos a terceros (excepto servicios de Google)

## Contribuciones
Para contribuir:
1. Fork del repositorio
2. Crear rama de características
3. Commit de cambios
4. Crear Pull Request

## Licencia
[Especificar tipo de licencia]

## Créditos
- Desarrollado con Streamlit
- Traducción: Google Translate
- Síntesis de voz: gTTS
- Reconocimiento de voz: Web Speech API
