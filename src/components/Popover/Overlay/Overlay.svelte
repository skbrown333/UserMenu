<script>
  /* IMPORTS */
  import { clickOutside } from '../../../utils/utils.js';

  /* PROPS */
  export let user;
  export let left;
  export let top;
  export let destroyPopover;
  export let overlayComponent;
</script>

<div
  class="overlay border-md absolute"
  style="left: {left}; top: {top}"
  use:clickOutside
  on:click_outside={destroyPopover}
>
  <svelte:component this={overlayComponent} {user} />
</div>

<style>
  .overlay {
    background-color: #181a1e;
    border: 1px solid rgba(121, 134, 148, 0.08);
    box-sizing: border-box;
    box-shadow: 0px -8px 64px rgba(0, 0, 0, 0.48);
    border-radius: 12px;
    padding: 8px;
  }
</style>
