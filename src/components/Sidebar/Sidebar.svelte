<script>
  /* IMPORTS */
  import Logo from '../../icons/logo.svelte';
  import Popover from '../Popover/Popover.svelte';
  import UserMenu from '../UserMenu/UserMenu.svelte';

  /* STATE */

  // Mock users
  const users = [
    {
      username: 'Mew2King',
      avatar: 'images/m2k.png',
    },
  ];
</script>

<div class="sidebar p-12px flex-1 flex flex-col items-center">
  <!-- LOGO -->
  <div class="sidebar__logo mb-4">
    <Logo />
  </div>
  <!-- USER SECTION -->
  <div class="sidebar__users">
    {#each users as user}
      <div class="sidebar__users__user">
        {#if user.avatar}
          <Popover overlayComponent={UserMenu} {user}>
            <img
              src={user.avatar}
              alt="Mew2King"
              class="rounded-md cursor-pointer"
            />
          </Popover>
        {:else}
          <!-- TODO: Display placeholder -->
        {/if}
      </div>
    {/each}
  </div>
</div>

<style>
  .sidebar {
    background-color: #181a1e;
    max-width: 64px;
  }
</style>
