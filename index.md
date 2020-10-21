
<!-- this is the latest version including a React button component -->

<html>
  <head>
    <!--<style type="style.css"/>-->
    <meta charset="UTF-8" />
    <title>C.H. Robinson Interview Project</title>
  </head>
  <body onload="JavaScript:clearData()">

    <h2>C.H. Robinson Interview Project</h2>
    <p>Enter a county code to see the path needed to travel to the country.</p>
    <!-- <p>React is loaded as a script tag.</p> -->

    <!-- Load React. -->
    <!-- Note: when deploying, replace "development.js" with "production.min.js". -->
    <script src="https://unpkg.com/react@16/umd/react.production.min.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@16/umd/react-dom.production.min.js" crossorigin></script> 
    <script src="https://cdnjs.cloudflare.com/ajax/libs/babel-standalone/6.21.1/babel.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.4.2/react.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/react/15.4.2/react-dom.js"></script>



    <div id="blockContainer">
    <!-- Load our React component. -->
    <form name="MyForm" > <!--onsubmit="event.preventDefault(); myValidation()">  -->
      <input type="text" id="input" name="input" placeholder="Write your country code..." />
      <!--<button name="button" id="buttonid" onclick="save()">Submit</button>-->
    </form>

    <!-- We will put our React component inside this div. -->
    <div id="enter_button_container"></div> 
  </div>
    <script type="text/babel">
       const e = React.createElement;

        class EnterButton extends React.Component {
          constructor(props) {
            super(props);
            this.state = { entered: false };
          }

          render() {
            if (this.state.entered) {
              window.location.reload(false);
              return save();
            }

            return e(
              'button',
              { onClick: () => this.setState({ entered: true }) },
              'Submit'
            );
          }
        }
           


        const domContainer = document.querySelector('#enter_button_container');
        ReactDOM.render(e(EnterButton), domContainer);

    </script>

        <p id="output"></p>

<script type="text/javascript">

    function clearData() {
        localStorage.clear();
        document.getElementById("input").value.clear();
        document.getElementById("output").innerHTML.clear();
    }

    function save(){
      var storedItem = localStorage.getItem("storedItem");
      var Item = document.getElementById("input").value;
      storedItem = localStorage.setItem("storedItem", Item);
      checkCountry();
    }

     void function checkCountry() {

        var coder = localStorage.getItem("storedItem");


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
    </script>


    

  </body>
</html>
