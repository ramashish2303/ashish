
<!DOCTYPE html>
<html>
    <head>
        <style>
            body{
                background:lightGray;
            }
            
            .countdown{
                postion:absolute;
                top:50%
                left:50%;
                transaform: translateX(-50%), translateY(-50%);
                text-align:center;
                background:#ddd;
                border: 1px solid #999;
                padding:10px;
                box-shadow: 0 0 5px 3px #ccc;
            }
            .info{
                font-size:80px;
            }
            
        </style>
    </head>
<body>
  <table class="countdown" border="1">
      <tr>
          <td colspan="4">Going Home in next:</td>
      </tr>
      <tr class="info">
          <td id="days">120</td>
           <td id="hours">15</td>
            <td id="minutes">40</td>
             <td id="seconds">12</td>
      </tr>
      <tr>
          <td>Days</td>
          <td>Hours</td>
          <td>Minutes</td>
          <td>Seconds</td>
      </tr>
      
  </table>  
    <script>
        function countdown(){
            var now= new Date();
            var eventDate= new Date(2018,08,11);
            var currentTime= now.getTime();
            var remTime= eventDate.getTime();
            var rem= remTime - currentTime;
            
            var s= Math.floor(rem/1000);
            var m=Math.floor(s/60);
            var h= Math.floor(m/60);
            var d= Math.floor(h/24);
            
            h %=24;
            m%=60;
            s%=60;
            
            h= (h<10) ? "0" + h : h;
            m= (m<10) ? "0" + m : m;
            s= (s<10) ? "0" + s : s;
            
            document.getElementById("days").textContent=d;
            document.getElementById("hours").textContent=h;
            document.getElementById("minutes").textContent=m;
            document.getElementById("seconds").textContent=s;
            
            setTimeout(countdown,1000);
            
            
        }
        
        countdown();
        
    </script>
</body>
</html>
