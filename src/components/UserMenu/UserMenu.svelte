<script>
  /* Imports */
  import SwitchIcon from '../../icons/switch.svelte';
  import SwitchOnIcon from '../../icons/switch_on.svelte';
  import CheckIcon from '../../icons/check.svelte';
  import LinkIcon from '../../icons/link.svelte';
  import UserIcon from '../../icons/user.svelte';
  import ControllerIcon from '../../icons/controller.svelte';
  import PackageIcon from '../../icons/package.svelte';
  import ArrowRightIcon from '../../icons/arrow_right.svelte';
  import PlansIcon from '../../icons/plans.svelte';
  import CalendarIcon from '../../icons/calendar.svelte';

  /* Props */
  export let user;

  /* State */
  let coachMode = false;

  /* Functions */

  // TODO: Implement on click
  const toggleCoachMode = () => (coachMode = !coachMode);
</script>

<div class="user-menu flex flex-col">
  <!-- COACH MODE HEADER -->
  <div class="user-menu__mode flex items-center text-white select-none">
    <span>Coach Mode</span>
    <span class="ml-auto cursor-pointer" on:click={toggleCoachMode}>
      {#if coachMode}
        <SwitchOnIcon />
      {:else}
        <SwitchIcon />
      {/if}
    </span>
  </div>
  <!-- COACH SECTION -->
  <div class="user-menu__coach">
    <div
      class="item flex items-center hover:bg-gray-700 rounded-md cursor-pointer"
    >
      <img src={user.avatar} alt="Mew2King" class="rounded-md mr-4" />
      <span class="text-white">{user.username}</span>
      <span
        class="icon ml-auto rounded-full flex items-center justify-center"
        class:coach-mode={coachMode}
        class:active={!coachMode}
      >
        {#if coachMode}
          <LinkIcon />
        {:else}
          <CheckIcon />
        {/if}
      </span>
    </div>
    {#if !coachMode}
      <div
        class="item flex items-center hover:bg-gray-700 rounded-md cursor-pointer"
      >
        <img
          src={'images/team.png'}
          alt="The Dragon Team"
          class="rounded-md mr-4"
        />
        <span class="text-gray-400">The Dragon Team</span>
      </div>
    {/if}
    <hr class="border-gray-800" />
  </div>
  <!-- LINK SECTION -->
  <div class="user-menu__links">
    {#if !coachMode}
      <div
        class="item flex flex-1 items-center hover:bg-gray-700 rounded-md cursor-pointer"
        on:click={() => {}}
      >
        <span class="mr-4 icon flex justify-center items-center"
          ><UserIcon /></span
        >
        <span class="text-white">My coaches</span>
        <span class="ml-auto"><ArrowRightIcon /></span>
      </div>
      <div
        class="item flex flex-1 items-center hover:bg-gray-700 rounded-md cursor-pointer"
        on:click={() => {}}
      >
        <span class="mr-4 icon flex justify-center items-center"
          ><ControllerIcon /></span
        >
        <span class="text-white">My games</span>
        <span class="ml-auto"><ArrowRightIcon /></span>
      </div>
      <div
        class="item flex flex-1 items-center hover:bg-gray-700 rounded-md cursor-pointer"
        on:click={() => {}}
      >
        <span class="mr-4 icon flex justify-center items-center"
          ><PackageIcon /></span
        >
        <span class="text-white">Lesson bundles</span>
        <span class="ml-auto"><ArrowRightIcon /></span>
      </div>
    {:else}
      <div
        class="item flex flex-1 items-center hover:bg-gray-700 rounded-md cursor-pointer"
        on:click={() => {}}
      >
        <span class="mr-4 icon flex justify-center items-center"
          ><UserIcon /></span
        >
        <span class="text-white">My students</span>
        <span class="ml-auto"><ArrowRightIcon /></span>
      </div>
      <div
        class="item flex flex-1 items-center hover:bg-gray-700 rounded-md cursor-pointer"
        on:click={() => {}}
      >
        <span class="mr-4 icon flex justify-center items-center"
          ><ControllerIcon /></span
        >
        <span class="text-white">Lessons</span>
      </div>
      <div
        class="item flex flex-1 items-center hover:bg-gray-700 rounded-md cursor-pointer"
        on:click={() => {}}
      >
        <span class="mr-4 icon flex justify-center items-center"
          ><PlansIcon /></span
        >
        <span class="text-white">Training plans</span>
      </div>
      <div
        class="item flex flex-1 items-center hover:bg-gray-700 rounded-md cursor-pointer"
        on:click={() => {}}
      >
        <span class="mr-4 icon flex justify-center items-center"
          ><CalendarIcon /></span
        >
        <span class="text-white">Availability</span>
      </div>
    {/if}
    <hr class="border-gray-800" />
  </div>
  <!-- ACCOUNT SECTION -->
  <div class="user-menu__account flex flex-col">
    <span class="text-gray-400 cursor-pointer">View my profile</span>
    <span class="text-gray-400 cursor-pointer">Sign out</span>
  </div>
</div>

<style>
  /* MENU */
  .user-menu .item {
    height: 40px;
    padding: 8px;
  }

  .user-menu span {
    font-family: Graphik;
    font-style: normal;
    font-weight: normal;
    font-size: 14px;
    line-height: 100%;
  }

  .user-menu .icon {
    width: 24px;
    height: 24px;
  }

  /* MENU MODE */
  .user-menu .user-menu__mode {
    width: 244px;
    height: 40px;
    background: linear-gradient(
      274.13deg,
      rgba(125, 193, 244, 0.12) 11.16%,
      rgba(241, 67, 67, 0.12) 97.41%,
      rgba(241, 67, 67, 0.12) 97.41%
    );
    border-radius: 8px;
    text-transform: uppercase;
    padding: 12px;
    margin-bottom: 8px;
  }

  .user-menu .user-menu__mode span {
    font-size: 12px;
    display: flex;
    align-items: center;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  /* MENU COACH */
  .user-menu .user-menu__coach .icon {
    width: 20px;
    height: 20px;
  }

  .user-menu .user-menu__coach .active {
    background: #239f5c;
  }

  .user-menu .user-menu__coach img {
    width: 24px;
    height: 24px;
  }

  /* MENU ACCOUNT */
  .user-menu .user-menu__account {
    padding: 16px 8px 8px 8px;
  }

  .user-menu .user-menu__account span {
    height: 22px;
  }
</style>
