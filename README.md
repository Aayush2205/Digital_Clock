# Digital_Clock
## Code used for this Digital clock

<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>
    <meta http-equiv='X-UA-Compatible' content='IE=edge'>
    <title>Digital Clock</title>
    <meta name='viewport' content='width=device-width, initial-scale=1'>
    <link rel='stylesheet' type='text/css' media='screen' href='main.css'>
    <script src='main.js'></script>
    <style>
        body{
            background-color: black;
        }  
        .Clock{
            position: absolute;
            color: red;
            top: 50%;
            left: 50%;
            transform: translateX(-50%) translateY(-50%);
            font-size: 70px;
            font-family: Orbitron;
            letter-spacing: 7px;
        }
    </style>
</head>
<body>
   <div id="DigitalClock" class= "Clock"></div> 
   <script type="text/javascript">
    function showTime(){
        var date = new Date();
        var h = date.getHours();
        var m = date.getMinutes();
        var s = date.getSeconds();
        var session="AM";
        if(h==0){
            h=12; // converting to 12 hr format
        }
        if(h>12){
            h=h-12; // converting to 12 hr format
            session="PM";
        }
        if(h<10){
            h="0"+ h;
        }
        if(m<10){
            m="0"+ m;
        }
        if(s<10){
            s="0"+ s;
        }
        document.getElementById("DigitalClock").innerHTML= h + ":" + m + ":" + s + "" + session; 
        setTimeout(showTime,1000); //repeats the function every 1000 milliseconds
    }
    showTime();
    </script>
</body>
</html>
