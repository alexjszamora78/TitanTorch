
# Titan Network Torch (TNT)
Es una poderosa Herramienta de Procesamiento del lenguaje natural, aprendizaje por refuerzo, análisis de series temporales, detección de anomalías

## Versión 1.0

## Crear un entorno virtual (Linux)

```bash
python -m venv env
source env/bin/active
```

## Crear un entorno virtual (Windows)

```bash
python -m venv env
env\Scripts\activate.bat
```


## Instalar dependencias necesarias

```bash
pip install TitanTorch
```


## Archivo config.json

Debe crear un archivo config.json con las preguntas y respuestas previamente formuladas para el aprendizaje del modelo
La estructura de este JSON debe seguir estas pautas

```json
[
    {
      "tag": "saludo",
      "patterns": [
        "Hola",
        "Buenos días",
        "¿Cómo estás?"
      ],
      "responses": [
        "¡Hola! ¿En qué puedo ayudarte hoy?",
        "¡Buenos días! ¿Cómo puedo asistirte?",
        "Estoy aquí para ayudarte. ¿En qué puedo colaborar contigo?"
      ]
    }
]
```

Los tag son el ID del tipo de interacción que se esta realizando.
Los patterns son los patrones de entra del input dele usuario.
Los responses son un conjunto de respuestas que el modelo puede usar para retonar

## Ejemplo de config.json

```json
[
    {
      "tag": "saludo",
      "patterns": [
        "Hola",
        "Buenos días",
        "¿Cómo estás?"
      ],
      "responses": [
        "¡Hola! ¿En qué puedo ayudarte hoy?",
        "¡Buenos días! ¿Cómo puedo asistirte?",
        "Estoy aquí para ayudarte. ¿En qué puedo colaborar contigo?"
      ]
    },
    {
      "tag": "despedida",
      "patterns": [
        "Adiós",
        "Hasta luego",
        "Nos vemos luego"
      ],
      "responses": [
        "¡Adiós! Que tengas un buen día.",
        "¡Hasta luego! No dudes en volver si necesitas ayuda.",
        "Nos vemos pronto. ¡Cuídate!"
      ]
    },
    {
      "tag": "ayuda",
      "patterns": [
        "Necesito ayuda",
        "Puedes ayudarme",
        "Quiero que me ayudes",
        "¿Podrías ayudarme?",
        "¿Podrías aconsejarme?",
        "¿Podrías darme un aconsejo?",
        "Dame un consejo"
      ],
      "responses": [
        "¡Claro! ¿Qué ocurre?",
        "¡Sí, por supuesto! ¿Pasa algo?",
        "¡Sí! ¿Te sientes mal?",
        "¡Sí! Cuentame por favor, estoy para ayudarte.",
        "¡Por supuesto! ¿En qué puedo ayudarte?",
        "¡Por supuesto! Cuentame tu situación, por favor.",
        "¡Por supuesto! Estoy para ayudarte, cuéntame sobre tu situación.",
        "¡Por supuesto! Dime como te sientes y qué podría ayudarte."
      ]
    },  
    {
      "tag": "definicion_burnout",
      "patterns": [
          "¿Qué es el burnout?",
          "¿Cómo puedo reconocer si estoy experimentando burnout?",
          "Señales de burnout"
      ],
      "responses": [
          "El burnout es un estado de agotamiento físico, emocional y mental causado por el estrés crónico en el trabajo.",
          "Algunas señales de burnout incluyen el agotamiento constante, la falta de motivación, la irritabilidad, el aislamiento social y la disminución del rendimiento laboral.",
          "Si te sientes abrumado, desmotivado y agotado física y emocionalmente, es posible que estés experimentando burnout. Es importante buscar apoyo y tomar medidas para cuidar tu bienestar."
      ]
    },
    {
      "tag": "ansiedad",
      "patterns": [
        "Siento que no puedo concentrarme en el trabajo.",
        "Estoy constantemente preocupado por mi desempeño laboral.",
        "Me cuesta trabajo relajarme después de un día de trabajo intenso."
      ],
      "responses": [
        "Prueba técnicas de respiración profunda para reducir la ansiedad.",
        "Haz pausas cortas durante el día para desconectar y relajarte.",
        "Habla con tu supervisor sobre cómo te sientes, podría ofrecerte apoyo adicional."
      ]
    },
    {
      "tag": "depresion",
      "patterns": [
        "Me siento mal",
        "No me siento del todo bien",
        "Siento que mi trabajo no tiene sentido o propósito.",
        "No tengo energía para enfrentar mis responsabilidades laborales.",
        "Me siento abrumado y sin esperanza en mi trabajo."
      ],
      "responses": [
        "Considera hablar con un terapeuta o consejero para obtener apoyo emocional.",
        "Busca actividades que disfrutes fuera del trabajo para mejorar tu estado de ánimo.",
        "Habla con recursos humanos sobre la posibilidad de ajustar tu carga de trabajo si te sientes abrumado."
      ]
    },
    {
      "tag": "estres",
      "patterns": [
        "Me siento constantemente tenso y nervioso en el trabajo.",
        "Tengo dificultades para conciliar el sueño debido al estrés laboral.",
        "Siento que tengo demasiadas tareas y plazos para cumplir."
      ],
      "responses": [
        "Haz ejercicio regularmente para liberar tensiones y reducir el estrés.",
        "Practica técnicas de manejo del tiempo para priorizar tareas y evitar la sobrecarga.",
        "Considera hablar con tu supervisor sobre la redistribución de tareas si te sientes abrumado."
      ]
    }
]
```

