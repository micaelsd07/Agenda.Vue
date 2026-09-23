<template>
  <nav>
    <RouterLink to="/">Início</RouterLink>
    <RouterLink to="/tarefas">Minhas tarefas</RouterLink>
  </nav>
  <main>
    <RouterView />
  </main>
</template>

<style>
nav {
  display: flex;
  gap: 16px;
  justify-content: center;
  padding: 16px;
  border-bottom: 1px solid #ddd;
}
nav a {
  color: #42b883;
  text-decoration: none;
  font-weight: 600;
}
nav a.router-link-exact-active {
  text-decoration: underline;
}
main {
  max-width: 600px;
  margin: 0 auto;
  padding: 24px 16px;
  text-align: center;
}
</style>
