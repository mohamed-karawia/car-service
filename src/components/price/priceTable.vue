<template>
  <div class="price__table--container">
    <table>
      <tr>
        <th>Name</th>
        <th>Description</th>
        <th>Price ($)</th>
      </tr>
      <tr v-for="(service, index) in brand" :key="index">
        <td>{{ service.name }}</td>
        <td>{{ service.description }}</td>
        <td>{{ service.price }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
    props:{
        brand: Array
    },
}
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.price__table--container {
  width: 90%;
  border: 1px solid #efefef;
  padding: 2rem;
  display: flex;
  justify-content: center;
  align-items: center;

  @media only screen and (max-width: 720px){
      width: 100%;
      padding: 1rem;
  }

    @media only screen and (max-width: 500px){
      width: 100%;
      padding: 0rem;
  }

  table {
    width: 100%;
  }

  th,
  td {
    border: 1px solid #ddd;
    padding: 8px;
    text-transform: capitalize;
    padding: 1rem;
  }

  & tr:nth-child(even) {
    background-color: #f2f2f2;
  }

  tr:hover {
    background-color: #ddd;
  }

  th {
    padding: 1rem;
    font-size: 1.1rem;
    text-align: left;
    background-color: $primary-color;
    color: white;
  }
}
</style>