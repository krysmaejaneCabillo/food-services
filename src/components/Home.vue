<script>
import Modal from '../Modal/Modal.vue';
export default {
    components: {
        Modal
    },
    props: {
        selectProduct: {
            type: Object
        },
        bar:{
            type: String
        }
      

    },
    data() {
        return {
            openModal: false,
            currentIndex: 0,
            product: [
                {
                    id: 1,
                    name: 'Roast Porkloin with Paprika Sauce',
                    price: '299.99',
                    img: 'https://www.carlitoscatering.ph/cdn/shop/products/2-Roast_Porkloin_with_Creamy_Paprika_Sauce_530591b2-5b4f-4b16-8a33-ab8774c75037_622x.png?v=1605075746',
                    sold: '(256)',
                    definition: 'Oven-roasted porkloin with hints of Dijon mustard and white wine, served in a paprika cream sauce.',
                    max: '50-100 Pax'
                },
                {
                    id: 2,
                    name: 'Prawns with Butter Garlic Sauce',
                    price: '129.99',
                    img: 'https://images.unsplash.com/photo-1625943553852-781c6dd46faa?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8UHJhd25zJTIwd2l0aCUyMEJ1dHRlciUyMEdhcmxpYyUyMFNhdWNlfGVufDB8fDB8fHww',
                    sold: '(128)',
                    definition: 'Jumbo prawns sauteed in butter, garlic and our own house blend of seasonings and spices.',
                    max: '50-100 Pax'
                },
                {
                    id: 3,
                    name: 'Creamy Mushroom Soup',
                    price: '199.00',
                    img: 'https://plus.unsplash.com/premium_photo-1769843181775-4a3f266dcea3?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NDh8fENyZWFteSUyME11c2hyb29tJTIwU291cHxlbnwwfHwwfHx8MA%3D%3D',
                    sold: '(98)',
                    definition: 'Creamy mushroom soup is a smooth, rich soup made with mushrooms and cream.',
                    max: '50-100 Pax'
                },
                {
                    id: 4,
                    name: 'Mesclun Green with Parmesan and Raspberry Vinaigrette',
                    price: '100.50',
                    img: 'https://th.bing.com/th/id/OIP.OzuDCgLFA5Sb3lSlo27YJgHaHa?w=191&h=191&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3',
                    sold: '(78)',
                    definition: 'Assorted fresh greens, Parmesan shavings and candied walnuts served with a tangy raspberry vinaigrette.',
                    max: '50-100 Pax'
                },
                {
                    id: 5,
                    name: 'Truffle Cream Pasta with Prosciutto',
                    price: '249.99',
                    img: 'https://th.bing.com/th/id/OIP.CstrRiRVLo3LTEwU3nsFhgHaHa?w=197&h=197&c=7&r=0&o=7&dpr=1.3&pid=1.7&rm=3',
                    sold: '(42)',
                    definition: 'Fresh shiitake mushrooms in a truffle cream sauce, tossed with freshly-cooked pasta and topped with silky prosciutto ribbons.',
                    max: '15-30 Pax'
                },
                {
                    id: 6,
                    name: 'Hickory Pork Belly',
                    price: '125',
                    img: 'https://www.carlitoscatering.ph/cdn/shop/products/20210301_194421_622x.jpg?v=1614599103',
                    sold: '(125)',
                    definition: 'Sweet and smokey barbecued pork belly',
                    max: '50-100 Pax'
                },
                {
                    id: 7,
                    name: 'Baby Back Ribs',
                    price: '89',
                    img: 'https://www.carlitoscatering.ph/cdn/shop/files/babybackribs_622x.png?v=1739989682',
                    sold: '(200)',
                    definition: 'Tender lean pork ribs cut from the upper rib cage near the loin, shorter and smaller than spare ribs.',
                    max: '50-100 Pax'
                },
                {
                    id: 8,
                    name: 'Pork Barbeque',
                    price: '80',
                    img: 'https://www.carlitoscatering.ph/cdn/shop/files/DSCF8986_180x.jpg?v=1773121929',
                    sold: '(99)',
                    definition: 'Marinated pork grilled over fire, sweet-savory, smoky, and tender.',
                    max: '50-100 Pax'
                },
                {
                    id: 9,
                    name: 'Chicken Teriyaki',
                    price: '120',
                    img: 'https://www.carlitoscatering.ph/cdn/shop/files/teriyaki_180x.png?v=1739990978',
                    sold: '(200)',
                    definition: 'Tender chicken glazed with sweet-savory soy sauce, sticky and glossy.',
                    max: '50-100 Pax'
                },
                {
                    id: 10,
                    name: 'Chicken Lollipop',
                    price: '120',
                    img: 'https://www.carlitoscatering.ph/cdn/shop/files/DSCF8843-2_622x.jpg?v=1773121575',
                    sold: '(220)',
                    definition: ' Chicken wing/meat shaped like a lollipop, crispy, spicy fried appetizer.',
                    max: '50-100 Pax'
                },

            ],

        }
    },
        computed: {
        filteredProducts() {
            if (!this.bar.trim()) {
                return this.product
            }
            const query = this.bar.toLowerCase().trim();
            return this.product.filter(foods =>
                foods.name.toLowerCase().includes(query)
            )
        }

    },
    methods: {
        open(index) {
            this.currentIndex = index;
            this.openModal = true;
        },
        addOrder(foods){
            this.$emit('add-order', {...foods})

        }
    }
}

