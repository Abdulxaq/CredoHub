<template>
  <div>
    <b-navbar class="nav">
      <b-navbar-brand class="logo" href="#">Credo<span>Hub</span></b-navbar-brand>
      <b-navbar-nav class="nav-links"  >
        <b-nav-item class="nav-item" href="#" active ><span>HOME</span></b-nav-item>
        <b-nav-item v-on:click="fact1 = !fact1" class="nav-item" href="#" active >
           <span>ABOUT US</span>  <b-icon class="down" rotate="90" icon="chevron-right"></b-icon>
            <ul>
                <li v-for="i in aboutUs" v-bind:key="i.info" ><a href="#">{{i.info}}</a></li>
            </ul>
            </b-nav-item>
            <span class="sub" v-bind:class="{'sub-true': fact1}">
                <b-nav-item class="nav-item" href="#" active ><span>{{aboutUs[0].info}}</span></b-nav-item>
                <b-nav-item class="nav-item" href="#" active ><span>{{aboutUs[1].info}}</span></b-nav-item>
                <b-nav-item class="nav-item" href="#" active ><span>{{aboutUs[2].info}}</span></b-nav-item>
            </span>

        <b-nav-item v-on:click="fact2 = !fact2" class="nav-item" href="#" active >
           <span>COURSES</span>  <b-icon class="down" rotate="90" icon="chevron-right"></b-icon>
            <ul>
                <li><a href="#">{{c1}}</a></li>
                <li><a href="#">{{c2}}</a></li>
                <li><a href="#">{{c3}}</a></li>
            </ul>
        </b-nav-item>
            <span class="sub" v-bind:class="{'sub-true': fact2}">
                <b-nav-item class="nav-item" href="#" active ><span>{{c1}}</span></b-nav-item>
                <b-nav-item class="nav-item" href="#" active ><span>{{c2}}</span></b-nav-item>
                <b-nav-item class="nav-item" href="#" active ><span>{{c3}}</span></b-nav-item>
            </span>
        <b-nav-item class="nav-item" href="#" active ><span>COURSES</span></b-nav-item>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "nav",
  data() {
      return {
          fact1: false,
          fact2: false,
          aboutUs:[
              {info: "Who we are?"},
              {info: "Our achievements"},
              {info: "Our goals"},
          ],
          c1: "Course 1",
          c2: "Course 2",
          c3: "Course 3",

      }
  },
  methods: {
      dropDown(){
          this.fact = !this.fact;
          console.log("vue")
      }
  },
};
</script>

<style scoped>
    .nav{
        background: white;
        width: 100vw;
        max-width: 100%;
        height: 90px;
        display: flex;
        justify-content: space-around;
        align-items: center;
        padding: 0 50px;
        border-bottom: 1px solid #f0f0f0 ;
    }
    .logo{
        font-weight: 900;
        font-size: 30px;
    }
    .logo span{
        color: rgb(255, 123, 0);
        margin-left: -5px;
    }
    .nav-links{
        max-width: 600px;
        width: 100%;
        display: flex;
        justify-content: space-evenly;
        align-items: center;
    }
    .nav-item{
        color: #3f3a64;
        font-size: 14px;
        font-weight: 700;
        position: relative;
        height: 60px;
        display: flex;
        justify-content: center;
        align-items: center;
        text-decoration: none;
        transition: 1s;
    }
    .nav-item span{transition: .5s;}
    .nav-item:hover ul{
        opacity: 1;
        top: 100%;
        transition: .5s;
        z-index: 2;
    }
    .nav-item ul{
        z-index: -1;
        overflow: hidden;
        padding: 0;
        left: 50%;
        top: 140%;
        opacity: 0;
        transform: translateX(-35%);
        list-style-type: none;
        position: absolute;
        width: 150px;
        border-radius: 5px;
        border-top: 2px solid #20ad96 ;
        box-shadow: 0 0 5px rgb(216, 216, 216);
        transition: .5s;
    }
    .nav-item ul li a{ text-decoration: none;  color: #3f3a64;}
    .nav-item ul li{
        text-decoration: none;
        height: 40px;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        padding-left: 25px;
        font-weight: normal;
        border-bottom: 1px solid #e9e9e9 ;
        text-transform: capitalize;
        background: #fff;
    }
    .nav-item:hover span{
        color: #20ad96;
        transition: .5s;
    }
    .down{
        width: 10px;
        margin-left: 3px;
    }
    .nav-item ul li:hover {
        background: #20ad96;
    }
    .nav-item ul li:hover a{
        color: white;
    }
    .nav-item ul li:last-child{
        border: 0;
    }
    .sub{
        max-height: 0;
        overflow: hidden;
        transition: .5s;
        opacity: 0;
    }
    .sub-true{
        opacity: 1;
        overflow: unset;
        max-height: 180px;
        transition: 0.5s;
    }
    .sub span{
        font-weight: 400;
    }

   /*++++++++++++++++++++++++++++++++++++    NAV-MEDIA QUERY ++++++++++++++++++++++++++++++++++++       */
   @media screen and (max-width: 770px) {
    .nav{
        justify-content: center;
        flex-direction: column;
        height: auto;
       }
    .nav-links{
        justify-content: center;
        flex-direction: column;
    }
    .nav-item{
        justify-content: center;
        flex-direction: column;
    }
    .nav-item ul{
        display: none;
    }
   }
    @media screen and (min-width: 770px){
        .sub{
            display: none;
        }
    }

</style>