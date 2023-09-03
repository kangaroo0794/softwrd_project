<script>

</script>

<link rel="stylesheet" href="global.css">
<style>
    @import "tailwindcss/base";
    @import 'tailwindcss/components';
    @import 'tailwindcss/utilities';

    .wrapper {
        display: flex;
        justify-content: center; 
        align-items: center; 
        height: 100vh; 
        margin: 0;
        padding: 0;
    }
    .circle1 {
        width: 185px;
        height: 185px;
        background: #ffffce;
        border-radius: 50%;
        border: none;
        position: absolute;
        top: 515px;
        left: 665px;
        z-index: 1;
    }
    .rose-box {
        width: 100%; 
        max-width: 300px; 
        height: 400px; 
        background-color: #FADADD;
        border: none;
        border-radius: 0;
        margin: 0; /* Remove margin */
        padding: 0px; /* Remove padding */
        position: absolute;
        top: 105px;
        left: 608px;
    }

    .yellow-box {
        width: 100%; 
        max-width: 300px; 
        height: 400px; 
        background-color: #ffffce;
        border: none;
        border-radius: 0;
        margin: 0; /* Remove margin */
        padding: 0px; /* Remove padding */
        position: absolute;
        top: 405px;
        left: 608px;
    }
    
    .dark-blue-box{
        width: 250px; 
        height: 250px; 
        background-color: #1e3f66;
        border: none;
        border-radius: 0;
        margin: 0; /* Remove margin */
        padding: 0px; /* Remove padding */
        position: absolute;
        top: 485px;
        left: 635px;
        z-index: 0;
    }
    .mountain {
      width: 0;
      height: 0;
      border-left: 80px solid transparent;
      border-right: 80px solid transparent;
      border-bottom: 80px solid #fe5f55;
      position: absolute;
      top: 600px;
      left: 665px;
      transform: rotate(deg);
      z-index: 2;
    }
   
    
</style>

<div class="wrapper">
    <div class="grid-container">
        <div class="grid-item left-box">
            <div>
                <div class="rose-box"></div>
            </div>
            <div>
                <div class="circle1"></div>
                <div class="yellow-box"></div>
                <div class="dark-blue-box"></div>
                <div class="mountain"></div>
            </div>
        </div>
    </div>
</div>