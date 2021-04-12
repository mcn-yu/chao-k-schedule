<template>
  <section>
    <div>
      <div class="links">
        <RoomTable />
      </div>
    </div>
  </section>
</template>

<script>
import RoomTable from "~/components/RoomTable.vue";
export default {
  components: {
    RoomTable,
  },
};
</script>

<style scoped>
.links {
  padding-top: 15px;
}
</style>
