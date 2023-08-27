<script lang="ts">
export let CssOutput:string = '';
</script>






<textarea name="" id="" cols="60" rows="20"  bind:value={CssOutput}></textarea>



<style>
      textarea{
    resize: none;
      
    font-size: 12px;
    line-height: 1;
    font-family: Monaco,monospace;
    color: #b1b6bb;
    background-color:#0b0c0c;
    box-shadow: 0 1px 3px 0 rgb(0 0 0 / 10%), 0 1px 2px 0 rgb(0 0 0 / 6%);
    border: 0;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
  
    border: 0.1px;
    border-color: #ffffff36;
    border-style: solid;
  
    outline: none;
  
    border-radius: 6px;
    line-height: 1.4;
    height: 175px;
    width: 98%;
  }
  textarea{
    overflow-x: hidden;
      --scrollbar-background: #0b0c0c;
    }
  
  
  textarea::-webkit-scrollbar {    
    /* background: #18181c;
    width: 15px; */
    background: #18181c00;
   
  
  }
  
  textarea::-webkit-scrollbar-thumb {
    background-color:#d1d1d13e;
    border-radius: 2px;
   
  }
</style>