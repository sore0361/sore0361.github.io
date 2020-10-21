

<html>
  <head>
    <meta charset="UTF-8" />
    <title>C.H. Robinson Interview Project</title>
  </head>
  <body onload="JavaScript:clearData()">


    <h2>C.H. Robinson Interview Project</h2>
    <p>Enter a county code to see the path needed to travel to the country.</p>
    <!-- <p>React is loaded as a script tag.</p> -->


    <form name="MyForm" > <!--onsubmit="event.preventDefault(); myValidation()">  -->
      <input type="text" id="input" name="input" placeholder="Write your country code..." />
      <button name="button" id="buttonid" onclick="save()">Submit</button>
    </form>


    <p id="output"></p>

<script type="text/javascript">

    function clearData() {
        localStorage.clear();
        document.getElementById("input").value.clear();
        document.getElementById("output").innerHTML.clear();
    }

    //function myValidation() {
    //  if(document.getElementById("input").value.len < 3)
    //  {
    //      return;
    //  }
   // }

    function save(){
      var storedItem = localStorage.getItem("storedItem");
      var Item = document.getElementById("input").value;
      storedItem = localStorage.setItem("storedItem", Item);
      checkCountry();
    }

     void function checkCountry() {
        ///var coder = "MEX";///document.CodeForm.name.value;

        var coder = localStorage.getItem("storedItem");//document.getElementById("input");
        //document.write(coder.value);
        //var codeVal = coder.value;

        //alert("COuntry code " + coder);

        if(coder == "CAN" || coder == "can") {
          //window.write("CAN");
          document.getElementById("output").innerHTML = "USA, CAN";
        }

        else if(coder == "USA" || coder ==  "usa") {
          document.getElementById("output").innerHTML = "USA";
        }

        else if(coder == "MEX" || coder == "mex") {
          document.getElementById("output").innerHTML = "USA, MEX";
        }

        else if(coder == "BLZ" || coder == "blz") {
          document.getElementById("output").innerHTML = "USA, MEX, BLZ";
        }

        else if(coder == "GTM" || coder == "gtm") {
          document.getElementById("output").innerHTML = "USA, MEX, GTM";
        }

        else if(coder == "SLV" || coder == "slv") {
          document.getElementById("output").innerHTML = "USA, MEX, GTM, SLV";
        }
        
        else if(coder == "HND" || coder == "hnd") {
          document.getElementById("output").innerHTML = "USA, MEX, GTM, HND";
        }

        else if(coder == "NIC" || coder == "nic") {
          document.getElementById("output").innerHTML = "USA, MEX, GTM, HND, NIC";
        }

        else if(coder == "CRI" || coder == "cri") {
          document.getElementById("output").innerHTML = "USA, MEX, GTM, HND, NIC, CRI";
        }

        else if(coder == "PAN" || coder == "pan") {
          document.getElementById("output").innerHTML = "USA, MEX, GTM, HND, NIC, CRI, PAN";
        }

        else if(coder.length < 3){
          window.alert("You have not entered a valid country code. Try again.");
        }
    } ();
    //toggle();
    </script>

   <!-- <script>
    var storedItem = localStorage.getItem("storedItem");

    function save() {
      var Item = document.getElementById("input").value;
      localStorage.setItem("storedItem", Item);
      document.getElementById("savedText").innerHTML = Item + " SAVED";
    }

    function get() {
      localStorage.getItem("storedItem");
      document.getElementById("openedText").innerHTML = storedItem + " entered";
    }

    </script> -->


  </body>
</html>
