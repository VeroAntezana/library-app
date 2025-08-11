<script setup>
const libros = [
  {
    titulo: "Cien Años de Soledad",
    autor: "Gabriel García Márquez",
    imagen: "https://edit.org/images/cat/portadas-libros-big-2019101610.jpg"
  },
  {
    titulo: "Don Quijote de la Mancha",
    autor: "Miguel de Cervantes",
    imagen: "https://edit.org/images/cat/portadas-libros-big-2019101610.jpg"
  },
  {
    titulo: "La Sombra del Viento",
    autor: "Carlos Ruiz Zafón",
    imagen: "https://edit.org/images/cat/portadas-libros-big-2019101610.jpg"
  },
  {
    titulo: "El Principito",
    autor: "Antoine de Saint-Exupéry",
    imagen: "https://edit.org/images/cat/portadas-libros-big-2019101610.jpg"
  }
]
</script>

<template>
  <div class="layout">
    <!-- Sidebar -->
    <aside class="sidebar">
      <h2 class="logo">📚 Biblioteca</h2>
      <nav class="menu">
        <a href="#">Clientes</a>
        <a href="#">Órdenes</a>
      </nav>
    </aside>

    <!-- Contenido principal -->
    <div class="dashboard">
      <h1 class="titulo">📚 Library App</h1>
      <div class="contenedor-tarjetas">
        <div class="tarjeta" v-for="(libro, index) in libros" :key="index">
          <img :src="libro.imagen" :alt="libro.titulo" class="imagen-libro" />
          <div class="info-libro">
            <h2>{{ libro.titulo }}</h2>
            <p>{{ libro.autor }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.layout {
  display: flex;
  min-height: 100vh;
  background-color: #f4f6f8;
  font-family: 'Segoe UI', sans-serif;
}

/* Sidebar */
.sidebar {
  width: 200px;
  background-color: #2c3e50;
  color: white;
  padding: 2rem 1rem;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.logo {
  font-size: 1.3rem;
  font-weight: bold;
  margin-bottom: 1rem;
}

.menu {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.menu a {
  color: #ecf0f1;
  text-decoration: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  transition: background 0.3s;
}

.menu a:hover {
  background-color: #34495e;
}

/* Panel de biblioteca */
.dashboard {
  flex: 1;
  padding: 2rem;
  text-align: center;
}

.titulo {
  font-size: 2.2rem;
  margin-bottom: 2rem;
  color: #2c3e50;
}

.contenedor-tarjetas {
  display: flex;
  flex-wrap: wrap;
  gap: 1.5rem;
  justify-content: center;
}

.tarjeta {
  width: 220px;
  background-color: #ffffff;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.3s ease;
}

.tarjeta:hover {
  transform: translateY(-5px);
}

.imagen-libro {
  width: 100%;
  height: 280px;
  object-fit: cover;
}

.info-libro {
  padding: 1rem;
  text-align: left;
}

.info-libro h2 {
  font-size: 1.1rem;
  margin: 0 0 0.5rem;
  color: #34495e;
}

.info-libro p {
  font-size: 0.9rem;
  color: #7f8c8d;
}
</style>
