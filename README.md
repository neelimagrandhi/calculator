<html>

  <head>?

     <style>?

      body{?

       border: 3px solid black;?

        width: 240px;?

        height: 380px;?

        padding: 25px;?

        }?

button{?

    margin: 5px;?

    height: 40px;?

    width: 40px;?

  background-color: white;?

  border: 1px solid #c4c4c4;?

}?

#form{?

    width: 230px;?

height: 40px;?

}?

 table{?

      padding-left: 8px;?

   padding-top: 10px;?

}?

   </style>?

  <script>?

      function calc(ids){?

             form.value+=ids;?

      }?

      function calc1(){?

             form.value="";?

      }?

      function calc2(){?

        form.value =eval(form.value);?

      }?

    </script>?

  </head>?

  <body>?

    <form id="display">?

    <input type="text" id="form"/>?

    </form>?

    <table>?

      <tr>?

         <td><button type="button" id="1" onclick="calc(this.id)">1</button></td>?

         <td><button type="button" id="2" onclick="calc(this.id)">2</button></td>?

         <td><button type="button" id="3" onclick="calc(this.id)">3</button></td>?

        <td><button type="button" id="+" onclick="calc(this.id)">+</button></td>?

      </tr>?

      <tr>?

               <td><button type="button" id="4" onclick="calc(this.id)">4</button></td>?

               <td><button type="button" id="5" onclick="calc(this.id)">5</button></td>?

               <td><button type="button" id="6" onclick="calc(this.id)">6</button></td>?

                <td><button type="button" id="-" onclick="calc(this.id)">-</button></td>?

      </tr>?

      <tr>?

               <td><button type="button" id="7" onclick="calc(this.id)">7</button></td>?

               <td><button type="button" id="8" onclick="calc(this.id)">8</button></td>?

               <td><button type="button" id="9" onclick="calc(this.id)">9</button></td>?

               <td><button type="button" id="*" onclick="calc(this.id)">*</button></td>?

      </tr>?

      <tr>?

               <td><button type="button" onclick="calc1()" style="background-color:#f0595f;color: white;">c</button></td>?

               <td><button type="button" id="0" onclick="calc(this.id)">0</button></td>?

              <td><button type="button" id="." onclick="calc(this.id)">.</button></td>?

               <td><button type="button" id="/" onclick="calc(this.id)">/</button></td>?

      </tr>?

      <tr>?

        <td><button type="button"  id="sin" onclick="display.form.value=Math.sin(display.form.value)">sin</button></td>?

         <td><button type="button"  id="tan" onclick="display.form.value=Math.tan(display.form.value)">tan</button></td>?

        <td><button type="button"  id="cos" onclick="display.form.value=Math.cos(display.form.value)">cos</button></td>?

        <td><button type="button"  id="sqrt" onclick="display.form.value=Math.sqrt(display.form.value)">v</button></td>?

       ?</tr>?

      <tr>?

      <td><button type=button id="1/x" onclick="display.form.value=1/display.form.value">1/x</button></td>?

     ? <td><button type="button"  id="sqrt" onclick="display.form.value=Math.pow(display.form.value,2)">^</button></td>?

       <td><button type="button" id="equal" onclick="calc2()" style="background-color: #2e86c0;color: white;">=</button></td>?

       </tr>

     </table>?

   </body>?
</html>



calculator using angular:



app.component.html

<html>
  <body>
<h1>{{name}}</h1>
<div id="calc">
<input type="text" placeholder=""  id="form" value="{{result}}"/>
<table>
  <tr>
    <td> <button (click)="addToCalculation('7')">7</button></td>
     <td><button (click)="addToCalculation('8')">8</button></td>
     <td><button (click)="addToCalculation('9')">9</button></td>
     <td><button (click)="addToCalculation('/')">/</button></td>
  </tr>
  <tr>
    <td><button (click)="addToCalculation('4')">4</button></td>
    <td><button (click)="addToCalculation('5')">5</button></td>
    <td><button (click)="addToCalculation('6')">6</button></td>
 <td><button (click)="addToCalculation('*')">X</button></td>
  </tr>
  <tr>
    <td><button (click)="addToCalculation('1')">1</button></td>
    <td><button (click)="addToCalculation('2')">2</button></td>
 <td><button (click)="addToCalculation('3')">3</button></td>
    <td><button (click)="addToCalculation('-')">-</button></td>
  </tr>
  <tr>
    <td> <button (click)="addToCalculation('0')">0</button></td>
    <td> <button (click)="addToCalculation('.')">.</button></td>
    <td><button (click)="getTotal()">=</button></td>
  <td><button (click)="addToCalculation('+')">+</button></td>
  </tr>
  <tr>
  <td><button (click)="calculates('c')">c</button></td>
  <td><button (click)="calls('^')">^</button></td>
   <td><button (click)="calls('1/x')">1/x</button></td>
    <td><button (click)="calls('tan')">tan</button></td>
  </tr>
    <tr>
  <td><button (click)="calls('sin')">sin</button></td>
  <td><button (click)="calls('cos')">cos</button></td>
   <td><button (click)="calls('cot')">cot</button></td>
    <td><button (click)="calls('sqrt')">sqrt</button></td>
  </tr>
</table>
</div>
  </body>
  </html>



app.component.css

#calc{
       border: 3px solid black;
        width: 260px;
        height: 380px;
        padding: 20px;
        }
button{
    margin: 5px;
    height: 40px;
    width: 50px;
    font-size: 20px;
}
#form{
    width: 230px;
height: 40px;
}


app.component.ts

import { Component } from '@angular/core';

@Component({
  selector: 'my-app',
  templateUrl: './app.component.html',
  styleUrls: [ './app.component.css' ]
})
export class AppComponent  {
     
      name="Calculator app";
      result="";
      addToCalculation(value){
     
         this.result+=value;
       }
      getTotal(){
         this.result=eval(this.result);
      }
      calculates(){
        this.result="";
      }
      calls(vals){
        if(vals=="^"){
       this.result=Math.pow(this.result,2);
        }
     else if (vals=="1/x"){
       this.result=1/this.result;
     }
     else if(vals=="tan"){
       this.result=Math.tan(this.result);
     }
     else if(vals=="sin"){
       this.result=Math.sin(this.result);
     }
     else if(vals=="cos"){
       this.result=Math.cos(this.result);
     }
     else if(vals=="cot"){
       this.result=Math.cot(this.result);
     }
     else if(vals=="sqrt"){
       this.result=Math.sqrt(this.result);
     }
      }
}
