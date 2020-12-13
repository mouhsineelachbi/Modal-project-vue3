<template>
    <div class="backdrop" @click.self="closeModal"> <!-- self is an event modifier to react only for this not Its children !-->
        <div class="modal" :class="{ sale: theme === 'sale'}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot> <!-- links is the name of the named slot -->
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ['theme'],
    methods: {
        closeModal () {
            this.$emit('close')
        }
    }
}
</script>

<style >
.modal {
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}
.backdrop {
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}
h1 {
    color: red;
}

.modal p {
    font-style: normal;
}

.modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
}

.modal .actions a {
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px
}

/* Sale styles */ 

.modal.sale .actions {
    color: white;
}

.modal.sale .actions a {
    color: white;
}

.modal.sale {
    background: crimson;
    color: white;
}

.modal.sale h1 {
    color: white;
}

</style>