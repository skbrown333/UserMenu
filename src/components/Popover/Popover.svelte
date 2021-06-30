<script>
  /* IMPORTS */
  import Overlay from './Overlay/Overlay.svelte';

  /* PROPS */
  export let user;
  export let overlayComponent;

  /* STATE */
  let children;
  let overlay = null;

  /**
   * Creates a popover for an element on click
   */
  const showPopover = () => {
    // destroy overlay if it already exists
    if (overlay) {
      overlay.$destroy();
      overlay = null;
    }

    // get the position of the element
    const boundBox = children.getBoundingClientRect();
    const height = boundBox.height;
    const left = boundBox.left.toString() + 'px';
    const top = (boundBox.top + height + 10).toString() + 'px';

    // create overlay element
    overlay = new Overlay({
      target: document.body,
      props: { top, left, user, destroyPopover, overlayComponent },
    });
  };

  /**
   * Destroys the popover element
   */
  const destroyPopover = () => {
    if (overlay) {
      overlay.$destroy();
      overlay = null;
    }
  };
</script>

<div class="popover">
  <div class="popover__base" bind:this={children} on:click={showPopover}>
    <slot />
  </div>
</div>
