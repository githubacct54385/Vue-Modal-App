<template>
    <h1>{{ title }}</h1>
    <p>Welcome...</p>
    <teleport to=".modals" v-if="showModal">
        <Modal :header="header" :text="text" theme="sale" @close="toggleModal">
            <template v-slot:links>
                <a href="#">Sign up now</a>
                <a href="#">More Info</a>
            </template>
            <h1>Ninja Giveaway</h1>
            <p>Grab your ninja swag for half price!</p>
        </Modal>
    </teleport>
    <teleport to=".modals" v-if="showModal2">
        <Modal :header="header" :text="text" theme="" @close="toggleModal2">
            <template v-slot:links>
                <a href="#">Sign up now</a>
                <a href="#">More Info</a>
            </template>
            <h1>Sign up to the newsletter</h1>
            <p>For updates and promo codes</p>
        </Modal>
    </teleport>
    <button @click="toggleModal">Open Modal</button>
    <button @click="toggleModal2">Open Modal2</button>
</template>

<script>
import Modal from './components/Modal.vue';
export default {
    name: 'App',
    data() {
        return {
            title: 'My first Vue app',
            header: 'Sign up for the giveaway!',
            text: 'Grab your Ninja swag for half price!',
            showModal: false,
            showModal2: false,
        };
    },
    components: {
        Modal,
    },
    methods: {
        toggleModal() {
            this.showModal = !this.showModal;
        },
        toggleModal2() {
            this.showModal2 = !this.showModal2;
        },
    },
};
</script>

<style>
#app,
.modals {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
h1 {
    border-bottom: 1px solid #ddd;
    display: inline-block;
    padding-bottom: 10px;
}
</style>
