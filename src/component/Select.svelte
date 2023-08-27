<script lang="ts">
     export let options:string[] = [];
     export let label:string = '';
    
     export let index = 0;
     export let value;
     $: {
    value = options[index];
  }



</script>


<label for="selectOptions">{label}</label>
<div class="select">
  <select  
      id="selectOptions"
     bind:value={index} 
   
     >
     {#each options as option, i}
     <option  value={i}  id="selectOption">{ option }</option>
    {/each}
  </select>
</div>




<style>

label{

  font-weight: 700;
}
  select {
    -webkit-appearance:none;
    -moz-appearance:none;
    -ms-appearance:none;
    appearance:none;
    outline:0;
    box-shadow:none;
    border:0!important;
    background: #ccd0db;
    background-image: none;
    flex: 1;
    padding: 0 .5em;
    color: #000;
    cursor:pointer;
    font-size: 18px;
    font-family: 'Open Sans', sans-serif;
 }
 select::-ms-expand {
    display: none;
 }
 .select {
    position: relative;
    display: flex;
    /* width: 20em; */
    height: 46px;
    line-height: 46px;
    background: #ccd0db;
    overflow: hidden;
    border: 0.1px;
    border-color: #ffffff36;
    border-style: solid;
    border-radius: 6px;
    margin-top: 9px;
    
    margin-bottom: 20px;

 }
 .select::after {
    content: '\25BC';
    position: absolute;
    top: 0;
    right: 0;
    padding: 0 1em;
    background: #0b0c0c;
    color: #ccd0db;
    cursor:pointer;
    pointer-events:none;
    transition:.25s all ease;
 }
 .select:hover::after {
    color: #b8c2dd;
 }
option{
  color: #000;
}




</style>