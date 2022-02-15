<template  >
  <v-container >
    
    <center><h1 class="text-info">Shop Doraemon</h1></center>
    <v-container class="d-flex flex-wrap">
      <v-card
        class="mx-auto mb-5"
        max-width="400"
        v-for="(i, index) in productlist"
        :key="index"
      >
        <v-img class="black--text align-end" height="200px" :src="i.imageurl">
          <v-card-title>{{ i.name }}</v-card-title>
        </v-img>

        <v-card-subtitle class="pb-0">{{ i.rightText }}</v-card-subtitle>

        <v-card-text class="text--primary">
          <div>{{ i.leftText }}</div>
        </v-card-text>

        <v-card-actions>
          <v-btn color="teal lighten-1" text :to="'/detail/' + i.name">detail</v-btn>
          <v-btn color="deep-orange lighten-2" text > Add </v-btn>
          <div class="card-footer">
            <input type="checkbox" class="form-control" @change="selected(i)" />
          </div>
        </v-card-actions>
      </v-card>
    </v-container>

    <table class="table table-striped table-hover">        
    
    </table>
    <v-container
      ><h4 class="text-danger fs-1">ยอดรวม  {{ total() }} บาท</h4></v-container
    >
    <v-container grid-list-xs class="light-blue accent-1">
      <router-view :key="$route.path"></router-view>
    </v-container>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
        productlist: [
        {
         
          name: "แมวเหมียวน่ารัก - แมวดำ",
          imageurl:
            "https://undubzapp.com/wp-content/uploads/2017/11/%E0%B8%AA%E0%B8%B1%E0%B8%95%E0%B8%A7%E0%B9%8C%E0%B9%81%E0%B8%AB%E0%B9%88%E0%B8%87%E0%B8%A5%E0%B8%B2%E0%B8%87%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%A2-%E0%B8%84%E0%B8%A7%E0%B8%B2%E0%B8%A1%E0%B8%95%E0%B8%B2%E0%B8%A2-%E0%B9%81%E0%B8%A1%E0%B8%A7%E0%B8%94%E0%B8%B3-%E0%B8%9B%E0%B8%A5%E0%B8%B8%E0%B8%81%E0%B8%9C%E0%B8%B5%E0%B9%84%E0%B8%94%E0%B9%89%E0%B8%88%E0%B8%A3%E0%B8%B4%E0%B8%87%E0%B8%AB%E0%B8%A3%E0%B8%B7%E0%B8%AD-800x445.jpg",
          rightText: "แมวสีดำเวลากลางคืนจะกลมกลืนไปกับความมืดแทบมองไม่เห็นเลยทีเดียวเชียว",
          ctaText: "Shop Now",
          active: false,
          price: 666,
        },

        {
         
          name: "แมวเหมียวน่ารัก - แมวส้มน่ารัก",
          imageurl:
            "https://gatoro.co/wp-content/uploads/2020/05/orange-cat-secret-featured-image.png.webp",
          rightText: "แมวส้มตัวนี้มีลายที่สวมงามบวกกับนิสัยบุคคลิกขี้เล่นน่ารักของแมวตัวนี้",
          ctaText: "Shop Now",
          active: false,
          price: 777,
        },

        {
         
          name: "แมวเหมียวน่ารัก - แมวขี้เซา",
          imageurl:
            "https://www.bloggang.com/data/thelover/picture/1208512830.jpg",
          rightText: "แมวขี้เซาเป็นแมวที่นอนเกือบทั้งวันนิสัยของมันขี้เกียจมากๆ",
          ctaText: "Shop Now",
          active: false,
          price: 888,
        },

        {
         
          name: "แมวเหมียวน่ารัก - แมวสามสี",
          imageurl:
            "",
          rightText: "แมวสามสีด้วยลายเป็นเอกลักษณ์ไม่เหมือนใครรวมถึงนิสัยของมันขึ้นอยู่กับการดูของเจ้าของมันต่างๆ",
          ctaText: "Shop Now",
          active: false,
          price: 999,
        },
      ],
    };
  },
  methods: {
    selected: function (i) {
      i.active = !i.active;
    },
    total: function () {
      var sum = 0;
      this.productlist.forEach(function (i) {
        if (i.active) {
          sum += i.price;
        }
      });
      return sum;
    },
  },
 
};
</script>

<style>
h2 {
  color: rgb(255, 56, 139);
}
</style>
