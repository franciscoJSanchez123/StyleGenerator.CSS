<script lang="ts">
import RangeInput from './component/RangeInput.svelte';
import ColorInput from './component/ColorInput.svelte';
import Select from './component/Select.svelte';
import TextTarea from './component/TextTarea.svelte';
import HeroSection from './component/HeroSection.svelte';
import Header from './component/Header.svelte';
import Footer from './component/Footer.svelte';

let thumbColor:string = "#6bdbce";

let thumbHeight:number = 36;

let thumbWidth:number = 36;

let thumbBorderRadius:number = 18;

let thumbBordercolor:string = "#ffffff";

let thumbBorderWidth:number = 1;

let trackColor:string = "#d9dade";

let trackHeight:number = 8.4;

let trackBorderRadius:number = 1;

let trackBorderWidth:number = 0.2;

let trackBordercolor:string = "#ffffff";

let thumbColorStyle2:string = "#ffffff";

let selected:string='Style 1';
let inputStyles:string[]=['Style 1', 'Style 2', 'Style 3']



$: style = `
<style> 
  #range1 { 
    width: 100%;
    margin: ${5+thumbHeight/2}px 0;
    background-color: transparent;
    -webkit-appearance: none;
  }
  #range1:focus {
    outline: none;
  }
  #range1::-webkit-slider-runnable-track {
    background: ${trackColor};
    border:  ${trackBorderWidth}px solid ${trackBordercolor};
    border-radius: ${trackBorderRadius}px;
    width: 100%;
    height: ${trackHeight}px;
    cursor: pointer;
  }
  #range1::-webkit-slider-thumb {
    margin-top: ${((trackHeight/2)-(thumbHeight/2))-trackBorderWidth}px;              
    width: ${thumbWidth}px;   
    height: ${thumbHeight}px;
    background: ${thumbColor};
    border: ${thumbBorderWidth}px solid  ${thumbBordercolor};
    border-radius:  ${thumbBorderRadius}px;
    cursor: pointer;
    -webkit-appearance: none;
  }
  #range1:focus::-webkit-slider-runnable-track {
    background:  ${trackColor};
  }
  #range1::-moz-range-track {
    background:  ${trackColor};
    border: ${trackBorderWidth}px solid ${trackBordercolor};
    border-radius: ${trackBorderRadius}px;
    width: 100%;
    height:${trackHeight}px;
    cursor: pointer;
  }
  #range1::-moz-range-thumb {
    width: ${thumbWidth}px;
    height: ${thumbHeight}px;
    background: #f4ffff;
    border: ${thumbBorderWidth}px solid ${thumbBordercolor};
    border-radius: ${thumbBorderRadius}px;
    cursor: pointer;
  }
  #range1::-ms-track {
    background: transparent;
    border-color: transparent;
    border-width: ${thumbHeight-14.8}px 0;
    color: transparent;
    width: 100%;
    height: ${trackHeight}px;
    cursor: pointer;
  }
  #range1::-ms-fill-lower {
    background:  ${trackColor};
    border: ${trackBorderWidth}px solid ${trackBordercolor};
    border-radius: ${trackBorderRadius}px;
  }
  #range1::-ms-fill-upper {
    background:  ${trackColor};
    border: ${trackBorderWidth}px solid ${trackBordercolor};
    border-radius:${trackBorderRadius}px;
  }
  #range1::-ms-thumb {
    width:${thumbWidth}px;
    height: ${thumbHeight}px;
    background: #f4ffff;
    border: ${thumbBorderWidth}px solid ${thumbBordercolor};
    border-radius:${thumbBorderRadius}px;
    cursor: pointer;
    margin-top: 0px;
    /*Needed to keep the Edge thumb centred*/
  }
  #range1:focus::-ms-fill-lower {
    background:  ${trackColor};
  }
  #range1:focus::-ms-fill-upper {
    background:  ${trackColor};
  }
  @supports (-ms-ime-align:auto) {
    #range1 {
      margin: 0;
     
    }
  } 
</style>`;



$: style2 = `
<style> 
  #range1 {  
    accent-color: ${thumbColor};
    width: 100%; 
  }
</style>`;



$: style3 = `
<style> 
#range1 {
  -webkit-appearance: none;
  appearance: none; 
  width: 100%;
  cursor: pointer;
  outline: none;
  overflow: hidden;
  border-radius: 16px;
}
#range1::-webkit-slider-runnable-track {
  height: 15px;
  background: ${trackColor};
  border-radius: 16px;
}
#range1::-moz-range-track {
  height: 15px;
  background: ${trackColor};
  border-radius: 16px;
}
#range1::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none; 
  height: 15px;
  width:15px;
  background-color: ${thumbColorStyle2};
  border-radius: 50%;
  border: 2px solid ${thumbColor};
  box-shadow: -407px 0 0 400px ${thumbColor};
}
#range1::-moz-range-thumb {
  height: 15px;
  width: 15px;
  background-color: #fff;
  border-radius: 50%;
  border: 1px solid #f50;
  box-shadow: -407px 0 0 400px ${thumbColor};
}
</style>`;