</script>

<template>
    <div class="bg-gradient-to-b from-black via-red-700 to-black text-gray-800 font-sans">
        <main>
            <!-- Hero Banner -->
            <section class="max-w-7xl mx-auto px-3 sm:px-4 lg:px-6 py-6 sm:py-8">
                <div class="rounded-xl overflow-hidden shadow-md border border-red-100 bg-transparent text-white">
                    <div class="grid md:grid-cols-2 items-center">
                        <div class="p-6 sm:p-8 lg:p-10 space-y-3 sm:space-y-4">
                            <h1 class="text-[clamp(1.5rem,4vw,2.5rem)] font-bold leading-tight">
                                Great Food, Great Service.
                            </h1>
                            <p class="text-blue-100 text-base sm:text-lg">
                                "Order now, and let us turn your event into a wonderful experience with food
                                that delights and service that cares."
                            </p>
                            <a href="#"
                                class="inline-block bg-white text-red-700 font-medium px-5 sm:px-6 py-2.5 rounded-lg shadow hover:shadow-md transition-all">
                                Order Now
                            </a>
                        </div>
                        <div class="hidden md:block p-4">
                            <img src="https://plus.unsplash.com/premium_photo-1673108852141-e8c3c22a4a22?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8Zm9vZCUyMHBob3RvZ3JhcGh5fGVufDB8fDB8fHww"
                                alt="Hero banner" class="w-full h-auto rounded-lg object-cover" />
                        </div>
                    </div>
                </div>
            </section>

            <!-- Categories Section -->
            <section class="max-w-7xl mx-auto px-3 sm:px-4 lg:px-6 py-6 sm:py-8">
                <h2 class="text-xl sm:text-2xl font-bold mb-4 sm:mb-6 text-red-100">Shop by Category</h2>
                <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 gap-3 sm:gap-4">
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://images.unsplash.com/photo-1624639644675-6b75d9b44b98?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTQ2fHxwb3JrJTIwZm9vZCUyMHBob3RvZ3JhcGh5fGVufDB8fDB8fHww"
                            alt="Pork" class="w-30 h-30  mx-auto mb-2 sm:mb-3" />
                        <span class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Pork</span>
                    </div>
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://images.unsplash.com/photo-1608877906601-33195b1dc2cb?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxwaG90by1yZWxhdGVkfDEwfHx8ZW58MHx8fHx8"
                            alt="Beef" class="w-30 h-30  mx-auto mb-2 sm:mb-3" />
                        <span class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Beef</span>
                    </div>
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://plus.unsplash.com/premium_photo-1669742928112-19364a33b530?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8Y2hpY2tlbiUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="Chicken" class="w-30 h-30 mx-auto mb-2 sm:mb-3" />
                        <span
                            class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Chicken</span>
                    </div>
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://plus.unsplash.com/premium_photo-1717345994192-f5bc10b61c09?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MXx8c2VhZm9vZCUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="Seafoods" class="w-30 h-30 mx-auto mb-2 sm:mb-3" />
                        <span
                            class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Seafood</span>
                    </div>
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://images.unsplash.com/photo-1627042633145-b780d842ba45?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8cGFzdGElMjBmb29kJTIwcGhvdG9ncmFwaHl8ZW58MHx8MHx8fDA%3D"
                            alt="Pasta" class="w-30 h-30 mx-auto mb-2 sm:mb-3" />
                        <span class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Pasta</span>
                    </div>
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://images.unsplash.com/photo-1678831654488-68e2559abfd1?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTYyfHxzYWxhZCUyMGdyZWVucyUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="salad" class="w-30 h-30 mx-auto mb-2 sm:mb-3" />
                        <span class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Salad
                            Greens</span>
                    </div>
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://images.unsplash.com/photo-1606791496080-69a6e309f42c?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MjR8fHNvdXAlMjBmb29kJTIwcGhvdG9ncmFwaHl8ZW58MHx8MHx8fDA%3D"
                            alt="soup" class="w-30 h-30 mx-auto mb-2 sm:mb-3" />
                        <span class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Soup</span>
                    </div>
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://images.unsplash.com/photo-1586357884522-4d4972459ff5?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NjJ8fHN0YXJjaCUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="starch" class="w-30 h-30 mx-auto mb-2 sm:mb-3" />
                        <span class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Starch</span>
                    </div>
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://plus.unsplash.com/premium_photo-1672865358972-d0fcd3188f98?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MzN8fG1lcmllbmRhJTIwZm9vZCUyMHBob3RvZ3JhcGh5fGVufDB8fDB8fHww"
                            alt="merienda" class="w-30 h-30 mx-auto mb-2 sm:mb-3" />
                        <span
                            class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Merienda</span>
                    </div>
                    <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow p-4 text-center">
                        <img src="https://images.unsplash.com/photo-1605807646983-377bc5a76493?w=600&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Mnx8Y2FrZSUyMGZvb2QlMjBwaG90b2dyYXBoeXxlbnwwfHwwfHx8MA%3D%3D"
                            alt="cake" class="w-30 h-30 mx-auto mb-2 sm:mb-3" />
                        <span class="text-sm font-medium text-gray-700 cursor-pointer hover:text-red-600">Cake</span>
                    </div>
                </div>
            </section>

            <!-- Recommended Products -->
            <section class="max-w-7xl mx-auto px-3 sm:px-4 lg:px-6 py-6 sm:py-8">
                <h2 class="text-red-100 text-xl sm:text-2xl font-bold mb-4 sm:mb-6">Menu</h2>
                <div
                    class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5 gap-4 sm:gap-5">

                    <div v-for="(foods, index) in filteredProducts" :key="foods.id"
                        class="bg-white rounded-lg shadow-sm hover:shadow-lg transition-shadow overflow-hidden group">
                        <div @click="open(index)">
                            <img :src="foods.img" alt="Product"
                                class="w-full h-40 sm:h-48 object-cover group-hover:scale-105 transition-transform duration-300" />
                            <div class="p-3 sm:p-4">
                                <h3 class="text-sm font-medium text-gray-800 line-clamp-2">{{ foods.name }}</h3>
                                <p class="text-lg font-bold text-red-700 mt-1">${{ foods.price }}</p>
                                <div class="flex items-center text-yellow-500 text-xs mt-1">
                                    <svg class="w-4 h-4 " aria-hidden="true" xmlns="http://www.w3.org/2000/svg"
                                        width="24" height="24" fill="currentColor" viewBox="0 0 24 24">
                                        <path
                                            d="M13.849 4.22c-.684-1.626-3.014-1.626-3.698 0L8.397 8.387l-4.552.361c-1.775.14-2.495 2.331-1.142 3.477l3.468 2.937-1.06 4.392c-.413 1.713 1.472 3.067 2.992 2.149L12 19.35l3.897 2.354c1.52.918 3.405-.436 2.992-2.15l-1.06-4.39 3.468-2.938c1.353-1.146.633-3.336-1.142-3.477l-4.552-.36-1.754-4.17Z" />
                                    </svg>
                                    <span class="text-gray-500 ml-1">{{ foods.sold }}</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </main>
    </div>

    <Modal v-if="openModal" :selectProduct="product[currentIndex]" @close-modal="openModal = false" @add-order="addOrder" />
</template>
