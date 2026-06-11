<script>
import Navbar from './components/Navbar.vue';
import Home from './components/Home.vue';
import About from './components/About.vue';
import Orders from './components/Orders.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';

export default {
    components: {
        Navbar,
        Home,
        About,
        Orders,
        Contact,
        Footer,

    },
    data() {
        return {
            currentPage: 'Home',
            order: [],
            searchBar: '',

        }
    },
    methods: {
        changePage(page) {
            this.currentPage = page;
        },
        addOrder(index) {
            this.order.push({ ...index })
        },
        handleSearch(searchValue) {
            this.searchBar = searchValue
        },
    }
}

</script>

<template>
    <Navbar @goTo="changePage" :orderCount="order.length"  @search-bar="handleSearch"/>
    <Home v-if="currentPage === 'Home'" @add-order="addOrder" :bar="searchBar" />
    <About v-if="currentPage === 'About'" />
    <Orders v-if="currentPage === 'Orders'" :order="order" />
    <Contact v-if="currentPage === 'Contact'"/>
    <Footer/>
</template>
