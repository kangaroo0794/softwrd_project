<script>

</script>

<link rel="stylesheet" href="global.css">
<style>
    @import "tailwindcss/base";
    @import 'tailwindcss/components';
    @import 'tailwindcss/utilities';

    .wrapper {
        width: 100%;
        height: 100%;
        overflow: hidden;
        display: flex;
        flex-wrap: wrap;
        align-items: center;
        justify-content: center;
        margin: 0; 
        padding: 0;  
    }
    
    .box {
        width: 100%; 
        max-width: 200px;
        height: 300px; 
        background-color: #3498db;
        border: none;
        border-radius: 0;
        margin: 0; 
        padding: 0;
        position: absolute;
        top: 5px;
        left: 8px;

    }

    .teal-box {
        width: 100%; 
        max-width: 200px; 
        height: 200px; 
        background-color: #26A69A;
        border: none;
        border-radius: 0;
        margin: 0; 
        padding: 0px; 
        position: absolute;
        top: 305px;
        left: 8px;
    }
    .fuchsia-box {
        width: 100%; 
        max-width: 600px; 
        height: 100px; 
        background-color: fuchsia;
        border: none;
        border-radius: 0;
        margin: 0; 
        padding: 0px; 
        position: absolute;
        top: 505px;
        left: 8px;
    }
    .rose-box {
        width: 100%; 
        max-width: 400px; 
        height: 500px; 
        background-color: #FADADD;
        border: none;
        border-radius: 0;
        margin: 0; 
        padding: 0px; 
        position: absolute;
        top: 5px;
        left: 208px;
    }

    .turquoise-box {
        width: 100%; 
        max-width: 600px; 
        height: 200px; 
        background-color: turquoise;
        border: none;
        border-radius: 0;
        margin: 0; 
        padding: 0px; 
        position: absolute;
        top: 5px;
        left: 608px;
    }
    .emerald-box {
        width: 100%; 
        max-width: 200px; 
        height: 400px; 
        background-color: #00ff9d;
        border: none;
        border-radius: 0;
        margin: 0; 
        padding: 0px; 
        position: absolute;
        top: 205px;
        left: 1008px;
    }
    
    .yellow-box {
        width: 100%; 
        max-width: 400px; 
        height: 400px; 
        background-color: #ffffce;
        border: none;
        border-radius: 0;
        margin: 0; 
        padding: 0px; 
        position: absolute;
        top: 205px;
        left: 608px;
    }

    .dark-blue-box{
        width: 250px; 
        height: 250px; 
        background-color: #1e3f66;
        border: none;
        border-radius: 0;
        margin: 0; 
        padding: 0px; 
        position: absolute;
        top: 285px;
        left: 685px;
        z-index: 0;
    }
    .circle1 {
        width: 200px;
        height: 200px;
        background: #ffffce;
        border-radius: 50%;
        border: none;
        position: absolute;
        top: 310px;
        left: 708px;
        z-index: 1;
    }
    .mountain {
      width: 0;
      height: 0;
      border-left: 80px solid transparent;
      border-right: 80px solid transparent;
      border-bottom: 80px solid #fe5f55;
      position: absolute;
      top: 380px;
      left: 728px;
      transform: rotate(deg);
      z-index: 2;
    }
    
</style>

<div class="wrapper">
    <div class="grid-container">
        <div class="grid-item left-box">
            <div>
               <div>
                    <div>
                        <div class="box"></div>
                    </div>
                   <div>
                       <div class="teal-box"></div>
                   </div>
               </div>
                <div>
                    <div class="rose-box"></div>
                </div>
            </div>
            <div>
                <div class="fuchsia-box"></div>
            </div>
        </div>
        <div class="grid-item right-box">
            <div>
                <div class="turquoise-box"></div>
            </div>
            <div>
                <div>
                    <div class="yellow-box"></div>
                    <div class="circle1"></div>
                    <div class="dark-blue-box"></div>
                    <div class="mountain"></div>
                </div>
                <div>
                    <div class="emerald-box"></div>
                </div>
            </div>
        </div>
    </div>
</div>
