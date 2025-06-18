# 🪐  Star Wars Universe Explorer - 👽
<p align="center"> 
  <img src="https://media1.tenor.com/m/EyBWo1UCxYcAAAAC/pepe-peppo.gif" width="220"/>
</p>

---

## 📝 Descripción del Proyecto

Star Wars Universe Explorer es una aplicación web interactiva que permite explorar el vasto universo de Star Wars: personajes, planetas, naves estelares y vehículos. El objetivo es ofrecer una experiencia visual inmersiva, educativa y atractiva, con navegación fluida y diseño responsive tanto en PC como en móvil, utilizando la API oficial de Star Wars (SWAPI).

---

## 📚 Aprendizajes Obtenidos

- Uso avanzado de **HTML5** y **CSS3** para interfaces responsivas y atractivas.
- Implementación de menús adaptativos y animaciones con efectos visuales.
- Integración con APIs externas (SWAPI) para obtener datos dinámicos.
- Gestión de estados y navegación entre páginas con JavaScript.
- Integración de recursos multimedia (video de fondo, imágenes).
- Organización y reutilización de componentes visuales y estilos.
- Buenas prácticas de estructura de carpetas y documentación.

---

## 🔧 Tecnologías Utilizadas

- HTML5
- CSS3 (Flexbox, Grid, Media Queries, Animaciones)
- JavaScript (ES6+, Async/Await, Fetch API)
- SWAPI (Star Wars API) para datos dinámicos
- Star Wars Visual Guide para imágenes
- Iconos y fuentes externas (FontAwesome)

---

## 🗂️ Estructura del Proyecto

```
/ (raíz del proyecto)
│
├── index.html              # Página principal con navegación
├── style.css               # Estilos principales
├── README.MD               # Documentación del proyecto
│
├── img/                    # Recursos multimedia
│   ├── video/              # Videos de fondo
│   │   └── Dart Vader - 73654.mp4
│   ├── darth_vader.png     # Favicon
│   ├── starwarslogo.png    # Logo principal
│   ├── characters.jpeg     # Imagen de personajes
│   ├── planets.jpeg        # Imagen de planetas
│   ├── starships.jpeg      # Imagen de naves
│   └── vehicles.jpeg       # Imagen de vehículos
│
└── Pages/                  # Páginas de contenido
    ├── Characters/         # Personajes de Star Wars
    │   ├── characters.html
    │   ├── characters.js
    │   └── characters.css
    ├── Planets/            # Planetas del universo
    │   ├── planets.html
    │   ├── planets.js
    │   └── planets.css
    ├── Starships/          # Naves estelares
    │   ├── starships.html
    │   ├── starships.js
    │   └── starships.css
    └── Vehicles/           # Vehículos terrestres
        ├── vehicles.html
        ├── vehicles.js
        └── vehicles.css
```

---

## 🌐 Publicación en GitHub Pages

El proyecto puede ser publicado fácilmente en GitHub Pages. Solo sube el contenido del repositorio y configura la rama principal como fuente de GitHub Pages.

🔗 **[Ver Aplicación en Vivo](https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/)**

---

## ❓ Preguntas Frecuentes

**¿Cómo navego por la aplicación?**
> Desde la página principal, puedes acceder a las diferentes secciones: Personajes, Planetas, Naves y Vehículos. Cada sección muestra información detallada de los elementos del universo Star Wars.

**¿Puedo usar la app en móvil y PC?**
> Sí, el diseño es 100% responsive y se adapta perfectamente a cualquier dispositivo.

**¿De dónde vienen los datos?**
> Todos los datos provienen de la API oficial de Star Wars (SWAPI) y las imágenes del Star Wars Visual Guide.

**¿Cómo funcionan los modales de información?**
> Al hacer clic en cualquier tarjeta, se abre un modal con información detallada del elemento seleccionado.

---

## 👨‍💻 Autores del Proyecto

| Nombre        | Info                                |
|---------------|-------------------------------------|
| 🧑 Daniel Vinasco | Estudiante de Campuslands |
| 🧑 Jhon Ardila | Estudiante de Campuslands |
| 🎓 Formación      | Desarrollo Web y Frontend         |
| 💻 Enfoque        | HTML, CSS, JavaScript, APIs      |
| 📍 Ubicación      | Colombia |

---

## 🧩 Funcionalidades Destacadas

✔️ Navegación entre secciones de Star Wars: Personajes, Planetas, Naves, Vehículos
✔️ Integración con SWAPI para datos dinámicos y actualizados
✔️ Modales informativos con detalles completos de cada elemento
✔️ Diseño visual inmersivo con video de fondo de Darth Vader
✔️ Navegación por páginas con botones anterior/siguiente
✔️ Manejo de errores y estados de carga
✔️ Experiencia de usuario fluida y atractiva
✔️ Diseño responsive para todos los dispositivos

