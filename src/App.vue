<script>
import Modal from "./components/Modal.vue";
export default {
    name: "App",
    components: { Modal },
    data() {
        return {
            title: "First Vue App",
            header: "Sign up for the Giveways",
            text: "Grab your ninja swag for half price",
            showModal: false,
        };
    },
    methods: {
        handleClick() {
            console.log(this.$refs.name);
            this.$refs.name.classList.add("active");
            this.$refs.name.focus();
        },
        toggleModal() {
            this.showModal = !this.showModal;
        },
    },
};
</script>

<template>
    <div>
        <h1>{{ title }}</h1>
        <br />
        <input type="text" ref="name" />
        <button @click="handleClick">click me</button>
    </div>
    <br />

    <div v-if="showModal">
        <Modal
            :header="header"
            :text="text"
            theme="sale"
            @close="toggleModal"
        />
    </div>
    <br />
    <button @click.alt="toggleModal">open modal (alt)</button>
</template>

<style>
h1 {
    border-bottom: 1px solid #ddd;
    padding-bottom: 10px;
}
</style>
