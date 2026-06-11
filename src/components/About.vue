<script>

</script>

<template>

    <div class="antialiased bg-gradient-to-b from-black via-red-700 to-black">
        <!-- Hero Section -->
        <section class="bg-neutral py-12 md:py-16">
            <div class="container mx-auto px-4 border border-red-100 p-10 rounded-3xl">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                    <div class="order-2 md:order-1">
                        <h1 class="text-[clamp(2rem,4vw,3.5rem)] font-bold leading-tight text-white mb-4">
                           Where Every Bite Tells a Story
                        </h1>
                        <p class="text-white text-lg mb-6 max-w-lg">

                            At Taste Bite, every bite is made with fresh ingredients, careful preparation, and bold,
                            delicious flavor. We craft food that’s satisfying, high-quality, and full of taste you’ll
                            love. Simple, tasty, and always worth coming back for—because great food is what we do best.
                        </p>
                        <div class="flex flex-wrap gap-3">
                            <a href="#categories"
                                class="border border-red-100 text-white px-6 py-3 rounded-lg font-medium  transition-colors">
                                Browse Categories
                            </a>
                            <a href="#featured"
                                class="border border-primary text-primary px-6 py-3 rounded-lg font-medium hover:bg-primary/5 transition-colors">
                                Featured Items
                            </a>
                        </div>
                    </div>
                    <div class="order-1 md:order-2 rounded-2xl overflow-hidden card-shadow">
                        <img src="https://plus.unsplash.com/premium_photo-1670740967011-86730910a2e5?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mzk2fHxmb29kJTIwcGhvdG9ncmFwaHl8ZW58MHx8MHx8fDA%3D"
                            alt="Marketplace" class="w-full h-[300px] md:h-[400px] object-cover">
                    </div>
                </div>
            </div>
        </section>

        <!-- Categories -->
        <section id="categories" class="py-12">
            <div class="container mx-auto px-4">
                <h2 class="text-2xl md:text-3xl font-bold text-center mb-10 text-white">Shop by Category</h2>
                <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-4 md:gap-6">
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://images.unsplash.com/photo-1624639644675-6b75d9b44b98?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTQ2fHxwb3JrJTIwZm9vZCUyMHBob3RvZ3JhcGh5fGVufDB8fDB8fHww"
                            alt="Electronics" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Pork</span>
                    </a>
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://images.unsplash.com/photo-1608877906601-33195b1dc2cb?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDEwfHx8ZW58MHx8fHx8"
                            alt="Fashion" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Beef</span>
                    </a>
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://plus.unsplash.com/premium_photo-1669742928112-19364a33b530?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8Y2hpY2tlbiUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="Home & Living" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Chicken</span>
                    </a>
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://plus.unsplash.com/premium_photo-1717345994192-f5bc10b61c09?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8c2VhZm9vZCUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="Sports" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Seafood</span>
                    </a>
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://images.unsplash.com/photo-1627042633145-b780d842ba45?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8cGFzdGElMjBmb29kJTIwcGhvdG9ncmFwaHl8ZW58MHx8MHx8fDA%3D"
                            alt="Beauty" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Pasta</span>
                    </a>
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://images.unsplash.com/photo-1678831654488-68e2559abfd1?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTYyfHxzYWxhZCUyMGdyZWVucyUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="Collectibles" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Salad Greens</span>
                    </a>
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://images.unsplash.com/photo-1606791496080-69a6e309f42c?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjR8fHNvdXAlMjBmb29kJTIwcGhvdG9ncmFwaHl8ZW58MHx8MHx8fDA%3D"
                            alt="Collectibles" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Pasta</span>
                    </a>
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://images.unsplash.com/photo-1586357884522-4d4972459ff5?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NjJ8fHN0YXJjaCUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="Collectibles" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Starch</span>
                    </a>
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://plus.unsplash.com/premium_photo-1672865358972-d0fcd3188f98?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MzN8fG1lcmllbmRhJTIwZm9vZCUyMHBob3RvZ3JhcGh5fGVufDB8fDB8fHww"
                            alt="Collectibles" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Merienda</span>
                    </a>
                    <a href="#"
                        class="group flex flex-col items-center p-4 rounded-xl bg-white hover:bg-neutral/70 transition-colors card-shadow">
                        <img src="https://images.unsplash.com/photo-1605807646983-377bc5a76493?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8Y2FrZSUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="Collectibles" class="w-30 h-30 mb-3">
                        <span class="font-medium text-center group-hover:text-red-500">Cake</span>
                    </a>
                </div>
            </div>
        </section>

       

    </div>
</template>