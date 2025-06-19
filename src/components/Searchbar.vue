<template>
  <div class="search-header">
    <div class="search-bar">
      <div class="location-input fade-in-up">
        <input type="text" class="location-text" placeholder="Search" value="Austin, Tx" />
        <div class="icons">
          <button class="clear-btn">&times;</button>
          <button class="search-btn">
            <img src="/assets/icons/searchIcon.svg" alt="Search" />
          </button>
        </div>
      </div>
      <button class="setting-btn">
        <img src="/assets/icons/setting.svg" alt="Settings" />
      </button>
    </div>

    <div class="filters fade-in-up">
      <select class="dropdown-select">
        <option value="sale">For Sale</option>
        <option value="sold">Sold</option>
      </select>

      <select class="dropdown-select">
        <option value="Price">Price</option>
        <option value="$10000-$20000">$10000-$20000</option>
        <option value="$20000-$30000">$20000-$30000</option>
        <option value="$30000-$40000">$30000-$40000</option>
      </select>

      <button class="saved">&#9998; Saved</button>
      <button class="save-search">Save Search</button>
    </div>
  </div>
</template>

<script>
document.addEventListener("DOMContentLoaded", () => {
  const input = document.querySelector(".location-text");
  const clear = document.querySelector(".clear-btn");

  const toggleClearButton = () => {
    clear.classList.toggle("show", input.value !== "");
  };

  toggleClearButton();

  input.addEventListener("input", toggleClearButton);

  clear.addEventListener("click", () => {
    input.value = "";
    toggleClearButton();
    input.focus();
  });
});
</script>

<style scoped>
.search-header {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: baseline;
  gap: 1rem;
  position: sticky;
  padding: 1rem 2rem;
  background-color: white;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.06);
  top: 0;
  z-index: 100;
}

.search-bar {
  display: flex;
  align-items: center;
  flex: 1 1 auto;
  gap: 10px;
  max-width: 500px;
}

.location-input {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 8px 12px;
  background-color: #f7f9fb;
  border-radius: 9999px;
  flex: 1;
  max-width: 500px;
  gap: 10px;
}

.location-input:focus-within {
  border: 1px solid #0d61a8;
  background-color: #0d62a80f;
}

.location-text {
  border: none;
  outline: none;
  background: transparent;
  font-weight: 600;
  color: #000;
  font-size: 14px;
  flex: 1;
  min-width: 0;
}

.icons {
  display: flex;
  gap: 10px;
}

.clear-btn {
  background: none;
  border: none;
  color: #999;
  font-size: 24px;
  cursor: pointer;
  visibility: hidden;
}

.clear-btn.show {
  visibility: visible;
}

.search-btn {
  background-color: #0d61a8;
  border: none;
  border-radius: 50%;
  padding: 6px;
  width: 40px;
  height: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  flex-shrink: 0;
}

.setting-btn {
  display: none;
  background-color: white;
  border: 1px solid #0d61a8;
  border-radius: 50%;
  padding: 6px;
  width: 3rem;
  height: 3rem;
  color: #0d61a8;
  cursor: pointer;
  align-items: center;
  justify-content: center;
}

@media (max-width: 730px) {
  .setting-btn {
    display: flex;
  }
}

.filters {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  min-width: 10px;
  max-width: fit-content;
  margin-left: 0;
}

.dropdown-select {
  padding: 8px 12px;
  border: 1px solid #ccc;
  border-radius: 10px;
  background-color: #fff;
  font-weight: 500;
  color: #333;
  padding-right: 32px;
  background-repeat: no-repeat;
  background-position: right 12px center;
  background-size: 12px;
  appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg fill='black' viewBox='0 0 24 24' width='18' height='18' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M7 10l5 5 5-5z'/%3E%3C/svg%3E");
  transition: border-color 0.3s ease;
}

.dropdown-select:focus {
  border: 2px solid #0d61a8;
  font-weight: 600;
  color: #0d61a8;
  outline: none;
  box-shadow: none;
}

.dropdown-select:hover {
  border-color: #0d61a8;
}

.filters .saved {
  padding: 0.5rem 1rem;
  border: 1px solid #ddd;
  background-color: #fff;
  border-radius: 2rem;
  cursor: pointer;
  transition: border-color 0.3s ease;
}

.saved:hover {
  border-color: #0d61a8;
}

.save-search {
  padding: 0.5rem 1rem;
  border: none;
  color: white;
  background-color: #0d61a8;
  border-radius: 2rem;
  cursor: pointer;
  display: none;
  transition: border-color 0.3s ease;
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

@media (max-width: 530px) {
  .saved {
    display: none;
  }

  .save-search {
    display: block;
    font-size: 10px;
    width: 6rem;
    padding: 9px 12px;
  }

  .search-bar {
    width: 100%;
  }

  .location-input {
    width: 10px;
  }

  .dropdown-select {
    font-size: 10px;
    width: 6rem;
  }
}
</style>
