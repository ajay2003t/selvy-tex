<template>
  <section class="image-slider">
    <div class="slider-container">
      <button class="nav-button prev" aria-label="Previous image" @click="prevSlide">
        <img
          src="https://cdn.builder.io/api/v1/image/assets/TEMP/3181379835e9b3b2bbbd323ed1435bb8ace1f0bde2e7a8567c5c87520acf8336?placeholderIfAbsent=true&apiKey=5acb37f697474270ad553272da64e56a"
          alt="" class="nav-icon-left" />
      </button>
      <div class="image-grid">
        <transition-group name="fade">
          <img v-for="(image, index) in visibleImages" :key="image.id" :src="image.src" :alt="image.alt"
            class="slider-image" :class="{ active: index === currentIndex }" />
        </transition-group>
      </div>
      <button class="nav-button next" aria-label="Next image" @click="nextSlide">
        <img
          src="https://cdn.builder.io/api/v1/image/assets/TEMP/d18d44c6e20963427cee5d44d41a33986528ac791c2c5f643202faf3b8d9d946?placeholderIfAbsent=true&apiKey=5acb37f697474270ad553272da64e56a"
          alt="" class="nav-icon-right" />
      </button>
    </div>
  </section>
</template>

<script>
import { ref, computed } from 'vue';
import { useImageSlider } from '../useImageSlider';
import i1 from '@/assets/1024logo2.png'
import i2 from '@/assets/logo1.png'
import i3 from '@/assets/logo2.png'
import i4 from '@/assets/logo3.png'
import i5 from '@/assets/logo4.png'
import i6 from '@/assets/logo5.png'
import i7 from '@/assets/logo6.png'
import i8 from '@/assets/logo7.png'
import i9 from '@/assets/logo8.png'
import i10 from '@/assets/logo9.png'
import i11 from '@/assets/logo10.png'
import i12 from '@/assets/logo11.png'
import i13 from '@/assets/logo12.png'
import i14 from '@/assets/logo13.png'
import i15 from '@/assets/logo14.png'
import i16 from '@/assets/logo15.png'
import i17 from '@/assets/logo16.png'
import i18 from '@/assets/logo17.png'
import i19 from '@/assets/logo18.png'
import i20 from '@/assets/logo19.png'
import i21 from '@/assets/logo20.png'
import i22 from '@/assets/logo21.png'
import i23 from '@/assets/logo22.png'
import i24 from '@/assets/logo23.png'
import i25 from '@/assets/logo24.png'
import i26 from '@/assets/logo25.png'
import i27 from '@/assets/logo26.png'
import i28 from '@/assets/logo27.png'
import i29 from '@/assets/logo31.png'



export default {
  name: 'ImageSlider',
  setup() {
    const images = [
      { id: 1, src: i1, alt: 'Slider image 1' },
      { id: 2, src: i2, alt: 'Slider image 2' },
      { id: 3, src: i24, alt: 'Slider image 3' },
      { id: 4, src: i23, alt: 'Slider image 4' },
      { id: 5, src: i29, alt: 'Slider image 5' },
      { id: 6, src: i6, alt: 'Slider image 6' },
      { id: 7, src: i7, alt: 'Slider image 7' },
      { id: 8, src: i8, alt: 'Slider image 8' },
      { id: 9, src: i9, alt: 'Slider image 9' },
      { id: 10, src: i10, alt: 'Slider image 10' },
      { id: 11, src: i11, alt: 'Slider image 11' },
      { id: 12, src: i12, alt: 'Slider image 12' },
      { id: 13, src: i13, alt: 'Slider image 13' },
      { id: 14, src: i14, alt: 'Slider image 14' },
      { id: 15, src: i15, alt: 'Slider image 15' },
      { id: 16, src: i16, alt: 'Slider image 16' },
      { id: 17, src: i17, alt: 'Slider image 17' },
      { id: 18, src: i18, alt: 'Slider image 18' },
      { id: 19, src: i19, alt: 'Slider image 19' },
      { id: 20, src: i20, alt: 'Slider image 20' },
      { id: 21, src: i21, alt: 'Slider image 21' },
      { id: 22, src: i22, alt: 'Slider image 22' },
      { id: 23, src: i3, alt: 'Slider image 23' },
      { id: 24, src: i4, alt: 'Slider image 24' },
      { id: 25, src: i25, alt: 'Slider image 25' },
      { id: 26, src: i26, alt: 'Slider image 26' },
      { id: 27, src: i27, alt: 'Slider image 27' },
      { id: 28, src: i28, alt: 'Slider image 28' },
      { id: 29, src: i5, alt: 'Slider image 29' },
      
    ];

    const { currentIndex, nextSlide, prevSlide } = useImageSlider(images.length);

    const visibleImages = computed(() => {
      const start = currentIndex.value;
      const end = (start + 6) % images.length;
      if (start < end) {
        return images.slice(start, end);
      } else {
        return [...images.slice(start), ...images.slice(0, end)];
      }
    });

    return {
      visibleImages,
      currentIndex,
      nextSlide,
      prevSlide,
    };
  },
};
</script>

<style scoped>
.image-slider {
  display: flex;
  flex-direction: column;
}

.slider-container {
  border-radius: 10px;
  background-color:none;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  padding: 59px 0px;
}

@media (max-width: 991px) {
  .slider-container {
    padding: 0 20px;
  }
}

.nav-button {
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  flex-basis: 10%;
}

.nav-icon {
  width: 15px;
  height: 25px;
  object-fit: contain;
}

.image-grid {
  display: flex;
  gap: 60px;
  flex-wrap:nowrap;
  flex-grow: 1;
  flex-basis: 60%;
}

.slider-image {
  width: 150px;
  height: 200px;
  object-fit: contain;
  max-width: 100%;
  transition: opacity 0.5s ease-in-out;
}



.next .nav-icon {
  width: 32px;
  height: 32px;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>