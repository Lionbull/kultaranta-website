<script lang="ts">
    import FaQuoteRight from 'svelte-icons/fa/FaQuoteRight.svelte';
    import { onMount, tick } from 'svelte';
  
    let currentIndex = 0;
    let interval: any;
  
    const reviews = [
      { text: "Hyperframe is a Wireframe Kit for Figma enabling you to create the prototype of your website, blog, landing page or a web app in the shortest time. The Wireframe Kit includes 150+ ready screens in 14 categories covering almost all spheres of software development.", name: "John Doe", source: "Google" },
      { text: "Hyperframe is a Wireframe Kit for Figma enabling you to create the prototype of your website, blog, landing page or a web app in the shortest time. The Wireframe Kit includes 150+ ready screens in 14 categories covering almost all spheres of software development.", name: "Jane Smith", source: "TripAdvisor" },
      { text: "Hyperframe is a Wireframe Kit for Figma enabling you to create the prototype of your website, blog, landing page or a web app in the shortest time. The Wireframe Kit includes 150+ ready screens in 14 categories covering almost all spheres of software development.", name: "Alice Johnson", source: "Yelp" },
      { text: "Hyperframe is a Wireframe Kit for Figma enabling you to create the prototype of your website, blog, landing page or a web app in the shortest time. The Wireframe Kit includes 150+ ready screens in 14 categories covering almost all spheres of software development.", name: "Alice Johnson", source: "Yelp" },
      { text: "Hyperframe is a Wireframe Kit for Figma enabling you to create the prototype of your website, blog, landing page or a web app in the shortest time. The Wireframe Kit includes 150+ ready screens in 14 categories covering almost all spheres of software development.", name: "Alice Johnson", source: "Yelp" },
    ];
  
    function startCarousel() {
      interval = setInterval(() => {
        nextSlide();
      }, 5000);
    }
  
    function resetInterval() {
      clearInterval(interval);
      startCarousel();
    }
  
    function nextSlide() {
      currentIndex = (currentIndex + 1) % reviews.length;
      resetInterval();
    }
  
    function prevSlide() {
      currentIndex = (currentIndex - 1 + reviews.length) % reviews.length;
      resetInterval();
    }
  
    function goToSlide(index: number) {
      currentIndex = index;
      resetInterval();
    }
  
    onMount(() => {
      startCarousel();
      return () => clearInterval(interval);
    });
  </script>
  
  <div class="carousel-container">
    <button class="nav-button prev" on:click={prevSlide}>❮</button>
    <div class="carousel">
      {#each reviews as review, index (index)}
        <div class="card" style="
          transform: translateX({(index - currentIndex) * 100}%) scale({currentIndex === index ? 1 : 0.8});
          opacity: {index === currentIndex ? 1 : (index === currentIndex - 1 || index === currentIndex + 1) ? 0.5 : 0};
          z-index: {(currentIndex === index) ? 1 : (index === currentIndex - 1 || index === currentIndex + 1) ? 0 : -1};
        ">
          <div class="quote"><FaQuoteRight /></div>
          <div class="review-text">{review.text}</div>
          <div class="reviewer-name">{review.name}</div>
          <div class="review-source">{review.source}</div>
        </div>
      {/each}
    </div>
    <div class="indicators">
        {#each reviews as _, index}
          <div
            class="indicator"
            class:selected={currentIndex === index}
            on:click={() => goToSlide(index)}
          ></div>
        {/each}
      </div>
    <button class="nav-button next" on:click={nextSlide}>❯</button>
  </div>
  
  <style>
    .carousel-container {
      position: relative;
      width: 100%;
      height: 400px;
      margin: 50px 0;
    }
  
    .carousel {
      display: flex;
      overflow: hidden;
      position: relative;
      width: 100%;
      justify-content: center;
      align-items: center;
      height: 100%;
    }
  
    .card {
      height: 250px;
      width: 450px;
      flex: 0 0 70%;
      max-width: 70%;
      transition: transform 0.5s, opacity 0.5s;
      position: absolute;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      background: white;
      padding: 1.5rem 3rem;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.15);
      border: 1px solid rgba(0, 0, 0, 1);
      border-radius: 10px;
      line-height: 25px;
    }
  
    .quote {
      width: 20px;
      height: 20px;
      color: black;
    }
  
    .review-text {
      margin: 1rem 0;
    }
  
    .reviewer-name {
      font-weight: bold;
    }
  
    .review-source {
      color: gray;
    }
  
    .nav-button {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      background: rgba(0, 0, 0, 0.5);
      color: white;
      border: none;
      padding: 1rem;
      cursor: pointer;
      z-index: 2;
    }
  
    .nav-button.prev {
      left: 10px;
    }
  
    .nav-button.next {
      right: 10px;
    }
  
    .indicators {
      display: flex;
      justify-content: center;
    }
  
    .indicator {
      width: 12px;
      height: 12px;
      background: gray;
      border-radius: 50%;
      margin: 0 5px;
      cursor: pointer;
    }
  
    .indicator.selected {
      background: black;
    }
  </style>
  