<template>
    <nav
        id="sidebar"
        v-if="isLoggedIn"
        v-show="
            $route.path === '/' ||
            $route.path === '/login' ||
            $route.path === '/register' ||
            $route.path === '/forget'
                ? false
                : true
        ">
        <ul class="navbar-nav sidebar sidebar-light accordion"
            id="accordionSidebar" >
            <a class="sidebar-brand d-flex align-items-center justify-content-center"
                href="#">

                <div class="sidebar-brand-text mx-3">Inventory Sales</div>
            </a>
            <hr class="sidebar-divider my-0" />
            <hr class="sidebar-divider" />
            <div class="sidebar-heading">
                Inventory
            </div>
            <li class="nav-item">
                <a
                    class="nav-link collapsed"
                    href="#"
                    data-toggle="collapse"
                    data-target="#product"
                    aria-expanded="true"
                    aria-controls="collapseForm"
                >
                    <i class="fab fa-fw fa-product-hunt"></i>
                    <span>Products</span>
                </a>
                <div
                    id="product"
                    class="collapse"
                    aria-labelledby="headingForm"
                    data-parent="#accordionSidebar"
                >
                    <div class="bg-white py-2 collapse-inner rounded">
                        <router-link
                            class="collapse-item"
                            :to="{ name: 'CreateProduct' }"
                            >Add Product</router-link
                        >
                        <router-link
                            class="collapse-item"
                            :to="{ name: 'Product' }"
                            >All Products</router-link
                        >
                    </div>
                </div>
            </li>

            <li class="nav-item">
                <a
                    class="nav-link collapsed"
                    href="#"
                    data-toggle="collapse"
                    data-target="#customer"
                    aria-expanded="true"
                    aria-controls="collapseTable"
                >
                    <i class="fas fa-fw fa-restroom"></i>
                    <span>Customer</span>
                </a>
                <div
                    id="customer"
                    class="collapse"
                    aria-labelledby="headingTable"
                    data-parent="#accordionSidebar"
                >
                    <div class="bg-white py-2 collapse-inner rounded">
                        <router-link
                            :to="{ name: 'CreateCustomer' }"
                            class="collapse-item"
                            >Add Customer</router-link
                        >
                        <router-link
                            class="collapse-item"
                            :to="{ name: 'Customer' }"
                            >All Customers</router-link
                        >
                    </div>
                </div>
            </li>
            <li class="nav-item">
                <a
                    class="nav-link collapsed"
                    href="#"
                    data-toggle="collapse"
                    data-target="#order"
                    aria-expanded="true"
                    aria-controls="collapseTable"
                >
                    <i class="fas fa-fw fa-sort-amount-up"></i>
                    <span>Order</span>
                </a>
                <div
                    id="order"
                    class="collapse"
                    aria-labelledby="headingTable"
                    data-parent="#accordionSidebar"
                >
                    <div class="bg-white py-2 collapse-inner rounded">

                        <router-link
                            :to="{ name: 'AllOrders' }"
                            class="collapse-item"
                            >All Orders</router-link
                        >
                    </div>
                </div>
            </li>
        </ul>
    </nav>
</template>

<script>
export default {
    data() {
        return {};
    },
    components: {},
    mounted() {
        this.$store.commit("isLogIn", window.auth_user);
    },
    created() {},
    computed: {
        isLoggedIn() {
            return this.$store.getters.isLoggedIn;
        }
    },
    methods: {}
};
</script>

<style></style>
