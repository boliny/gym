<template>
  <!-- Navbar -->
  <nav class="sticky top-0 left-0 w-full bg-blue-900 bg-opacity-80 backdrop-blur-md z-50 shadow-md">
    <div class="container mx-auto flex justify-between items-center p-4">
      
      <!-- Logo & Social Icons -->
      <div class="flex items-center space-x-6">
        <h1 class="text-xl font-bold text-white">COACH ONLINE GYM</h1>
        <div class="flex space-x-3">
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-facebook-f"></i></a>
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-x-twitter"></i></a>
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-linkedin-in"></i></a>
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fab fa-instagram"></i></a>
        </div>
      </div>

      <!-- Navigation Links & Search/Cart Icons -->
      <div class="flex items-center space-x-6">
        <ul class="flex space-x-4 items-center">
          <li><a href="#" class="nav-link active">Home</a></li>
          <li class="relative group">
            <a href="#" class="nav-link flex items-center cursor-pointer">
              Blog <i class="fas fa-chevron-down ml-1"></i>
            </a>
            <ul class="absolute left-0 hidden group-hover:block bg-blue-800 text-white mt-2 rounded shadow-lg w-40 py-2">
              <li><a href="#" class="block px-4 py-2 hover:bg-blue-700">For Individuals</a></li>
              <li><a href="#" class="block px-4 py-2 hover:bg-blue-700">For Business</a></li>
            </ul>
          </li>
          <li><a href="#" class="nav-link">Shop</a></li>
          <li><a href="#" class="nav-link">Contact</a></li>
        </ul>
        
        <!-- Search & Cart Icons -->
        <div class="flex space-x-3">
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fas fa-shopping-cart"></i></a>
          <a href="#" class="text-gray-300 hover:text-white transition"><i class="fas fa-search"></i></a>
        </div>
      </div>

    </div>
  </nav>
</template>

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