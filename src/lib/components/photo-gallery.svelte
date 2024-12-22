<script lang="ts">
    import { base } from "$app/paths";

    let currentIndex = -1; // Index of the currently viewed image
    const images = [
      `${base}/area-photo-1.jpg`,
      `${base}/area-photo-2.jpg`,
      `${base}/area-photo-3.jpg`,
      `${base}/area-photo-4.jpg`,
      `${base}/area-photo-5.jpg`,
      `${base}/area-photo-6.jpg`,
      `${base}/area-photo-7.jpg`,
      `${base}/area-photo-8.jpg`,
    ];
  
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
  
  <div class="image-grid">
        {#each images as image, index}
            <!-- svelte-ignore a11y-no-static-element-interactions -->
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <div class="image-container" on:click={() => openImage(index)}>
                <img src={image} alt="kultaranta area" loading="lazy" />
            </div>
        {/each}
  </div>
  
  {#if currentIndex !== -1}
        <div class="modal">
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <!-- svelte-ignore a11y-no-static-element-interactions -->
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
      padding: 0 120px;
      margin: 0 0 100px 0;
    }
  
    .image-container {
      position: relative;
      width: 100%;
      aspect-ratio: 1 / 1;
      overflow: hidden;
      border-radius: 8px;
      cursor: pointer;
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
      height: 100vh;
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
      object-fit: contain; /* Ensures the full image is displayed */
      border-radius: 8px;
      z-index: 1001;
    }
  
    .close-button {
      position: absolute;
      top: 20px;
      right: 20px;
      font-size: 2rem;
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
  </style>
  