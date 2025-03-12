<template>
  <!-- Navbar -->
  <nav class="sticky top-0 left-0 w-full bg-blue-900 bg-opacity-90 backdrop-blur-md z-50 shadow-md">
    <div class="container mx-auto flex justify-between items-center p-4 flex-wrap">
      
      <!-- Logo & Social Icons -->
      <div class="flex items-center space-x-4">
        <h1 class="text-xl font-bold text-white cursor-pointer"> <a @click="goToHome">COACH ONLINE</a> </h1>
        <div class="hidden md:flex space-x-3">
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-facebook-f"></i></a>
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-x-twitter"></i></a>
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-linkedin-in"></i></a>
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-instagram"></i></a>
        </div>
      </div>

      <!-- Mobile Menu Button -->
      <button @click="toggleMenu" class="md:hidden text-white focus:outline-none text-2xl">
        <i class="fas fa-bars"></i>
      </button>

      <!-- Navigation Links -->
      <div :class="{'hidden': !menuOpen, 'flex': menuOpen}" class="md:flex md:items-center md:space-x-6 w-full md:w-auto mt-4 md:mt-0">
        <ul class="flex flex-col md:flex-row md:space-x-4 items-center w-full md:w-auto">
          <li><a @click="goToHome" class="nav-link active cursor-pointer">Home</a></li>
          <li class="relative group">
            <a href="#" class="nav-link flex items-center cursor-pointer">
              Blog <i class="fas fa-chevron-down ml-1"></i>
            </a>
            <ul class="md:absolute left-0 hidden group-hover:block bg-blue-800 text-white mt-2 rounded shadow-lg w-40 py-2">
              <li><a href="#" class="block px-4 py-2 hover:bg-blue-700">For Individuals</a></li>
              <li><a href="#" class="block px-4 py-2 hover:bg-blue-700">For Business</a></li>
            </ul>
          </li>
          <li><a href="#" class="nav-link">Shop</a></li>
          <li><a @click="goToContact" class="nav-link cursor-pointer">Contact</a></li>

        </ul>
        
        <!-- Search & Cart Icons -->
        <div class="flex space-x-3 mt-4 md:mt-0">
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fas fa-shopping-cart"></i></a>
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fas fa-search"></i></a>
        </div>
      </div>

    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      menuOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
   goToContact() {
  navigateTo('/contact', { external: false });
},
goToHome() {
  navigateTo('/', { external: false });
}
  },
};
</script>

<style scoped>
.nav-link {
  position: relative;
  padding: 8px 16px;
  font-size: 1rem;
  text-transform: uppercase;
  font-weight: 700;
  border-radius: 8px;
  transition: all 0.3s ease-in-out;
  color: white;
  display: block;
}

.nav-link::after {
  content: "";
  position: absolute;
  left: 50%;
  bottom: -2px;
  width: 0;
  height: 2px;
  background: white;
  transition: all 0.3s ease-in-out;
  transform: translateX(-50%);
}

.nav-link:hover::after, .nav-link.active::after {
  width: 100%;
}
</style>
