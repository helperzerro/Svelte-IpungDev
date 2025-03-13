<script lang="ts">
  import { onMount } from "svelte";

  export let title: string;
  let isVisible = false;
  let widget: HTMLElement; // Deklarasikan tipe widget sebagai HTMLElement

  onMount(() => {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            isVisible = true;
          }
        });
      },
      { threshold: 0.5 }
    );

    if (widget) {
      observer.observe(widget); // Mulai observasi elemen
    }

    return () => observer.disconnect(); // Cleanup observer
  });
</script>

<div
  bind:this={widget}
  class={`transition-transform duration-700 ease-in-out transform ${
    isVisible ? "opacity-100 translate-y-0" : "opacity-0 translate-y-10"
  }`}
>
  <div class="bg-blue-500 p-4 rounded-lg shadow-lg text-white">
    <h3 class="text-xl font-bold">{title}</h3>
    <p class="mt-2">
      <slot></slot>
    </p>
  </div>
</div>
