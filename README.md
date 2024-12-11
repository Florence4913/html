<!DOCTYPE html>
<html lang="en">
<!--Start of HTML-->
    <head>
        <meta charset="UTF-8">
        <meta name="Florence" content="Hostel">
        <title>Hostel</title>

        <!--Link with external CSS-->
        <link rel="stylesheet" type="text/css" href="style.css">

        <script>        

            function validate(event) {
              event.preventDefault();   //prevents the default form submission when validation fails
              // get the values entered on the HTML form using document.getElementById()
              // write the JS codes to on the values  
                
              var name = document.getElementById("name").value;
              var email = document.getElementById("email").value;
              var enquiry = document.getElementById("enquiry").value;
              var valid1 = valid2 = valid3 = true;
      
              document.getElementById("msg1").innerHTML = "";
              document.getElementById("msg2").innerHTML = "";
              document.getElementById("msg3").innerHTML = "";
      
              var email_filter = /^([a-zA-Z0-9_\.\-])+\@(([a-zA-Z0-9\-])+\.)+([a-zA-Z0-9]{2,4})$/;
              
              if (name == ""){
                document.getElementById("msg1").innerHTML = "Please enter your user name.";
                valid1=false;
              } 
              
              if(email == ""){
                document.getElementById("msg2").innerHTML = "Please enter your email address.";
                valid2=false;
              }
      
              if(enquiry == ""){
                document.getElementById("msg3").innerHTML = "Please enter your enquiry.";
                valid3=false;
              }
              
              if(valid1 && valid2 && valid3){
                alert("Form Submitted");
              }
      
            }
          </script>

    </head>
    <body>
        <nav>
            <ul>
                <li><a href="hostel.html">Hostel</a></li>
                <li><a href="room.html">Room rates</a></li>
                <li><a href="book.html">Book Now</a></li>
            </ul>
        </nav>

        <header>
            <a href="homepage.html" target="_blank"><img src="logo.PNG" alt="logo"></a>
        </header>

        <article>
            <h1>Room Rates</h1>
            <h3>Membership ID: SS111</h3>

            <table>
                <caption><strong>Refer to the table below for our room rates</strong></caption>
                <tr>
                    <th rowspan="2" class="member">Room Type</th>
                    <th rowspan="2" class="member">Breakfast</th>
                    <th colspan="2" class="member">Rate per person($)</th>
                </tr>

                <tr>
                    <th colspan="1" class="member">Without membership</th>
                    <th colspan="1" class="member">With membership</th>
                </tr>

                <tr>
                    <td>Single private</td>
                    <td rowspan="2">Yes</td>
                    <td rowspan="1">100</td>
                    <td rowspan="4">10% discount</td>
                </tr>
                <tr>
                    <td>Twin private</td>
                    <td rowspan="1">90</td>
                </tr>
                <tr>
                    <td>Shared female</td>
                    <td rowspan="2">No</td>
                    <td rowspan="2">50</td>
                </tr>
                <tr>
                    <td>Shared male</td>
                </tr>
            </table>
        </article>
        
        <section>
            <form name="order" action="mailto:florencefswr@gmail.com" enctype="text/plain" method="post">
                <fieldset>
                    <legend><strong>Submit your enquiry here</strong></legend>
                    <p><label for="name">Full Name:</label>
                    <input type="text" id="name" name="name" placeholder="Include your first and last name" size="40" required></p>
                    <p class="error" id="msg1"></p>
                    
                    <p><label for="email">Email address:</label>
                    <input type="email" id="email" name="email" size="40"></p>
                    <p class="error" id="msg2"></p>

                    <p><label for="enquiry">Enquiry:</label></p>
                    <textarea id="enquiry" name="enquiry" rows="4" cols="40"></textarea>
                    <p class="error" id="msg3"></p>
                
                    <button type="submit" id="submit" onclick="validate(event)">Submit</button>
                </fieldset>
            </form>
        </section>
    </body>
</html>
