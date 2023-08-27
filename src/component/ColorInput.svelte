<script lang="ts">
  
    
    export let color:string = '1';
    export let label:string = '';
    export let for_id:string="";
   
</script>






<label for={for_id}>{label}</label>
<div class="color-inputs">
    <div id="color-text">
      <input type="text"  bind:value={color}>
    </div>
     <div >
      <input class="color" type="color" id={for_id}  bind:value={color}  />
    </div> 
</div>



<style> 

label{
  color: #fff;
  font-weight: 700;
  
}
.color-inputs{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    padding-top: 9px;
    padding-bottom: 10%;
  }

  #color-text{
    width: 80%;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  #color-text input{
    width: 100%;
    margin: 0;
    height: 46px;
    text-indent: 15px;
    font-size: inherit;
    line-height: 1;
    font-family: inherit;
    color: #000;
    background-color: #ccd0db;
    box-shadow: 0 1px 3px 0 rgb(0 0 0 / 10%), 0 1px 2px 0 rgb(0 0 0 / 6%);
  
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    border: 0.1px;
    border-color: #ffffff36;
    border-style: solid;
  
    outline: 1;
    border-radius: 6px;
    padding: 0;
    
  }


  
.color {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background-color: transparent;
    width: 45px;
    height: 45px;
    border: none;
    cursor: pointer;
  }
  .color::-webkit-color-swatch {
    border-radius: 50%;
    border: 1px solid rgb(255, 255, 255);
  }
  .color::-moz-color-swatch {
    border-radius: 50%;
    border: 1px solid #ffffff;
  }

</style> 