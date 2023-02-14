
<template>
    <div class="col">
        <div class="card" style="width: 18rem">
            <img
                src="../assets/img/flowers.png"
                width="28"
                class="card-img-top"
                alt="contact"
            />
            <div class="card-body">
                <h5 class="card-title">Namn: {{ list.name }}</h5>
                <p class="card-text"> Telefon: {{ list.phone }}
                </p>
                <a href="#" class="btn btn-primary">Kontakta mig här</a>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        list:{
            required: true,
            type: Object
        }

    }
}
</script>
<style></style>
