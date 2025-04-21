# bancocontinetal palette ui/ux

*1. Paleta de Colores Inspirada en Banco Continental*

Podríamos definir los siguientes colores clave (los códigos hexadecimales son una aproximación basada en su identidad visual general, podrían variar ligeramente en el sitio real):

- *Primario (Azul Corporativo):* #0033A0 - Un azul fuerte y confiable. Ideal para botones principales, encabezados importantes, iconos clave y elementos de marca.
    - Tailwind (custom): primary: '#0033A0'
- *Acento (Verde Lima):* #C4D600 - Un verde vibrante que aporta modernidad y se usa para llamadas a la acción secundarias, highlights o elementos que necesitan destacar sin ser la acción principal.
    - Tailwind (custom): accent: '#C4D600'
- *Fondo Principal (Body):* #FFFFFF (Blanco) - Proporciona un lienzo limpio y maximiza la legibilidad.
    - Tailwind: bg-white
- *Fondo Sutil/Alternativo:* #F8F9FA (Gris muy claro) - Útil para diferenciar secciones, fondos de tarjetas o contenedores sin crear demasiado contraste.
    - Tailwind: bg-gray-100
- *Texto Principal:* #343A40 (Gris Oscuro) - Excelente para párrafos y texto general. Más suave a la vista que el negro puro.
    - Tailwind: text-gray-800
- *Texto Secundario:* #6C757D (Gris Medio) - Para textos de apoyo, etiquetas, metadatos o información menos crítica.
    - Tailwind: text-gray-600
- *Bordes y Divisores:* #DEE2E6 (Gris Claro) - Para separar elementos sutilmente.
    - Tailwind: border-gray-200

*2. Recomendaciones de Uso (UI/UX con Tailwind)*

- **Fondos (Backgrounds - bg):**
    - *Body:* Usa bg-white como base general.
    - *Secciones:* Alterna entre bg-white y bg-gray-100 para crear separación visual suave entre diferentes partes de la página.
    - *Cards/Contenedores:* bg-white border border-gray-200 rounded-lg shadow-sm (o shadow-md para más énfasis).
- **Textos (text):**
    - *Párrafos y Cuerpo:* text-gray-800. Considera usar una fuente sans-serif limpia y legible (ej. Inter, Lato, Roboto).
    - *Títulos Principales (h1, h2):* text-blue-700 (usando tu color primario customizado) o text-gray-900 (casi negro) para un look más sobrio.
    - *Subtítulos y Texto de Apoyo:* text-gray-600.
    - *Texto sobre fondo azul:* text-white. Asegúrate de que el contraste sea suficiente.
    - *Texto sobre fondo verde:* text-gray-900 o text-black. El blanco podría no tener suficiente contraste con el verde lima. ¡Verifica siempre la accesibilidad!
- **Botones (button, a con estilos):**
    - *Botón Primario:* bg-primary text-white font-semibold py-2 px-4 rounded-md hover:bg-opacity-90 transition-opacity duration-200 (Ajusta bg-primary a tu azul).
    - *Botón Secundario (Outline):* border border-primary text-primary font-semibold py-2 px-4 rounded-md hover:bg-primary hover:text-white transition-colors duration-200.
    - *Botón de Acento:* bg-accent text-gray-900 font-semibold py-2 px-4 rounded-md hover:bg-opacity-90 transition-opacity duration-200 (Ajusta bg-accent a tu verde).
- *Efectos Hover:*
    - *Enlaces:* Cambia el color al primario (hover:text-primary) o al de acento (hover:text-accent) y/o añade un subrayado (hover:underline).
    - *Botones:* Ligeros cambios de opacidad (hover:bg-opacity-90), oscurecimiento/aclarado del fondo (ej. hover:bg-blue-800 si primary es blue-700), o inversión de colores para los outline.
    - *Cards/Elementos interactivos:* Aumenta ligeramente la sombra (hover:shadow-lg) o aplica un borde sutil del color primario (hover:border-primary).
- *Tipografía:* Elige una fuente sans-serif moderna y legible. Open Sans, Lato, Montserrat, Inter son buenas opciones que se suelen usar en webs corporativas/financieras. Define tamaños consistentes para h1, h2, h3, p, etc.
- *Espaciado:* Usa el sistema de espaciado de Tailwind (p-, m-, space-y-, gap-) generosamente para crear un diseño aireado y organizado. El "whitespace" es crucial para un look limpio.

*3. Configuración de Tailwind (tailwind.config.js)*

Para usar los colores personalizados fácilmente:

*JavaScript*

jsx
// tailwind.config.js
const colors = require('tailwindcss/colors')

module.exports = {
  content: [
    './pages/**/*.{js,ts,jsx,tsx}',
    './components/**/*.{js,ts,jsx,tsx}',
  ],
  theme: {
    extend: {
      colors: {
        primary: '#0033A0', // Azul Banco Continental
        accent: '#C4D600',  // Verde Lima Banco Continental
        // Puedes añadir los grises aquí también si prefieres nombres específicos
        'text-primary': '#343A40',
        'text-secondary': '#6C757D',
        'bg-subtle': '#F8F9FA',
        'border-light': '#DEE2E6',
      },
      // Puedes extender otras cosas como fuentes aquí
      // fontFamily: {
      //   sans: ['Inter', 'sans-serif'],
      // },
    },
  },
  plugins: [],
}


Ahora podrías usar clases como bg-primary, text-accent, border-border-light, etc.

*4. Prompt Reutilizable para Futuras Peticiones*

Aquí tienes un prompt que puedes usar para pedirme que aplique este estilo:

*Fragmento de código* 


Por favor, utiliza el "Estilo Banco Continental" que definimos para diseñar/crear [Describe aquí el componente, sección o página que necesitas. Por ejemplo: "un formulario de contacto", "la cabecera de la página", "una tarjeta de producto"].

*Recordatorio del Estilo Banco Continental:*
* *Primario:* Azul #0033A0 (botones principales, títulos clave). Clase: primary.
* *Acento:* Verde Lima #C4D600 (llamadas a la acción secundarias, highlights). Clase: accent.
* *Texto Principal:* Gris Oscuro #343A40. Clase: text-primary o text-gray-800.
* *Texto Secundario:* Gris Medio #6C757D. Clase: text-secondary o text-gray-600.
* *Fondos:* Blanco #FFFFFF y Gris Claro #F8F9FA. Clases: bg-white, bg-gray-100.
* *Botones:* Primario (fondo azul, texto blanco), Secundario (borde azul, texto azul), Acento (fondo verde, texto oscuro).
* *Hover:* Sutiles cambios de opacidad/color en botones, cambio de color/subrayado en enlaces.
* *General:* Diseño limpio, buena legibilidad, uso de whitespace, bordes redondeados suaves (ej. rounded-md).

Asegúrate de aplicar estos colores y principios de forma consistente en el diseño solicitado.