</script>



{#if selected==='Style 1'}
  {@html style}
{:else if selected==='Style 2'}
  {@html style2}
{:else if selected==='Style 3'}
  {@html style3}
{/if}


<main>
 
  <Header/>
  <HeroSection/>
  <div class="main-section">
      <div class="view">
        <div class="view-container">
            <header>
              Select a style for your range input
            </header>
            <div>
              <Select bind:value={selected} options={inputStyles} label={'Select a style'}/>
            </div>
        
            <div class="preview">
              <p>Preview</p>
              <input type="range"  id="range1" >
            </div>
        
            <div class="output">
              <p>CSS Ouput</p>
              {#if selected==='Style 1'}
                <TextTarea CssOutput={style.replace(/#range1/g, 'input[type=range]').split('<style>').join('').split('</style>').join('')}/>
              {:else if selected==='Style 2'}
                <TextTarea CssOutput={style2.replace(/#range1/g, 'input[type=range]').split('<style>').join('').split('</style>').join('')}/>
              {:else if selected==='Style 3'}
                <TextTarea CssOutput={style3.replace(/#range1/g, 'input[type=range]').split('<style>').join('').split('</style>').join('')}/>
              {/if}
            </div>
        </div>
    </div>
    <div class="control">
      

      
      <div class="control-container">
        <header>
          Cuztomize
        </header>
        
        {#if selected==='Style 1'}
          <div>
              <ColorInput bind:color={thumbColor} label={'Thumb Color'} for_id={'Thumb-Color'}/>
              
              <RangeInput bind:range={thumbHeight} label={'Thumb Height'} />
            
              <RangeInput bind:range={thumbWidth} label={'Thumb Width'} />

              <RangeInput bind:range={thumbBorderRadius} label={'Thumb Border-Radius'} />

              <ColorInput bind:color={thumbBordercolor} label={'Thumb Border color'} for_id={'Thumb-border-color'}/>
          
              <RangeInput bind:range={thumbBorderWidth} label={'Thumb Border Width'} max={10}/>

          </div>
          <hr>
          <div>
          
            <ColorInput bind:color={trackColor} label={'Track Color'} for_id={'Track-Color'}/>

            <RangeInput bind:range={trackHeight} label={'Track Height'} />

            <RangeInput bind:range={trackBorderRadius} label={'Track Border-Radius'} />

            <RangeInput bind:range={trackBorderWidth} label={'Track Border Width'} min={0} max={10}/>

            <ColorInput bind:color={trackBordercolor} label={'Track border Color'} for_id={'track-border-color'}/>

          </div>
        
        {:else if selected==='Style 2'}

            <div>
              <ColorInput bind:color={thumbColor} label={'Thumb Color'} for_id={'Thumb-Color'}/>
            </div>



      
        {:else if selected==='Style 3'}
            <div>
              <ColorInput bind:color={thumbColorStyle2} label={'Thumb Color'} for_id={'Thumb-Color'}/>
              <hr>
              <ColorInput bind:color={thumbColor} label={'Track 1 Color'} for_id={'Track1-Color'}/>
              <ColorInput bind:color={trackColor} label={'Track 2 Color'} for_id={'Track2-Color'}/>
             
            </div>
        {/if}
      </div>
      
        
    </div>
  </div>
<Footer/>
</main>



<style>
main{

  height: 100%;
}
.main-section{
  display: flex;
  flex-direction: row;
  justify-content: center;
}
.view{
  background-color: #EEEEEE;
  width: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2%;
  height: 100vh;
  position: sticky;
  top: 0%;
}
.view-container{
  width: 70%;

  display: flex;
  flex-direction: column;
  justify-content: center;
}
.view-container header{
  font-weight: 700;
  padding-top: 20px;
  padding-bottom: 40px;
  font-size: 1.5em;
  color:#b8c2dd
}
.preview{
  padding-top: 37px;
  padding-bottom: 37px;
  font-weight: 700;
}
.output{
  font-weight: 700;
}
.control{
  background-color: #b8c2dd;
  width: 50%;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 2%;
}
.control-container{
  width: 70%;

  display: flex;
  flex-direction: column;
  justify-content: center;
}
.control-container header{
  font-weight: 700;
  padding-top: 20px;
  padding-bottom: 40px;
  font-size: 1.5em;
  color: #fff;
}

hr{
  width: 100%;
  height: 1px;
    background-color: white;
    margin-bottom: 54px;
    margin-top: 40px;
}

@media only screen and (max-width: 900px){

  .main-section{
 
  flex-direction: column;

}
    .view{

      width:96%;
      position: inherit;
    }

    .control{
  
  width: 96%;

}
  
  }


</style>
