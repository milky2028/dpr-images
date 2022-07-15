<script lang="ts">
  export let src: string;
  export let alt: string;

  export let width: string;
  export let height: string;

  export let containerStyles: string | null = null;
  export let imageStyles: string | null = null;

  export let under = true;
</script>

<style lang="postcss">
  .container {
    display: grid;
    grid-template-areas: "main";
  }

  picture {
    grid-area: main;
  }

  .under {
    z-index: -1;
  }

  img {
    object-fit: cover;
  }

  .content {
    grid-area: main;
  }
</style>

<div class="container {containerStyles}">
  <picture class={imageStyles} class:under>
    <source
      media="(min-width: 834px)"
      srcset="/{src}-desktop-1x.webp 1x, /{src}-desktop-2x.webp 2x"
    />
    <source
      media="(min-width: 428px)"
      srcset="/{src}-tablet-1x.webp 1x, /{src}-tablet-2x.webp 2x"
    />
    <source
      media="(max-width: 428px)"
      srcset="/{src}-phone-1x.webp 1x, /{src}-phone-2x.webp 2x, /{src}-phone-3x.webp 3x"
    />
    <img src="/{src}-desktop-1x.webp" {alt} style="width: {width}; height: {height};" />
  </picture>
  <div class="content">
    <slot />
  </div>
</div>