## Ejecución

```python
from TitanTorch import ChatBot

response = ChatBot("config.json")
```

## Output

![Output](resources/output.png)


## ¿ Cuándo usar ChatBot como solución para proyectos ?

* **Servicio de atención al cliente 24/7:** Para responder preguntas frecuentes, resolver problemas básicos, guiar al usuario por el sitio web, recomendar productos, responder preguntas de envíos y devoluciones, etc.

* **Agendar Citas:** Puedes usarlo como alternativa para gestionar la agenda, programar citas y enviar recordatorios.

* **Captación de clientes potenciales:** Puede recopilar información y datos del usuario para clasificarlos.

* **Asistente virtual:** Para ayudar a los usuarios a crear listas de tareas, gestionar su tiempo, etc.

* **Educación y formación:** Para proporcionar respuestas rápidas a preguntas, explicación de conceptos y apoyo en el aprendizaje. Para enseñar a aprender idiomas, matemáticas, etc.

* **Juegos Interactivos:** Para crear o predecir experiencias de juego y usuario más inmersas y personalizadas.

* **Marketing y Publicidad:** Para segmentar la audiencia y ofrecer mensajes personalizados acordes a ella.

* **Investigación de mercado:** Para recopilar opiniones de los usuarios sobre productos o servicios. 

* **Reservas de viajes:** Para reservar vuelos, hoteles, coches y otros servicios turísticos. 

* **Asistencias de compras online:** Para encontrar productos, comparar precios y obtener recomendaciones personalizadas. 

* **Entretenimientos:** Para jugar juegos, contar historias, dar predicciones de gustos sobre las mejores o peores (mediante un filtro) películas y libros, etc.

* **Gestión de redes sociales:** Para responder a los mensajes, publicar contenido, analizar datos, etc.


## Ejemplo de uso tomando como ejemplo el proyecto 038.

El Objetivo general del [Proyecto 038](resources/Documento038.docx) es Desarrollar una plataforma integral de **análisis predictivo** y experiencia de usuario en comercio electrónico que emplee técnicas avanzadas de recopilación y análisis de datos para **predecir** el comportamiento del usuario, ofrecer recomendaciones personalizadas y mejorar la interacción en el sitio web, optimizando así la navegación y la experiencia de compra para aumentar la satisfacción del cliente y potenciar el rendimiento del comercio electrónico.

* Se toma en cuenta que lo que se quiere es predecir, pronosticar y una de las posibles soluciones es la utilización del ChatBot

* Primeramente se tendría que crear la configuración (JSON) correspondiente pra entrenar al modelo de aprendizaje

```json
[
    {
      "tag": ...,
      "patterns": [
        ...
      ],
      "responses": [
        ...
      ]
    }
]
```

* En el tag se debe poner una palabra clave para el uso que se está empleando, en este caso se pudiera usar la categoría del profucto o servicio

* El patterns son los gusto o preferencias del usuario que en la tabla de interés aparece como (userInterests) **Intereses del Usuario** 

* Los respondes son productos o servicios que está brindando la Empresa y que en la tabla de interés aprece como (comProducts) y (comServices) respectivamente

* Solo quedaría pasar esos valores proporciondos por el grupo de Scrapping para el config.json


## Ejemplo del config.json con los datos proporciondos por el grupo de Scrapping

