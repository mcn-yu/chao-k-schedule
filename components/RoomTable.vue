<template>
  <div>
    <table
      class="yg-table table-bordered"
      v-bind:style="{ minWidth: tableMin }"
    >
      <thead>
        <tr>
          <th scope="col"></th>
          <th scope="col" v-for="(i, k) in rooms" :key="k">
            {{ i.fields.Name }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(i, k) in schedules" :key="k">
          <td class="timeslot">
            {{ i.fields.time }}
          </td>
          <td
            :class="
              i.fields[i2.fields.Code] === true
                ? 'yg-schedule-full'
                : 'yg-schedule-empty'
            "
            v-for="(i2, k2) in rooms"
            :key="k2"
          >
            {{ i.fields[i2.fields.Code] === true ? "×" : "◯" }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      schedules: [],
      rooms: [],
      tableMin: "500px",
    };
  },
  created() {
    this.getData();
  },
  methods: {
    async getData() {
      const reponse = await this.$axios.$get(
        "https://api.airtable.com/v0/appZeqFbVXrGled2I/Schedule?sort%5B0%5D%5Bfield%5D=time",
        {
          headers: {
            Authorization: "Bearer keyda38YqYRDASE5C",
          },
        }
      );
      const reponse2 = await this.$axios.$get(
        "https://api.airtable.com/v0/appZeqFbVXrGled2I/Room?sort%5B0%5D%5Bfield%5D=Order",
        {
          headers: {
            Authorization: "Bearer keyda38YqYRDASE5C",
          },
        }
      );
      this.schedules = reponse.records;
      this.rooms = reponse2.records;
      this.tableMin = this.rooms.length * 70 + "px";
      console.log(this.tableMin);
    },
  },
};
</script>
<style scoped>
table.yg-table {
  border: 1px solid #ccc;
  border-collapse: collapse;
  margin: 0;
  padding: 0;
  width: 100%;
  table-layout: fixed;
}

table.yg-table caption {
  font-size: 1.5em;
  margin: 0.5em 0 0.75em;
}

table.yg-table tr {
  background-color: #f8f8f8;
  border: 1px solid #ddd;
  padding: 0.35em;
}

table.yg-table th,
table.yg-table td {
  padding: 0.625em;
  text-align: center;
}

table.yg-table th {
  font-size: 0.85em;
  letter-spacing: 0.1em;
  text-transform: uppercase;
}

table.yg-table {
  overflow-x: auto;
}

.yg-thead {
  font-size: 16px;
  line-height: 1.5em;
  background: #f6f6f6;
  color: #000;
  font-family: sans-serif;
}

.yg-schedule-empty {
  background: #69ca47;
  color: black;
  text-align: center;
}

.yg-schedule-full {
  color: black;
  text-align: center;
}

.table-bordered td,
.table-bordered th {
  border: 1px solid #f2f2f2;
}
</style>