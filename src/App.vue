<template>

  <header class="portfolio-header">
    <a class="portfolio-logo" href="#">
      <span class="logo-dot"></span>
      Mi Portfolio
    </a>
 
    
    <nav class="portfolio-nav" aria-label="Navegación principal">
      <a class="nav-link active" href="#home" onclick="setActive(this)">
        <i class="ti ti-home" style="font-size:15px; vertical-align:-2px; margin-right:5px;"></i>
        Home
      </a>
      <a class="nav-link" href="#about" onclick="setActive(this)">
        <i class="ti ti-user" style="font-size:15px; vertical-align:-2px; margin-right:5px;"></i>
        About me
      </a>
      <a class="nav-link" href="#gallery" onclick="setActive(this)">
        <i class="ti ti-photo" style="font-size:15px; vertical-align:-2px; margin-right:5px;"></i>
        Gallery
      </a>
      <a class="nav-link nav-cta" href="#contact" onclick="setActive(this)">
        <i class="ti ti-mail" style="font-size:15px; vertical-align:-2px; margin-right:5px;"></i>
        Contact
      </a>
    </nav>
 
  </header>

  <!-- Home -->
  <section id="home" class="hero">

    <div class="container text-center">

      <h1 class="display-3 fw-bold">
        Bienvenid@ a mi Portafolio
      </h1>

      <p class="lead">
        Informacion Estudiantil y algunos de mis proyectos realizados
      </p>

    </div>

  </section>

  <!-- About -->
  <section id="about" class="container py-5">

    <h2 class="text-center mb-4">
      SOBRE MI
    </h2>

    <div class="row align-items-center">

      <div class="col-md-4 text-center">

        <img :src="fotoPerfil" class="img-fluid rounded-circle shadow perfil-img" alt="Foto de perfil"/>
      </div>

      <div class="col-md-8">

        <p>
          Holaa! Mi nombre Ian Karim De Anda Mendez , soy estudiante de universidad en la carrera de Entornos Virtuales y Negocios Digitales , Actualmente me encuentro cursando el 5to cuatrimestre, Me gusta mucho dibujar y escuchar musica para pasar el tiempo, Actualmente cuento con varias habilidades las cuales son el manejo apps de diseño como canva o figma, tambien tengo habilidades sociales como el trabajo en equipo y la comunicacion, Me gusta mucho el trabajo en equipo y aprender cosas nuevas.
        </p>

      </div>

    </div>

  </section>

  <!-- Gallery -->
  <section id="gallery" class="bg-light py-5">

    <div class="container">

      <h2 class="text-center mb-4">
        Galeria Personal
      </h2>

      <div class="row g-4">

       <div
  class="col-md-4"
  v-for="proyecto in proyectos"
  :key="proyecto.titulo"
>

  <div class="card h-100 shadow-sm">

    <img
  :src="proyecto.imagen"
  class="card-img-top"
  :alt="proyecto.titulo"
>

    <div class="card-body">

      <h5 class="card-title">
        {{ proyecto.titulo }}
      </h5>

      <p class="card-text">
        {{ proyecto.descripcion }}
      </p>

    </div>

  </div>

</div>

      </div>

    </div>

  </section>

  <!-- Contact -->
  <section id="contact" class="container py-5">

    <h2 class="text-center mb-4">
      Contactame por este medio
    </h2>

    <form @submit.prevent="sendForm">

      <div class="mb-3">
        <input
          type="text"
          class="form-control"
          placeholder="Your Name"
          v-model="name"
          required
        >
      </div>

      <div class="mb-3">
        <input
          type="email"
          class="form-control"
          placeholder="Your Email"
          v-model="email"
          required
        >
      </div>

      <div class="mb-3">
        <textarea
          class="form-control"
          rows="5"
          placeholder="Your Message"
          v-model="message"
          required
        ></textarea>
      </div>

      <button
        type="submit"
        class="btn btn-primary"
      >
        Send Message
      </button>

    </form>

  </section>

  <!-- Footer -->
  <footer class="bg-dark text-white text-center py-3">

    <p class="mb-0">
      © 2026 My Portfolio
    </p>

  </footer>
</template>

<script setup>
import { ref } from 'vue'

import fotoPerfil from './assets/fotoPerfil.jpeg'
import proyecto1 from './assets/figma.png'
import proyecto2 from './assets/logoVocary.png'
import proyecto3 from './assets/pagcafe .png'
import proyecto4 from './assets/ProyectoBlender.png'
import proyecto5 from './assets/dibujo.jpeg'
import proyecto6 from './assets/proyecto32.png'

const name = ref('')
const email = ref('')
const message = ref('')

const proyectos = [
  {
    imagen: proyecto1,
    titulo: 'Diseño en Figma',
    descripcion: 'Actividad entregada en Figma sobre nuestra experiencia al usar los lentes de Realidad Virtual.'
  },
  {
    imagen: proyecto2,
    titulo: 'Proyecto Universitario',
    descripcion: 'Proyecto colaborativo  creado con mi equipo de integradora llamado VOCARY el cual es un proyecto pensado en los estudiantes egresados de la preparatoria.'
  },
  {
    imagen: proyecto3,
    titulo: 'Desarrollo Web',
    descripcion: 'Página web desarrollada durante la universidad.'
  },
  {
    imagen: proyecto4,
    titulo: 'Blender 2D',
    descripcion: 'Vistazo de un Proyecto hecho en Blender con un personaje hecho por mi.'
  },
  {
    imagen: proyecto5,
    titulo: 'Apartado Creativo',
    descripcion: 'Algunos de mis dibujos hechos por mi cuenta.'
  },
  {
    imagen: proyecto6,
    titulo: 'Actividades Laborales',
    descripcion: 'Algunas de las actividades realidadas en mi entonro de trabajo en el Mcdonalds, actividad llamada puerta.'
  }
]

function sendForm() {
  alert(
`Name: ${name.value}
Email: ${email.value}
Message: ${message.value}`
  )

  name.value = ''
  email.value = ''
  message.value = ''
}
</script>