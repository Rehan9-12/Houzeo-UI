<template>
  <div class="listings-grid">
    <h2 class="heading fade-in-up">Austin, TX real estate & homes for sale</h2>

    <div class="search-result">
      <p class="subheading fade-in-up fade-delay-1">2,010 Homes</p>
      <p class="subheading fade-in-up fade-delay-1">
        Sort by:
        <select class="sort">
          <option value="Listing">Listing</option>
          <option value="Price">Price</option>
        </select>
      </p>
    </div>

    <div class="grid-container">
      <ListingCard v-for="(listing, index) in listings" :key="index" :listing="listing" />
    </div>
  </div>
</template>

<script>
import ListingCard from './ListingCard.vue';

export default {
  name: 'ListingsGrid',
  components: { ListingCard },
  data() {
    return {
      listings: [
        {
          images: [
            '/assets/properties/house1.png',
            '/assets/properties/house2.png',
            '/assets/properties/house3.png'
          ],
          daysOn: '06 days on Houzeo',
          tag: 'House For Sale',
          views: '2.5k',
          price: '$2,349,000',
          beds: 4,
          baths: 3,
          sqft: 1229,
          street: '2856 Meadow Park Ave,',
          city: 'Henderson, NV 89052',
          agency: 'Nashville (Real Tracs Mid) MLS-TN',
          liked: false
        },
        {
          images: [
            '/assets/properties/house2.png',
            '/assets/properties/house1.png',
            '/assets/properties/house3.png'
          ],
          daysOn: '10 days on Houzeo',
          tag: 'Condo For Sale',
          views: '3.0k',
          price: '$3,209,000',
          beds: 9,
          baths: 3,
          sqft: 1229,
          street: '2856 Meadow Park Ave,',
          city: 'Henderson, NV 89052',
          agency: 'Nashville (Real Tracs Mid) MLS-TN',
          liked: false
        },
        {
          images: [
            '/assets/properties/house3.png',
            '/assets/properties/house2.png',
            '/assets/properties/house1.png'
          ],
          daysOn: '10 days on Houzeo',
          tag: 'House For Sale',
          views: '2.5k',
          price: '$4,349,000',
          beds: 4,
          baths: 3,
          sqft: 1229,
          street: '2856 Meadow Park Ave,',
          city: 'Henderson, NV 89052',
          agency: 'Nashville (Real Tracs Mid) MLS-TN',
          liked: false
        },
        {
          images: [
            '/assets/properties/house1.png',
            '/assets/properties/house2.png',
            '/assets/properties/house3.png'
          ],
          daysOn: '06 days on Houzeo',
          tag: 'House For Sale',
          views: '2.5k',
          price: '$2,349,000',
          beds: 4,
          baths: 3,
          sqft: 1229,
          street: '2856 Meadow Park Ave,',
          city: 'Henderson, NV 89052',
          agency: 'Nashville (Real Tracs Mid) MLS-TN',
          liked: false
        },
        {
          images: [
            '/assets/properties/house2.png',
            '/assets/properties/house1.png',
            '/assets/properties/house3.png'
          ],
          daysOn: '10 days on Houzeo',
          tag: 'Condo For Sale',
          views: '3.0k',
          price: '$3,209,000',
          beds: 9,
          baths: 3,
          sqft: 1229,
          street: '2856 Meadow Park Ave,',
          city: 'Henderson, NV 89052',
          agency: 'Nashville (Real Tracs Mid) MLS-TN',
          liked: false
        },
        {
          images: [
            '/assets/properties/house3.png',
            '/assets/properties/house2.png',
            '/assets/properties/house1.png'
          ],
          daysOn: '10 days on Houzeo',
          tag: 'House For Sale',
          views: '2.5k',
          price: '$4,349,000',
          beds: 4,
          baths: 3,
          sqft: 1229,
          street: '2856 Meadow Park Ave,',
          city: 'Henderson, NV 89052',
          agency: 'Nashville (Real Tracs Mid) MLS-TN',
          liked: false
        },
      ]
    };
  }
};
</script>

<style scoped>
.listings-grid {
  flex: 1;
  padding: 1rem 1.5rem;
  overflow-y: auto;
  background-color: #ffffff;
  color: black;
  width: 50%;
  height: auto;
  z-index: 10;
}

.heading {
  font-size: 1.2rem;
  font-weight: 700;
}

@media (max-width: 410px) {
  .heading {
    font-size: 1rem;
  }
}

.search-result {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.subheading {
  font-size: 0.875rem;
  color: #6b7280;
  margin-bottom: 1rem;
}

.sort {
  font-weight: 500;
  color: #0d61a8;
  border: none;
  background-color: transparent;
}

.sort:active {
  border: none;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1.25rem;
}

@media (max-width: 1100px) {
  .grid-container {
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  }
}

@media (max-width: 850px) {
  .grid-container {
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  }
}

/* Hide scrollbar for all browsers */
::-webkit-scrollbar {
  display: none;
}

body {
  scrollbar-width: none;
  -ms-overflow-style: none;
}

/* Animation */
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

.fade-delay-1 {
  animation-delay: 0.2s;
}
</style>
