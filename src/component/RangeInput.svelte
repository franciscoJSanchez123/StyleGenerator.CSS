<script lang="ts">
  
    
    export let range:number = 1;
    export let label:string = '';
    export let max:number = 100;
    export let min:number = 0;
   
</script>



<label for="range-input">{label}</label>
<div  class="range">
    
    <input type="range" id="range-input" bind:value={range} {max} {min} >{range}px
    
</div>



<style> 
label{
  color: #fff;
  font-weight: 700;
}
 input{
    width: 80%
}
.range{
    display: flex;
      flex-direction: row;
      justify-content: space-between;
      padding-bottom: 10%;
      padding-top: 9px;
      
  }




    input[type=range] {
    -webkit-appearance: none;
    appearance: none; 
    width: 100%;
    cursor: pointer;
    outline: none;
    overflow: hidden;
    border-radius: 16px;
  }
  
  input[type=range]::-webkit-slider-runnable-track {
    height: 15px;
    background: #ccd0db;
    border-radius: 16px;
  }
  
  input[type=range]::-moz-range-track {
    height: 15px;
    background: #ccd0db;
    border-radius: 16px;
  }
  
  input[type=range]::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none; 
    height: 15px;
    width: 15px;
    background-color: #fff;
    border-radius: 50%;
    border: 2px solid #6bdbce;
    box-shadow: -407px 0 0 400px #6bdbce;
  }
  
  input[type=range]::-moz-range-thumb {
    height: 15px;
    width: 15px;
    background-color: #fff;
    border-radius: 50%;
    border: 1px solid #f50;
    box-shadow: -407px 0 0 400px #6bdbce;
  }
  </style>