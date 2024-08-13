<script lang="ts">
    import SquareRoot from '$lib/SquareRoot.svelte';
    import Minus from '$lib/icon/Minus.svelte';
    import Division from'$lib/icon/Division.svelte';
    import PlusIcon from '$lib/icon/PlusIcon.svelte';
    import MultiplyIcon from '$lib/icon/MultiplyIcon.svelte';
    import BackSpace from '$lib/icon/BackSpace.svelte';'$lib/icon/BackSpace.svelte';
     function oddToequation(value:string) {
        equation += value
     }
     function backSpace (){
        switch ( equation = equation.substring(0,equation.length-1)){
            case ' * ':
            case ' + ':
            case ' / ':
            case ' - ':
            equation.substring(equation.length - 3, equation.length);

            break;
            default:
            equation = equation.substring(0,equation.length -1);
     }

        }
          
     
     function delet (){
        equation = '';
     }
     function equal(){
         equation = eval(equation);
     }
    let equation:string = "";

</script>



<svelte:head>
    <title>
        الة حاسبة
    </title>
</svelte:head>


<div class="bg-white h-[29rem] w-[16rem] 
rounded-3xl grid grid-cols-4 gap-1 p-5 font-semibold text-xl shadow-xl">

<div class="bg-blue-500 rounded-2xl col-span-4 min-h-12 
     flex items-center px-2 mb-2 text-white break-all ">
{equation}

</div>
    
   
    <button class="bg-slate-200 hover:bg-slate-200/85 text-black" on:click={()=> delet ()}>AC</button>
  
    <!-- Back Space -->
    <button class="bg-slate-200 hover:bg-slate-200/85"on:click={()=> backSpace ()}>
        <BackSpace/>
    </button>
    <button class="bg-slate-200 hover:bg-slate-200/85"on:click={()=> oddToequation (' /100')}>%</button>

    <button class=" bg-green-500 hover:bg-green-500/85 text-white"on:click={()=> oddToequation (' + ')} >
        <PlusIcon/>
    </button>
    
    <button on:click={()=> oddToequation ('7')}>7</button>
    <button on:click={()=> oddToequation ('8')} >8</button>
    <button on:click={()=> oddToequation ('9')}>9</button>
    <!-- Minus -->
    <button class="bg-red-500 hover:bg-red-500/85 text-white"on:click={()=> oddToequation (' - ')} >
    <Minus/>
    </button>
    <button on:click={()=> oddToequation ('4')}>4</button>
    <button on:click={()=> oddToequation ('5')} >5</button>
    <button on:click={()=> oddToequation ('6')}>6</button>
    <!-- division -->
    <button class="bg-blue-500 hover:bg-blue-500/85 text-white"on:click={()=> oddToequation (' / ')}>
        <Division/>
    </button>
    <button on:click={()=> oddToequation ('1')}>1</button>
    <button on:click={()=> oddToequation ('2')} >2</button>
    <button on:click={()=> oddToequation ('3')}>3</button>
    <button class="bg-yellow-400 hover:bg-yellow-400/85 text-white" on:click={()=> oddToequation (' * ')}>
     <MultiplyIcon/>
    </button>
    <button on:click={()=> oddToequation ('.')}>.</button>
    <button on:click={()=> oddToequation ('0')}>0</button>
    <button  class="col-span-2 w-full bg-slate-200 hover:bg-slate-200/75"on:click={()=> equal ()}>=</button>
   
</div>
