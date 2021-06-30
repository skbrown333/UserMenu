<script>
  /* IMPORTS */
  import Sidebar from './components/Sidebar/Sidebar.svelte';
</script>

<main>
  <div class="app w-screen h-screen flex">
    <Sidebar />
  </div>
</main>

<style global lang="postcss">
  @tailwind base;
  @tailwind components;
  @tailwind utilities;

  @layer utilities {
    .p-12px {
      padding: 12px;
    }

    .w-64px {
      width: 64px;
    }
  }

  .app {
    background-color: #030404;
  }

  @font-face {
    font-family: 'Graphik';
    font-weight: 400;
    src: url('../fonts/Graphik/Graphik-400-Regular.otf');
  }
</style>
