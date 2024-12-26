<script lang="ts">
    import FaQuoteRight from 'svelte-icons/fa/FaQuoteRight.svelte';
    import { onMount, tick } from 'svelte';
  
    let currentIndex = 0;
    let interval: any;
  
    const reviews = [
      { text: "We loved staying at this place. Beautiful calm surroundings and the house had everything we needed. It was also very nice to use the grill spots and the rowing boats and we even rented sups. The host is also very friendly. I think this is one of my favourite places I ever stayed at.", name: "Eva, Belgium", source: "Booking.com" },
      { text: "Great location, nice quiet place. A good beach with chairs, toys for kids and boats to use free of charge. Communication with the owner was easy and without problems. Sauna, fireplace, amazing view, privacy.", name: "Jaroslav, Czech Republic", source: "Booking.com" },
      { text: "Peaceful location, beach close to the cabin, facilities more than adequate for 5 people, clean and tidy, it was nice to have 3 separate bedrooms. Explored the sights and environment a lot, beautiful lakes, trails etc. The staff was really helpful.", name: "Elisa, Finland", source: "Booking.com" },
      { text: "Location was perfect and very peaceful. There was a pier to jump off from and also a little beach. There were also boats you could take to go into the lake. It’s very close to Puumala by car, where there are supermarkets and restaurants. Overall 10/10.", name: "Myrsini, Cyprus", source: "Booking.com" },
      { text: "The host was a very kind person and she did everything possible to make us feel welcome and help us have a comfortable stay. We had to change cottage during our stay due to lack of availability of the same cottage when we did the reservation, and she helped...", name: "Slowcoffee, Finland", source: "Booking.com" },
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

    let startX: number;
    let endX: number;

    function handleTouchStart(event: TouchEvent) {
      startX = event.touches[0].clientX;
    }

    function handleTouchMove(event: TouchEvent) {
      endX = event.touches[0].clientX;
    }

    function handleTouchEnd() {
      if (startX - endX > 50) {
          nextSlide(); // Swipe left
      } else if (endX - startX > 50) {
          prevSlide(); // Swipe right
      }
    }
  
    onMount(() => {
      startCarousel();
      return () => clearInterval(interval);
    });
  </script>
  
  <div class="content-section" id="reviews">
    <h1>Reviews</h1>
    <div
        class="carousel-container"
        on:touchstart={handleTouchStart}
        on:touchmove={handleTouchMove}
        on:touchend={handleTouchEnd}
    >
        <div class="carousel">
            {#each reviews as review, index (index)}
                <div
                    class="card"
                    style="
                        transform: translateX({(index - currentIndex) * 100}%) scale({currentIndex === index ? 1 : 0.8});
                        opacity: {index === currentIndex ? 1 : (index === currentIndex - 1 || index === currentIndex + 1) ? 0.5 : 0};
                        z-index: {(currentIndex === index) ? 1 : (index === currentIndex - 1 || index === currentIndex + 1) ? 0 : -1};
                    "
                >
                    <div class="quote"><FaQuoteRight /></div>
                    <div class="review-text">{review.text}</div>
                    <div class="reviewer-name">{review.name}</div>
                    <div
                        class="review-source"
                        style="cursor: {currentIndex === index ? 'pointer' : 'default'};"
                        on:click={() => currentIndex === index ? window.open(`https://www.booking.com/hotel/fi/saimaan-kultaranta.html#tab-reviews`, "_blank") : null}
                    >
                        {review.source}
                    </div>
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
    </div>
</div>
  
  <style lang="scss">

    .content-section {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 20px;
      box-sizing: border-box;
      margin: 0 0 100px 0;

      h1 {
        margin: 0;
      }
    }
    
    .carousel-container {
      position: relative;
      width: 100%;
      height: 460px;
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
      height: 300px;
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
      text-decoration: underline;
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
      left: 20px;
    }
  
    .nav-button.next {
      right: 20px;
    }
  
    .indicators {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 10px;
      height: 15px;
    }
  
    .indicator {
      width: 12px;
      height: 12px;
      background: white;
      border-radius: 50%;
      border: 1px solid #687058;
      cursor: pointer;
    }
  
    .indicator.selected {
      background: #687058;
    }

    @media (max-width: 768px) {

      .content-section {
        margin: 0 0 80px 0;
        h1 {
          margin: 0;
        }
      }
      .carousel-container {
        height: 375px;
      }

      .card {
        height: 325px;
        width: 300px;
        padding: 1rem 2rem;
      }

      .quote {
        width: 15px;
        height: 15px;
      }

      .nav-button {
        display: none;
      }

      .nav-button.prev {
        left: 10px;
      }

      .nav-button.next {
        right: 10px;
      }

      .indicators {
        margin-top: 10px;
        gap: 5px;
      }

      .indicator {
        width: 12px;
        height: 12px;
      }

      .carousel-container {
        touch-action: pan-x; /* Allow horizontal swiping */
      }
    }
  </style>
  