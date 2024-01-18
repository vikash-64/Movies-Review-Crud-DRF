<template>
    <div class="w3-container w3-card-4 w3-light-grey">

        <div class="table">
            <Table />

        </div>
        <div class="addmov">
            <AddMovie />
        </div>

    </div>
</template>

<script>
import Table from '@/components/Table.vue';
import AddMovie from '@/components/AddMovie.vue';
export default {

    components: {
        Table,
        AddMovie,
    }


}
</script>

<style scoped >
.addmov {
    margin-top: 20px;
    margin-bottom: 20px;
}
</style>