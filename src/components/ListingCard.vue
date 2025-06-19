<template>
  <div class="card fade-in-up fade-delay-2">
    <div
      class="image-container"
      @mouseenter="showControls = true"
      @mouseleave="showControls = false"
    >
      <img
        :src="listing.images[currentImageIndex]"
        alt="House"
        class="card-img"
        loading="lazy"
      />

      <button v-if="showControls" class="nav-arrow left" @click="prevImage">&#10094;</button>
      <button v-if="showControls" class="nav-arrow right" @click="nextImage">&#10095;</button>

      <div v-if="showControls" class="bullets">
        <span
          v-for="(img, i) in listing.images"
          :key="i"
          :class="['bullet', { active: i === currentImageIndex }]"
          @click="goToImage(i)"
        ></span>
      </div>

      <span class="days">{{ listing.daysOn }}</span>
      <button class="like-btn">
        <img src="/src/assets/icons/heart.svg" alt="" />
      </button>
    </div>

    <div class="card-body">
      <div class="current-info">
        <span class="tag">
          <div class="dot"></div>{{ listing.tag }}
        </span>
        <p class="count">&#128065; {{ listing.views }}</p>
      </div>

      <div class="property-info">
        <div class="price">{{ listing.price }}</div>
        <div class="details">
          <span><span class="highlighted-text">{{ listing.beds }}</span> Beds</span>
          <span><span class="highlighted-text">{{ listing.baths }}</span> Baths</span>
          <span><span class="highlighted-text">{{ listing.sqft }}</span> sqft</span>
        </div>
      </div>

      <div class="address">
        <span class="street">{{ listing.street }}</span>
        <span class="city">{{ listing.city }}</span>
      </div>

      <div class="agency">{{ listing.agency }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ListingCard',
  props: {
    listing: Object
  },
  data() {
    return {
      currentImageIndex: 0,
      showControls: false
    };
  },
  methods: {
    nextImage() {
      this.currentImageIndex = (this.currentImageIndex + 1) % this.listing.images.length;
    },
    prevImage() {
      this.currentImageIndex =
        (this.currentImageIndex - 1 + this.listing.images.length) % this.listing.images.length;
    },
    goToImage(index) {
      this.currentImageIndex = index;
    }
  }
};
</script>

<style scoped>
.card {
  background-color: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.134);
  transition: box-shadow 0.3s ease-in-out, transform 0.3s ease;
}
.card:hover {
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
  transform: translateY(-3px);
}

.image-container {
  position: relative;
}
.image-container:hover .card-img {
  transform: scale(1.03);
}

.card-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease-in-out;
}

.nav-arrow {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  border: none;
  background: transparent;
  color: white;
  font-size: 1.5rem;
  cursor: pointer;
  padding: 4px 10px;
  z-index: 2;
  border-radius: 50%;
  transition: background 0.3s;
}
.nav-arrow:hover {
  background: rgba(255, 255, 255, 0);
}
.nav-arrow.left {
  left: 10px;
}
.nav-arrow.right {
  right: 10px;
}

.bullets {
  position: absolute;
  bottom: 8px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  gap: 5px;
}
.bullet {
  width: 8px;
  height: 8px;
  background: rgba(255, 255, 255, 0.7);
  border-radius: 50%;
  cursor: pointer;
  transition: background 0.3s;
}
.bullet.active {
  background: #0d61a8;
}

.days {
  position: absolute;
  top: 13px;
  left: 15px;
  font-weight: 500;
  background: white;
  padding: 2px 8px;
  font-size: 0.75rem;
  border-radius: 10px;
}

.like-btn {
  position: absolute;
  top: 13px;
  right: 14px;
  border: none;
  background: none;
  font-size: 1rem;
  cursor: pointer;
}
:deep(.like-btn:hover) {
  animation: pulse 0.6s ease;
}

.card-body {
  padding: 12px;
  padding-top: 7px;
}

.current-info {
  display: flex;
  justify-content: space-between;
  padding-right: 2px;
}

.tag {
  display: flex;
  align-items: center;
  gap: 5px;
  padding: 1px 5px;
  border: 0.3px solid rgb(147, 147, 147);
  border-radius: 10px;
  font-size: 0.75rem;
  color: #000;
  margin-bottom: 0.25rem;
  width: max-content;
}

.dot {
  height: 10px;
  width: 10px;
  background-color: #10b981;
  border-radius: 50%;
}

.price {
  font-size: 1.1rem;
  font-weight: 600;
  color: #0d61a8;
  margin: 0.2rem;
}

.property-info {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  align-items: center;
}

.details {
  display: flex;
  gap: 10px;
  font-size: 1rem;
  color: #374151;
}

.highlighted-text {
  font-size: 1.1rem;
  font-weight: 600;
  color: #0d61a8;
}

.street {
  font-size: 0.85rem;
  font-weight: 500;
  color: black;
}

.city {
  font-size: 0.8rem;
  color: rgb(89, 89, 89);
}

.agency {
  font-size: 0.75rem;
  color: #6b7280;
}

.fade-in-up {
  opacity: 0;
  transform: translateY(30px);
  animation: fadeInUp 0.6s ease-out forwards;
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.3);
  }
  100% {
    transform: scale(1);
  }
}

.fade-delay-2 {
  animation-delay: 0.4s;
}
</style>
