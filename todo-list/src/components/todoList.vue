<template>
  <div class="container">
      <h2>Todo-List</h2>
      <div class="flex">
        
      
      
          <input v-model="form.name" type="text" placeholder="Enter name" />
          <input v-model="form.phone" type="text" placeholder="Enter phone" />
          <input v-model="form.gmail" type="text" placeholder="Enter gmail" />
          <button @click="submitAll">Submit</button>
     

      
      </div>
    <table>
      <tr>
        <th>Name</th>
        <th>Number phone</th>
        <th>Gmail</th>
        <th>Edit</th>
        <th>Delete</th>
      </tr>
      <tr v-for="(all, index) in alls" :key="index">
        <td>{{ all.name }}</td>
        <td> {{ all.phone }} </td>
        <td> {{ all.gmail }} </td>
        <td>
          <div @click="editAll(index)">
            <b-icon icon="brush-fill"></b-icon>
          </div>
        </td>
        <td>
          <div @click="deleteAll(index)">
            <b-icon icon="trash"></b-icon>
          </div>
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
     
    editedAll: null,
     form: {
       name: "",
       phone: "",
       gmail: "",
     },
      alls: [
        {
          name: "Nguyễn Văn A",
          phone: 123456,
          gmail: "nguyenvana@gmail.com"
        },
        {
          name: "Nguyễn Văn B",
          phone: 123456,
          gmail: "nguyenvanb@gmail.com"
        },
        {
          name: "Nguyễn Văn C",
          phone: 123456,
          gmail: "nguyenvanc@gmail.com"
        },
      ]
    }
  },
  methods: {
    submitAll() {
      console.log(this.form)




      // if(!this.name && !this.phone && !this.gmail) return;

      // if (!this.editedAll) {
      //   this.alls.push({
          
      //     name: this.name,
      //     phone: this.phone,
      //     gmail: this.gmail
      //   });
      // } else {
      //   this.alls[this.editedAll].name = this.all;
      //   this.editedAll = null;
      // }
      
      
       
    },

    deleteAll(index) {
      this.alls.splice(index, 1);
    },

    editAll(index) {
      this.name = this.alls[index].name;
      this.phone = this.alls[index].phone;
      this.gmail = this.alls[index].gmail;
      this.editedAll = index;
      

    }
  }
}
</script>

<style scoped>
table {
  border-collapse: collapse;
  width: 50%;
}
td,
th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}
</style>