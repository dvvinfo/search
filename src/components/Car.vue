<template>
  <div class="hello">
    <h1>Блог</h1>
    <div class="form">
      <form action="#">
        <input type="search" class="input" v-model="search" placeholder="поиск">
        
      </form>
    </div>
    <div class="wrapper"> 
      <div class="item " v-for="car in filteredItems" :key="car.id">
        <div class="img">
          <img :src=car.img alt="">
        </div>
        <h3 class="item__title">{{car.title}}</h3>
        <div class="item__descr">{{car.descr}}</div>
      </div>
    </div>
    <div class="padination">
      <button class="padination__btn"></button>
      
    </div>
  </div>
</template>

<script>
  
export default {
  data() {
    return {
      search: "",
      cars:[
      {
        id:1,
        img: 'https://mashintop.ru/images_cache/car_photo_big/uploads/attachments/car_photo/2013-08-04/1949574135/originals/800x600_6941375631910.jpg',
        title: 'Мустанг',
        descr: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Reiciendis iure dolor quas error laborum saepe illo voluptatum quam veritatis. Ducimus dolorum maiores aliquam minima reiciendis ipsum distinctio laboriosam quibusdam qui.Adipisci, vel quas? Fuga odio harum, nesciunt voluptas minus fugit soluta odit officiis. Neque, natus veniam. Ut iure unde corrupti eaque rem aut atque culpa eligendi deleniti aspernatur? Eligendi, temporibus?'
      },
      {
        id:2,
        img: 'https://flirtic.com/media/photos/1/0/1/10143758800.jpg',
        title: 'Мерседес',
        descr: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Reiciendis iure dolor quas error laborum saepe illo voluptatum quam veritatis. Ducimus dolorum maiores aliquam minima reiciendis ipsum distinctio laboriosam quibusdam qui.Adipisci, vel quas? Fuga odio harum, nesciunt voluptas minus fugit soluta odit officiis. Neque, natus veniam. Ut iure unde corrupti eaque rem aut atque culpa eligendi deleniti aspernatur? Eligendi, temporibus?'
      },
      {
        id:3,
        img: 'https://sadaomix.com/blog/wp-content/uploads/2011/05/p8.jpg',
        title: 'Мазда',
        descr: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Reiciendis iure dolor quas error laborum saepe illo voluptatum quam veritatis. Ducimus dolorum maiores aliquam minima reiciendis ipsum distinctio laboriosam quibusdam qui.Adipisci, vel quas? Fuga odio harum, nesciunt voluptas minus fugit soluta odit officiis. Neque, natus veniam. Ut iure unde corrupti eaque rem aut atque culpa eligendi deleniti aspernatur? Eligendi, temporibus?'
      },
      {
        id:4,
        img: 'https://autohorses.ru/upload/iblock/80e/80e168657dbca022ef8cbbde2eb227c9.jpg',
        title: 'Ауди',
        descr: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Reiciendis iure dolor quas error laborum saepe illo voluptatum quam veritatis. Ducimus dolorum maiores aliquam minima reiciendis ipsum distinctio laboriosam quibusdam qui.Adipisci, vel quas? Fuga odio harum, nesciunt voluptas minus fugit soluta odit officiis. Neque, natus veniam. Ut iure unde corrupti eaque rem aut atque culpa eligendi deleniti aspernatur? Eligendi, temporibus?'
      },
      {
        id:5,
        img: 'https://avto-dvizh.ru/wp-content/uploads/2020/01/toyota_venza.jpg',
        title: 'Тойота',
        descr: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Reiciendis iure dolor quas error laborum saepe illo voluptatum quam veritatis. Ducimus dolorum maiores aliquam minima reiciendis ipsum distinctio laboriosam quibusdam qui.Adipisci, vel quas? Fuga odio harum, nesciunt voluptas minus fugit soluta odit officiis. Neque, natus veniam. Ut iure unde corrupti eaque rem aut atque culpa eligendi deleniti aspernatur? Eligendi, temporibus?'
      },
      {
        id:6,
        img: 'https://img.favcars.com/skoda/octavia/pictures_skoda_octavia_2009_16_800x600.jpg',
        title: 'Шкода',
        descr: 'Lorem ipsum, dolor sit amet consectetur adipisicing elit. Reiciendis iure dolor quas error laborum saepe illo voluptatum quam veritatis. Ducimus dolorum maiores aliquam minima reiciendis ipsum distinctio laboriosam quibusdam qui.Adipisci, vel quas? Fuga odio harum, nesciunt voluptas minus fugit soluta odit officiis. Neque, natus veniam. Ut iure unde corrupti eaque rem aut atque culpa eligendi deleniti aspernatur? Eligendi, temporibus?'
      },
    ]
    }
   
  },
  computed: {
    filteredItems() {
      return this.cars.filter(elem =>{
        return elem.title.toLowerCase().includes(this.search) ;
      })
    }

    },
  name: 'Car',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.wrapper{
display: flex;
  max-width: 1400px;
  margin: 20px auto;
  column-gap: 20px;
  flex-direction: column;
  
}
.item{
  width: 100%;
  margin-bottom: 20px;

  
}
.img img{
  max-width: 600px;
  width: 100%;
}
.btn{
  margin-left: 20px;
  font-family: serif;
  font-size: 16px;
  height: 34px;
}
.input{
  padding: 5px;
  height: 30px;
}
.padination{
  display: flex;
  align-items: center;
  justify-content: center;
}
.padination__btn{
  margin: 0 5px;
}
a {
  color: #42b983;
}
</style>
