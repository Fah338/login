<template>
  <div class="Menu">
    <div class="container">
      <b-nav tabs fill align="left">
        <router-link to="/Menu">Main coures</router-link> |
        <router-link to="/Appetizer">Appetizer</router-link>
      </b-nav>
    </div>
    <b-container>
     
     <pagemenu
      v-for="(item,index) in list"
      :key="index"
      :Name="item.name"
       :price="item.price"
      :Img="item.url"
      :Engname="item.Engname"
      :title="item.title"
      :title1="item.title1"
     
      :id="item.mal_id"
     class="mt-4"
      />

 
  
         
        
      
    </b-container>
  </div>
</template>
<script>

import { db } from "@/plugin/firebaseConfig.js";
import Pagemenu from '../components/Pagemenu.vue';
export default {
  name: 'menu',
  components: {
    Pagemenu
   
  },
  data() {
    return {
      list: [],
    };
  },
  created() {
    this.get();
  },
  methods: {
    get() {
      db.collection("FoodDetail")
        .orderBy("id")
        .onSnapshot(querySnapshot => {
          querySnapshot.forEach(doc => {
            console.log(doc.id);
            this.list.push(doc.data());
          });
        });
    },
  },
};
</script>
