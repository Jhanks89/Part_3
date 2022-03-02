# Temperture Converter
<br>
<section> <div class="row"> <form name="myform"> <div class="one-half column"> <p>Input a temperature!</p> <table> <thead> <tr> <th style="text-align:left">Unit</th> <th style="text-align:center">Value</th> <th style="text-align:center"><input type="button" value="Reset" id="reset"></th> </tr> </thead> <tbody> <tr> <td style="text-align:left">Celcius</td> <td style="text-align:center"><input type="number" id="celcius" name="celcius" min="-1000" max="1000" required=""></td> <td style="text-align:center"><input type="button" class="button-primary" onclick="calc(&quot;ctof&quot;)" value="to ºF"></td> </tr> <tr> <td style="text-align:left">Farenheit</td> <td style="text-align:center"><input type="number" id="farenheit" name="farenheit" min="-1000" max="1000" required=""></td> <td style="text-align:center"><input type="button" class="button-primary" onclick="calc(&quot;ftoc&quot;)" value="to ºC"></td> </tr> </tbody> </table> </div> <div class="one-half column"> <br><br> <div id="messages"></div> <br> </div> </form> </div> </section>
<script>const displayResults=(e="",t=0,s=32)=>{document.getElementById("messages").textContent=e,document.forms.myform.elements.celcius.value=t.toFixed(0),document.forms.myform.elements.farenheit.value=s.toFixed(0)};function calc(e){const t="You have to enter a numeric value.";let s={celcius:parseFloat(document.forms.myform.elements.celcius.value),farenheit:parseFloat(document.forms.myform.elements.farenheit.value),tof:()=>1.8*s.celcius+32,toc:()=>5/9*(s.farenheit-32)};"ctof"==e?Number.isNaN(s.celcius)?displayResults(t,NaN,NaN):displayResults("",s.celcius,s.tof()):"ftoc"==e&&(Number.isNaN(s.farenheit)?displayResults(t,NaN,NaN):displayResults("",s.toc(),s.farenheit))}document.getElementById("reset").addEventListener("click",(()=>{displayResults("",0,32)})),displayResults()</script>
