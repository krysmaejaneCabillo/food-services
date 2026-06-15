<script>
export default {
    props: {
        orderCount: {
            type: Number,
            default: 0
        }
    },
    data() {
        return {
            isCategoryOpen: false,
            isMobileMenuOpen: false,
            activePage: 'Home',
             searchBar: ''
        }
    },
    methods: {
        // loginBtn() {
        //     this.$emit('show')
        // },
        // registerBtn() {
        //     this.$emit('register')
        // },
        navigate(page) {
            this.$emit('goTo', page)
            this.activePage = page

        },
         search() {
            this.$emit('search-bar', this.searchBar)
        },
    }



}
</script>

<template>
    <nav class="w-full bg-gray-50 border-b border-gray-200 shadow-sm sticky top-0 z-50 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <!-- Top Bar: Logo + Search + Icons -->
            <div class="flex items-center justify-between h-16 gap-3 md:gap-4">
                <!-- Brand Name-->
                <a href="/" class="flex-shrink-0">
                    <span
                        class="text-[clamp(1.6rem,3vw,2rem)] font-bold bg-gradient-to-r from-black to-red-700 bg-clip-text text-transparent hover:from-red-700 hover:to-black transition-all duration-300">
                        Tasty Bites
                    </span>

                </a>

                <!-- Category Dropdown -->
                <div class="hidden md:block relative">
                    <button @click="isCategoryOpen = !isCategoryOpen"
                        class="flex items-center gap-1.5 px-3 py-2 text-sm font-medium text-gray-700 hover:text-red-600 hover:bg-white rounded-md transition-all">
                        Shop by Category
                        <svg class="w-4 h-4 transition-transform duration-200" :class="{ 'rotate-180': isCategoryOpen }"
                            fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                        </svg>
                    </button>

                    <!-- Category Menu -->
                    <transition class="transition ease-out duration-200">
                        <div v-if="isCategoryOpen"
                            class="absolute left-0 z-50 mt-1 w-56 bg-white rounded-lg shadow-lg border border-gray-100 py-2">
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">Pork
                            </a>
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">Beef
                            </a>
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">Chicken
                            </a>
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">Seafood
                            </a>
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">
                                Pasta
                            </a>
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">
                                Salad Greens
                            </a>
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">
                                Soup
                            </a>
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">
                                Starch
                            </a>
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">
                                Merienda
                            </a>
                            <a href=""
                                class="block px-4 py-2.5 text-sm text-red-700 hover:bg-red-50 hover:text-red-600">
                                Cakes
                            </a>
                        </div>
                    </transition>
                </div>

                <!-- Search Bar -->
                <div class="flex-1 w-full max-w-2xl hidden sm:flex items-center">
                    <div class="relative w-full flex">
                        <input v-model="searchBar" @input="search" type="text" placeholder="Search for anything..."
                            class="w-full px-4 py-2.5 rounded-l-lg border border-red-300 focus:outline-none focus:ring-1 focus:ring-red-900/40 focus:border-red-500 bg-white transition-all" />
                        <button
                            class="px-5 bg-gradient-to-r from-black to-red-700 text-white rounded-r-lg hover:from-red-700 hover:to-black transition-all duration-300">
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                    d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
                            </svg>
                        </button>
                    </div>
                </div>

                <!-- Right Side Icons/Links -->
                <div class="hidden md:flex items-center gap-5 text-sm font-medium text-gray-700">
                    <a @click="loginBtn" href="#" class="hover:text-red-600 transition-colors">Sign In</a>
                    <a @click="registerBtn" href="#" class="hover:text-red-600 transition-colors">Register</a>
                    <a @click="navigate('Help')" href="#" class="hover:text-red-600 transition-colors">Help</a>
                    <a @click="navigate('Orders')" href="#"
                        class="relative p-2 hover:bg-white rounded-full transition-all "
                        :class="activePage === 'Orders' ? 'underline underline-offset-6 decoration-red-800 text-red-800 font-bold' : 'bg-none'">
                        <svg class=" w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.29 2.29c-.63.63-.18 1.71.71 1.71H17" />
                        </svg>
                        <span
                            class="absolute -top-1 -right-1 bg-red-500 text-white text-[10px] font-bold rounded-full w-5 h-5 flex items-center justify-center shadow-sm">{{ orderCount }}</span>
                    </a>
                </div>

                <!-- Mobile Menu Button -->
                <button @click="isMobileMenuOpen = !isMobileMenuOpen"
                    class="md:hidden text-gray-700 hover:text-red-600 transition-colors" aria-label="Toggle menu">
                    <svg v-if="!isMobileMenuOpen" class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M4 6h16M4 12h16M4 18h16" />
                    </svg>
                    <svg v-else class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                            d="M6 18L18 6M6 6l12 12" />
                    </svg>
                </button>
            </div>

            <!-- Mobile Search Bar -->
            <div class="sm:hidden py-3">
                <div class="relative w-full flex">
                    <input v-model="searchBar" @input="search" type="text" placeholder="Search products, categories..."
                        class="w-full px-4 py-2 rounded-l-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-blue-500/40 focus:border-blue-500 bg-white" />
                    <button
                        class="px-4 bg-gradient-to-r from-black to-red-700 text-white rounded-r-lg hover:from-indigo-700 hover:to-blue-600 transition-all">
                        <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
                        </svg>
                    </button>
                </div>
            </div>

            <!-- Secondary Navigation Bar -->
            <div class="hidden md:flex items-center h-10 text-sm font-medium border-t border-gray-200/70">
                <p @click="navigate('Home')"
                    class="px-3 py-1.5 hover:text-red-600 hover:underline underline-offset-6 transition-all cursor-pointer"
                    :class="activePage === 'Home' ? 'underline underline-offset-6 decoration-red-800 text-red-800 font-bold' : 'bg-none'">
                    Home</p>
                <p @click="navigate('About')"
                    class="px-3 py-1.5 hover:text-red-600 hover:underline underline-offset-6 transition-all cursor-pointer"
                    :class="activePage === 'About' ? 'underline underline-offset-6 decoration-red-800 text-red-800 font-bold' : 'bg-none'">
                    About Us</p>
                <p @click="navigate('Card')"
                    class="px-3 py-1.5 hover:text-red-600 hover:underline underline-offset-6 transition-all cursor-pointer"
                    :class="activePage === 'Card' ? 'underline underline-offset-6 decoration-red-800 text-red-800 font-bold' : 'bg-none'">
                    Note Card</p>
                <p @click="navigate('Contact')"
                    class="px-3 py-1.5 hover:text-red-600 hover:underline underline-offset-6 transition-all cursor-pointer"
                    :class="activePage === 'Contact' ? 'underline underline-offset-6 decoration-red-800 text-red-800 font-bold' : 'bg-none'">
                    Contact us</p>
                <p @click="navigate('Orders')"
                    class="px-3 py-1.5 hover:text-red-600 hover:underline underline-offset-6 transition-all cursor-pointer"
                    :class="activePage === 'Orders' ? 'underline underline-offset-6 decoration-red-800 text-red-800 font-bold' : 'bg-none'">
                    Orders</p>
            </div>
        </div>

        <!-- Mobile Menu -->
        <transition class="transition-all duration-300 ease-out">
            <div v-if="isMobileMenuOpen" class="md:hidden bg-white border-t border-gray-200 shadow-md">
                <div class="px-3 py-4 space-y-2">
                    <p @click="navigate('Home')"
                        class="block px-3 py-2.5 rounded-md text-base font-medium text-gray-700 hover:bg-blue-50 hover:text-blue-600">
                        Home</p>

                    <p @click="navigate('About')"
                        class="block px-3 py-2.5 rounded-md text-base font-medium text-gray-700 hover:bg-blue-50 hover:text-blue-600">
                        About Us</p>
                    <p @click="navigate('Card')"
                        class="block px-3 py-2.5 rounded-md text-base font-medium text-gray-700 hover:bg-blue-50 hover:text-blue-600">
                        Note Card</p>
                    <p @click="navigate('Contact')"
                        class="block px-3 py-2.5 rounded-md text-base font-medium text-gray-700 hover:bg-blue-50 hover:text-blue-600">
                       Contact Us</p>
                    <p @click="navigate('FAQ')"
                        class="block px-3 py-2.5 rounded-md text-base font-medium text-gray-700 hover:bg-blue-50 hover:text-blue-600">
                        FAQ
                    </p>
                    <div class="border-t border-gray-200 my-2"></div>
                    <p @click="loginBtn"
                        class="block px-3 py-2.5 rounded-md text-base font-medium text-gray-700 hover:bg-blue-50 hover:text-blue-600">
                        Sign
                        In</p>
                    <p @click="registerBtn"
                        class="block px-3 py-2.5 rounded-md text-base font-medium text-gray-700 hover:bg-blue-50 hover:text-blue-600">
                        Register</p>
                    <p @click="navigate('Orders')"
                        class="block px-3 py-2.5 rounded-md text-base font-medium text-gray-700 hover:bg-blue-50 hover:text-blue-600">
                        Orders</p>
                </div>
            </div>
        </transition>
    </nav>
</template>