---

## 🧪 Código Destacado (Integración con SWAPI)

```javascript
// Ejemplo de carga de datos desde SWAPI
async function cargarNaves(url) {
    try {
        const response = await fetch(url);
        if (!response.ok) {
            throw new Error(`Error HTTP: ${response.status}`);
        }
        const responseJson = await response.json();
        
        responseJson.results.forEach(async (nave) => {
            // Crear tarjetas dinámicamente
            const tarjeta = document.createElement("div");
            tarjeta.className = "cards";
            
            // Obtener imagen desde Star Wars Visual Guide
            const id = nave.url.split('/').slice(-2)[0];
            let imageUrl = `https://starwars-visualguide.com/assets/img/starships/${id}.jpg`;
            
            // Manejo de errores de imagen
            try {
                const imgResponse = await fetch(imageUrl);
                if (imgResponse.status === 404) {
                    imageUrl = PLACEHOLDER_IMAGE_URL;
                }
            } catch (imgError) {
                imageUrl = PLACEHOLDER_IMAGE_URL;
            }
            
            tarjeta.style.backgroundImage = `url('${imageUrl}')`;
            // ... más lógica de creación de tarjetas
        });
    } catch (error) {
        console.error('Error al cargar la lista de naves:', error);
        mostrarMensajeModal('No se pudieron cargar las naves. ¡La comunicación está interferida!');
    }
}
```

---

## 💬 Conclusión

Este proyecto demuestra cómo se puede construir una experiencia web moderna, interactiva y educativa sobre el universo de Star Wars usando tecnologías web estándar y APIs externas. El enfoque en la usabilidad, el diseño responsive y la integración con SWAPI hacen de esta aplicación una referencia para proyectos educativos y de portafolio.

---

## 💭 Filosofía Personal

> "Que la fuerza del código esté contigo. Cada línea es una oportunidad para crear algo extraordinario y explorar nuevos mundos digitales." - Daniel Vinasco y Jhon Ardila

---

## 🎯 Entregable Final

Repositorio: [GitHub – Star Wars Universe Explorer](https://github.com/TU-USUARIO/NOMBRE-DEL-REPO)
Despliegue: [GitHub Pages – Star Wars Universe Explorer](https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/)

---

## 📞 Contacto y Redes

- 📧 Email: [vinascodaniel9@gmail.com](mailto:vinascodaniel9@gmail.com)
- 🐙 [GitHub](https://github.com/DanielSantiagoV)
- 🎵 [Spotify - Playlist de Programación](https://open.spotify.com/playlist/6a3d9qWLg1cOyMRWoqwr16)

---

## 📸 Capturas del Diseño

<p align="center">
  <b>Página Principal</b><br>
  <img src="img/star wars.png" width="600"/>
</p>


## ✨ Características del Proyecto

- 🎨 Diseño inmersivo inspirado en Star Wars con video de fondo
- 📱 100% responsive: experiencia perfecta en PC y móvil
- 🌌 Navegación fluida entre secciones del universo Star Wars
- 🔗 Integración completa con SWAPI para datos dinámicos
- 🖼️ Imágenes desde Star Wars Visual Guide
- 🎭 Modales informativos con detalles completos
- 🧩 Código organizado, reutilizable y fácil de mantener
- 🚀 Listo para despliegue en GitHub Pages o cualquier hosting estático

---

## 📝 Licencia

Este proyecto está bajo la Licencia MIT.
Consulta el archivo [LICENSE](./LICENSE) para más detalles.

---

<p align="center">
  Desarrollado con ❤️ por Daniel Vinasco y Jhon Ardila<br>
  🔥 <b><a href="https://github.com/DanielSantiagoV">Visita mi GitHub</a></b> 🚀
</p>

## 🛡️ Declaración Ética

Este proyecto fue desarrollado únicamente con fines educativos y de aprendizaje personal. No tiene ninguna intención de suplantar, copiar ni competir con la página oficial de Star Wars ni con ninguna de sus marcas registradas. Todos los recursos visuales, nombres y temáticas utilizados son empleados con el objetivo de practicar y demostrar habilidades de desarrollo web, diseño UI/UX y programación frontend.

Los datos utilizados provienen de la API pública de Star Wars (SWAPI) y las imágenes del Star Wars Visual Guide, utilizados únicamente con fines educativos.

Si eres parte de Lucasfilm, Disney o cualquier entidad oficial de Star Wars y consideras que algún contenido debe ser retirado o modificado, por favor contáctame y lo haré de inmediato.

---