```json
[
    {
	  "tag": "tecnologia",
	  "patterns": [
	    "teléfonos inteligentes",
	    "portátiles",
	    "auriculares inalámbricos",
	    "altavoces inteligentes",
	    "tabletas",
	    "smartwatches",
	    "cámaras digitales",
	    "impresoras",
	    "componentes de PC"
	  ],
	  "responses": [
	    "Teléfono inteligente de última generación con cámara de alta resolución y procesador potente",
	    "Portátil ultradelgado y ligero con pantalla de alta definición y gran autonomía",
	    "Auriculares inalámbricos con cancelación de ruido activa y sonido de alta fidelidad",
	    "Altavoces inteligentes con asistente de voz y conectividad Bluetooth",
	    "Tablet con pantalla táctil de gran tamaño y sistema operativo Android",
	    "Smartwatch con funciones de seguimiento de actividad física y notificaciones",
	    "Cámara digital réflex con objetivo intercambiable y resolución de alta calidad",
	    "Impresora multifunción con conectividad inalámbrica y capacidad de impresión a doble cara",
	    "Componentes de PC de alta gama, incluyendo tarjeta gráfica, procesador, memoria RAM y almacenamiento SSD"
	  ]
	},
	{
	  "tag": "moda",
	  "patterns": [
	    "ropa para hombre",
	    "ropa para mujer",
	    "zapatos",
	    "bolsos",
	    "accesorios",
	    "ropa deportiva",
	    "trajes",
	    "vestidos de fiesta",
	    "jeans"
	  ],
	  "responses": [
	    "Camisasde algodón con diseños modernos y tallas para todos",
	    "Pantalones vaqueros ajustados, rectos o acampanados con diferentes lavados",
	    "Vestidos de verano de algodón fresco y colores vibrantes",
	    "Zapatos de tacón alto para ocasiones especiales",
	    "Bolsos de mano para mujer de diferentes tamaños y materiales",
	    "Ropa deportiva de alta calidad para correr, entrenar o hacer ejercicio",
	    "Trajes de chaqueta y pantalón elegantes para ocasiones formales",
	    "Vestidos de fiesta largos o cortos con diseños únicos y elegantes",
	    "Jeans de diferentes estilos, colores y tallas para hombre y mujer"
	  ]
	},
	{
	  "tag": "hogar",
	  "patterns": [
	    "muebles",
	    "decoración",
	    "textiles para el hogar",
	    "electrodomésticos",
	    "iluminación",
	    "artículos de cocina",
	    "alfombras",
	    "cortinas",
	    "cojines"
	  ],
	  "responses": [
	    "Sofá de cuero con diseño moderno y confortable para tu salón",
	    "Mesa de comedor de madera maciza para 6 personas",
	    "Lámparas de techo con diseño elegante y funcional para tu habitación",
	    "Electrodomésticos de última generación como lavavajillas, lavadora y secadora",
	    "Textiles para el hogar como sábanas, toallas y cortinas de alta calidad",
	    "Artículos de cocina como ollas, sartenes y cubiertos de acero inoxidable",
	    "Alfombras de diferentes materiales y estilos para tu hogar",
	    "Cortinas opacas o translúcidas para controlar la entrada de luz",
	    "Cojines decorativos con diferentes estampados y tejidos para tu sofá"
	  ]
	},
	{
	  "tag": "belleza",
	  "patterns": [
	    "productos de belleza",
	    "cosméticos",
	    "maquillaje",
	    "cuidado de la piel",
	    "cuidado del cabello",
	    "perfumes",
	    "productos para hombres",
	    "productos para mujeres"
	  ],
	  "responses": [
	    "Cremas faciales hidratantes y antiedad para todos los tipos de piel",
	    "Productos de maquillaje de alta calidad como sombras de ojos, labiales y bases",
	    "Champús y acondicionadores para el cuidado del cabello",
	    "Perfumes para hombre y mujer con aromas únicos y duraderos",
	    "Productos para el cuidado personal como desodorantes, jabones y cremas para manos",
	    "Productos de afeitado para hombres como espuma de afeitar y bálsamos después del afeitado"
	  ]
	},
	{
	  "tag": "libros",
	  "patterns": [
	    "libros de ficción",
	    "libros de no ficción",
	    "libros de texto",
	    "biografías",
	    "novelas",
	    "cuentos",
	    "poesía",
	    "libros infantiles",
	    "libros de cocina",
	    "libros de viajes"
	  ],
	  "responses": [
	    "Novela de misterio y suspense con giros inesperados",
	    "Biografía de un personaje histórico fascinante",
	    "Libro de cocina con recetas deliciosas y fáciles de seguir",
	    "Libro de viajes con consejos y recomendaciones para explorar el mundo",
	    "Libro infantil con ilustraciones coloridas e historias encantadoras",
	    "Libro de no ficción sobre un tema interesante y actual",
	    "Libro de texto para estudiantes de primaria, secundaria o universidad",
	    "Poesía contemporánea con versos emotivos y reflexivos",
	    "Colección de cuentos clásicos con moralejas para todos",
	    "Libro de autoayuda con consejos prácticos para mejorar tu vida"
	  ]
	},
	{
	  "tag": "viajes",
	  "patterns": [
	    "vuelos",
	    "hoteles",
	    "alojamientos",
	    "cruceros",
	    "viajes en tren",
	    "tours",
	    "paquetes vacacionales",
	    "rent a car",
	    "seguros de viaje",
	    "actividades turísticas"
	  ],
	  "responses": [
	    "Vuelos baratos a destinos nacionales e internacionales",
	    "Hoteles de lujo, boutique o económicos en diferentes ciudades",
	    "Alojamientos alternativos como apartamentos, villas o casas rurales",
	    "Cruceros por el Mediterráneo, Caribe o Alaska",
	    "Viajes en tren panorámicos por Europa",
	    "Tours guiados por las principales ciudades del mundo",
	    "Paquetes vacacionales personalizados para todos los gustos y presupuestos",
	    "Rent a car con diferentes modelos de vehículos",
	    "Seguros de viaje para cubrir imprevistos",
	    "Actividades turísticas como museos, parques temáticos o excursiones"
	  ]
	},
	{
	  "tag": "deportes",
	  "patterns": [
	    "ropa deportiva",
	    "calzado deportivo",
	    "accesorios deportivos",
	    "equipamiento deportivo",
	    "suscripciones a gimnasios",
	    "clases de fitness",
	    "material para deportes de equipo",
	    "material para deportes individuales",
	    "nutrición deportiva",
	    "complementos deportivos"
	  ],
	  "responses": [
	    "Ropa deportiva de alta calidad para correr, entrenar o hacer ejercicio",
	    "Calzado deportivo cómodo y resistente para diferentes disciplinas",
	    "Accesorios deportivos como relojes inteligentes, auriculares inalámbricos y cintas para el sudor",
	    "Equipamiento deportivo para gimnasio, yoga, pilates o entrenamiento en casa",
	    "Suscripciones a gimnasios con acceso a diferentes actividades",
	    "Clases de fitness como spinning, zumba o crossfit",
	    "Material para deportes de equipo como fútbol, baloncesto o voleibol",
	    "Material para deportes individuales como tenis, golf o natación",
	    "Nutrición deportiva para optimizar el rendimiento",
	    "Complementos deportivos para aumentar la energía, la fuerza o la recuperación"
	  ]
	},
	{
	  "tag": "entretenimiento",
	  "patterns": [
	    "películas",
	    "series de televisión",
	    "música",
	    "videojuegos",
	    "consolas de videojuegos",
	    "libros de cómics",
	    "entradas para eventos",
	    "instrumentos musicales",
	    "material de dibujo",
	    "juegos de mesa"
	  ],
	  "responses": [
	    "Películas de estreno en cine o en streaming",
	    "Series de televisión de diferentes géneros como drama, comedia o ciencia ficción",
	    "Música de todos los estilos, desde pop hasta rock o clásica",
	    "Videojuegos para PC, consola o móvil",
	    "Consolas de videojuegos de última generación como Playstation 5 o Xbox Series X",
	    "Libros de cómics de superhéroes, manga o novela gráfica",
	    "Entradas para conciertos, espectáculos teatrales o eventos deportivos",
	    "Instrumentos musicales como guitarras, pianos o baterías",
	    "Material de dibujo como lápices, colores, acuarelas o pinceles",
	    "Juegos de mesa para todas las edades, desde clásicos hasta modernos"
	  ]
	},
	{
	  "tag": "mascotas",
	  "patterns": [
	    "comida para mascotas",
	    "accesorios para mascotas",
	    "productos de higiene para mascotas",
	    "juguetes para mascotas",
	    "ropa para mascotas",
	    "camas para mascotas",
	    "servicios veterinarios",
	    "adopción de mascotas",
	    "cuidado de mascotas",
	    "adiestramiento de mascotas"
	  ],
	  "responses": [
	    "Comida para perros, gatos, conejos u otras mascotas",
	    "Accesorios para mascotas como collares, correas, arneses o transportines",
	    "Productos de higiene para mascotas como champús, cepillos o peines",
	    "Juguetes para mascotas de diferentes tamaños y materiales",
	    "Ropa para mascotas como abrigos, jerseys o impermeables",
	    "Camas para mascotas de diferentes tamaños y diseños",
	    "Servicios veterinarios como consultas, vacunas o cirugías",
	    "Adopción de mascotas de refugios o protectoras",
	    "Cuidado de mascotas a domicilio o en residencias",
	    "Adiestramiento de mascotas para corregir comportamientos y mejorar la convivencia"
	  ]
	}
]
```


## Ejecución de la prueba 038

```python
from TitanTorch import ChatBot

response = ChatBot("config.json")
```


## Output

![Output](resources/output2.png)


## Información para Desarrolladores (DEV)

* [Aquí pueden ver el código fuente con que fue creado la librería TitanTorch](resources/main.py)