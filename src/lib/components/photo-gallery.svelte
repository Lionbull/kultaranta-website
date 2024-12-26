<script lang="ts">
    import { onMount } from 'svelte';
    export let images: any = [];

    let currentIndex = -1; // Index of the currently viewed image
    let isMobile = false; // Tracks whether the view is on mobile

    function updateIsMobile() {
        if (typeof window !== "undefined") {
            isMobile = window.innerWidth <= 768; // Adjust breakpoint as needed
        }
    }

    // Set up dynamic resizing
    onMount(() => {
        updateIsMobile(); // Initialize on load
        window.addEventListener("resize", updateIsMobile); // Update on resize
    });
  
    function openImage(index: number) {
      currentIndex = index;
    }
  
    function closeImage() {
      currentIndex = -1;
    }
  
    function nextImage() {
      currentIndex = (currentIndex + 1) % images.length;
    }
  
    function prevImage() {
      currentIndex = (currentIndex - 1 + images.length) % images.length;
    }
  </script>
  
  <!-- svelte-ignore a11y-no-static-element-interactions -->
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <div class="image-grid">
    {#each images.slice(0, isMobile ? 4 : images.length) as image, index}
      <div class="image-container" on:click={() => openImage(index)}>
          <img src={image} alt="kultaranta area" loading="lazy" />
      </div>
    {/each}
  </div>
  
  {#if currentIndex !== -1}
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div class="modal">
        <div class="image-counter">
          {currentIndex + 1} / {images.length}
        </div>   
        <div class="overlay" on:click={closeImage} />
        <img src={images[currentIndex]} alt="Full size" class="modal-image" />
        <button class="close-button" on:click={closeImage}>×</button>
        <button class="nav-button prev" on:click={prevImage}>‹</button>
        <button class="nav-button next" on:click={nextImage}>›</button>
    </div>
  {/if}
  
  <style>
    .image-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 20px;
      box-sizing: border-box;
      width: 100%;
      margin: 0;
    }
  
    .image-container {
      position: relative;
      width: 100%;
      aspect-ratio: 1 / 1;
      overflow: hidden;
      border-radius: 8px;
      cursor: pointer;

      transition: filter 250ms, transform 250ms;
      backface-visibility: hidden; /* Prevent rendering glitches */
      transform: translateZ(0); /* Force hardware acceleration */

      &:hover {
        filter: brightness(0.85);
        transform: scale(1.02);
      }
    }
  
    img {
      position: absolute;
      top: 50%;
      left: 50%;
      width: 100%;
      height: 100%;
      object-fit: cover;
      transform: translate(-50%, -50%);
    }
  
    .modal {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100svh;
      background: rgba(0, 0, 0, 0.8);
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }
  
    .overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: transparent;
      cursor: pointer;
    }
  
    .modal-image {
      max-width: 80%;
      max-height: 90%;
      height: auto;
      width: auto;
      object-fit: contain;
      border-radius: 8px;
      z-index: 1001;
    }
  
    .close-button {
      position: absolute;
      top: 20px;
      right: 20px;
      font-size: 3rem;
      color: white;
      background: none;
      border: none;
      cursor: pointer;
      z-index: 1002;
    }
  
    .nav-button {
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;
        top: 50%;
        transform: translateY(-50%);
        font-size: 2rem;
        background-color: rgba(128, 128, 128, 0.142);
        color: white;
        border: none;
        cursor: pointer;
        z-index: 1002;
        width: 100px;
        height: 75px;
        border-radius: 10px;
    }
  
    .nav-button.prev {
      left: 15px;
    }
  
    .nav-button.next {
      right: 15px;
    }

    .image-counter {
      position: absolute;
      bottom: 10px;
      color: white;
      font-size: 1rem;
      font-weight: 500;
      background: rgba(0, 0, 0, 0.5);
      padding: 5px 10px;
      border-radius: 5px;
      z-index: 1002;
      pointer-events: none;
    }

    @media (max-width: 768px) {
      .image-grid {
        grid-template-columns: repeat(2, 1fr);
        gap: 12px;
      }

      .close-button {
        position: absolute;
        top: 20px;
        right: 20px;
        font-size: 3rem;
        color: white;
        background: none;
        border: none;
        cursor: pointer;
        z-index: 1002;
      }
      .nav-button {
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;
        top: 50%;
        transform: translateY(-50%);
        font-size: 3rem;
        background-color: rgba(128, 128, 128, 0.142);
        color: white;
        border: none;
        cursor: pointer;
        z-index: 1002;
        width: 30px;
        height: 60px;
        border-radius: 10px;
      }
    
      .nav-button.prev {
        left: 3px;
      }
    
      .nav-button.next {
        right: 3px;
      }
    }

  </style>
  