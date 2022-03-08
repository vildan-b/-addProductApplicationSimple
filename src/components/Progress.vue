<template>
 <div class="progress">
      <div class="progress-bar bg-info" role="progressbar" :style="{width: progress + '%'}" aria-valuenow="50" aria-valuemin="0" aria-valuemax="100">
        {{productTotal }} /10
      </div>
    </div>

</template>

<script>
import {eventBus} from '../main';

export default{
  data(){
    return{
      productTotal: 0,
      progress: 0
    }
  },

 created(){
   eventBus.$on("productTotal", (productTotal) => {
     this.productTotal = productTotal;
     this.progress = this.productTotal*10;
     console.log(productTotal)
   }
    );
 } 
}</script>