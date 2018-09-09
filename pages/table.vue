<template>
 <div>
  <v-data-table
    :headers="headers"
    :items="desserts"
    class="elevation-1"
  >
    <template slot="items" slot-scope="props">
      <td>{{ props.item.K_code }}</td>
      <td class="text-xs-center">{{ props.item.K_name }}</td>
      <td class="text-xs-center">{{ props.item.K_number }}</td>
      <td class="text-xs-center">{{ props.item.K_price }}</td>
    </template>
    <template slot="pageText" slot-scope="props">
      Lignes {{ props.pageStart }} - {{ props.pageStop }} de {{ props.itemsLength }}
    </template>
  </v-data-table>
  <div>
    <v-btn color="success">ตกลง</v-btn>
    <v-btn color="error">แก้ไข</v-btn>
    <v-btn color="warning">ชำระเงิน</v-btn>
    <v-btn color="info">ที่อยู่</v-btn>
  </div>
   </div>
</template>
<script>
  export default {
    data () {
      return {
        headers: [
          {
            text: 'รหัสสินค้า',
            align: 'left',
            sortable: false,
            value: 'name'
          },
          { text: 'ชื่อสินค้า', value: 'sunny_n', align: 'center'},
          { text: 'จำนวน', value: 'sunny_nb', align: 'center' },
          { text: 'ราคา', value: 'sunny_p', align: 'center' },
        ],
        desserts: [],
      }
    },
    async created() {
    this.getstudent()
  }, 
methods: {
    async getstudent() {
      let res = await this.$http.get('http://127.0.0.1/php-api - Copy/list-student.php')
      this.desserts = res.data.student
    },
},
  }
</script>
