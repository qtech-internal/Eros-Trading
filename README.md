Documentation by “Ansonika” v2.1
“REMOVALS - HTML Site template”
Created: 23 April 2015
Last update: 10 Janaury 2024
By: Ansonika

Thank you for purchasing my theme. If you are happy with the theme, please TAKE A MOMENT TO RATE IT from your DOWNLOADS PAGE. Thanks so much!

Table of Contents
HTML Structure
CSS Files, Structure and basic modifications
PHP contact form, quotation and quotation wizard
JavaScript
Sources and Credit
Updates
A) HTML Structure - top
This theme has a fixed centered layout 1170px. It's based on Boostrap framework grid. It's ULTRA RESPONSIVE!!.

B) CSS Files Structure and basic modfication - top
The css files are inside the css folder (minified versions included) .To modify colors, typografy, button style ecc....find the realtive comment line in style.css. Below how the file is organized:

1. SITE STRUCTURE and TYPOGRAPHY
- 1.1 Typography
- 1.2 Buttons
- 1.3 Structure

2. CONTENT
- 2.1 Home
- 2.2 About
- 2.3 Removals
- 2.4 Quotation
- 2.5 Quotation wizard
- 2.6 Tips / faq
- 2.7 Contact us

3. COMMON
- Tooltips
- Containers styles
- Form styles
- Tabs, collapse
- etc

LAYERSLIDER
Please refer this DOCUMENTATION

Change the address of Google map in contact page: open mapmarker_func.js and change with your latitude and longitude + your full address. You can change also your map marker (that has to be png24); you can use also the psd provided in the psd folder.

//set up markers 
		var myMarkers = {"markers": [
				{"latitude": "51.511732", "longitude":"-0.123270", "icon": "img/map-marker2.png"}
			]
		};
		
		//set up map options
		$("#map").mapmarker({
			zoom	: 14,
			center	: 'Covent Garden London', //YOUR FULL ADDRESS 
			markers	: myMarkers
		});
COMMON ISSUE ON GOOGLE MAP (if the Google map works locally but does not works once the site will be online)
In some cases Google requires an api key for the Google map.

You can create your own "Standard api key" here 
by clicking on "GET KEY" BUTTON (on Authentication for the standard API—API keys section), 
and follow the steps.
https://developers.google.com/maps/documentation/javascript/get-api-key#key

Here some additionale info on how to create an API KEY http://thegrue.org/google-map-javascript-api-key/

Then replace at the bottom of every page that use Google map, this line

<script src="http://maps.googleapis.com/maps/api/js"></script> OR 
<script type="text/javascript" src="http://maps.googleapis.com/maps/api/js?sensor=false"></script>

with your api key included, like the example below
<script src="http://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY"></script>
  
THE GRID
Please refer to this documentation Boostrap

ON SCROLL ANIMATIONS
Please refer to this documentation

C) PHP files: Contact form, quotation and quotation wizard - top
The templates use two different types of php scriptst: one for the contact form (all the files are located in the assets folder), second for the quotation and quotation wizard page.

Below the script for the contact form, you can set the error messages in the validate.js.


If you doesn't recieve the email please first check:
1) Your spam folder
2) If you hosting requires special settings
3) If your email has to be managed from the same hosting provider
4) Set the permission of the asset folder on your host to 755 your FTP client 5) This script does not support SMTP authentication

Quotation wizard
Add an input field into form first step

1) Apply the proper name to the input (<input type="text" name="new_field" />)
2) Call validation/error messages for the new field: open js/quotation-validate.js and look the example below in bold:

$('#custom').validate({
errorPlacement: function(error, element) {
$('#custom .stepy-error').append(error);
}, rules: {
'name':		'required',
'last_name':		'required',
'email':		'required',
'newsletter':	'required',
'new field':	'required',
'address':		'required',
'zip_code':			'required',
'country':			'required',
'terms':		'required' 	// BE CAREFUL: last has no comma
}, messages: {
'name':		{ required: 	 'Name required' },
'last_name':		{ required: 	 'Last name required' },
'email':		{ required: 	 'Invalid e-mail!' },					
'newsletter':	{ required:  'Newsletter required!' },
'new_field':	{ required:  'New field required!' },
'address':		{ required:  'Address required!' },
'zip_code':			{ required:  'Zip code required' },
'country':			{ required:  'Country required' },
'terms':		{ required:  'Please accept terms!' }
}
});
3) Then open quotation_wizard.php and follow the instructions/example below:
$mail = $_POST['email'];

/*$subject = "".$_POST['subject'];*/
$to = "test@ansonika.com"; <<< write your email here >>>
$subject = "Sign up from REMOVALS"; <<< write your subject >>>
$headers = "From: REMOVALS web site ";
$message = "Message\n";
$message .= "\nName: " . $_POST['name'];
$message .= "\nLast Name: " . $_POST['last_name'];
$message .= "\nEmail: " . $_POST['email'];
$message .= "\nPhone number: " . $_POST['phone_number'];
$message .= "\nSubscribe to newsletter: " . $_POST['newsletter'];
$message .= "\nNew field title: " . $_POST['new_field'];
$message .= "\nAddress: " . $_POST['address'];
$message .= "\nZip code: " . $_POST['zip_code'];
$message .= "\nCountry: " . $_POST['country'];
$message .= "\nMessage: " . $_POST['message'];
$message .= "\nTerms and conditions accepted: " . $_POST['terms'];
						
//Receive Variable
$sentOk = mail($to,$subject,$message,$headers);
	
Add one more step
Each step is determined by the fieldset tag...so simply add a fieldset. Use the tag legend to describe your step/tab (Ex. <legend>Personal info</legend>)

 <fieldset title="Step 1">
  ......       
 </fieldset><!-- End Step one -->
        
 <fieldset title="Step 2" >
  ......
 </fieldset><!-- End Step two -->

 etc....
      
Quotation normal
It use a similar PHP script of the wizard, except for the validation that is simplified. I you need to validate/makes required a field...simply add the class "required" to the input.
D) JavaScript - top
This theme use These Javascript (minified versions included). i've included the common theme scripts in a single file for a fast edit and load.

common_scripts.js content:

Boostrap.js
Magnifc-popup.js
jQuery Migrate
Scroll Cue Animations
Retina-replace.js
Below a full list of js used.



E) Sources and Credits - top
I've used the following images, icons or other files as listed.

Bootstrap
Fontello
Elegant Icon font
Magnific popup
Retina replace
Jquery validate
Jquery
Jquery Stepy wizard
Scroll Cue Animations
Elegant Icon Font
Images and Videos are not included. Envato for copyright rules, does not permit to include those assets in the downloadable file. They are only for demo purpose. Below the sources sites:

Pixabay
Unsplash
Vectorstock
F) Updates - top
V.2.1 (10 January 2024)
- Updated Documentation

V.2.0 (4 October 2023)
- Updated Jquery Library
How to update:

Updated Jquery Library        
Update on footer pages this line <script src="js/jquery-3.7.1.min.js"></script> (of course copy the new file in the js folder).
V.1.9 (21 June 2023)
- Updated Jquery Library
How to update:

Updated Jquery Library        
Update on footer pages this line <script src="js/jquery-3.7.0.min.js"></script> (of course copy the new file in the js folder).
V.1.8 (17 January 2023)
- Updated Jquery Library
- Increased the font size and minor css improvements
- Added animations on scroll
- Added Home Slider/carousel

How to update:

- Updated Jquery Library        
1) Update on footer pages this line <script src="js/jquery-3.6.3.min.js"></script> (of course copy the new file in the js folder).
2) Update js/common_scripts_min.js
3) Update js/functions.js

- Increased the font size
1) Update css/style.css (or the selector/classes body, #top_line, .btn_1, .form-control, .box_style_2 h5, footer h3, #address_footer:before, #phone_footer:before, #email_footer:before,  #email_footer:before)
2) Update css/menu.css (or the selector/classes .main-menu ul ul li a, .main-menu ul li.submenu ul, .main-menu ul li.submenu ul li)

- Added animations Scroll (takes as reference index.html, index_2.html, about.html)
1) Update css/style.css or Scroll cue animations section at the bottom
2) Update js/common_scripts_min.js
3) Update js/functions.js

- Added Home Slider/carousel (takes as reference index.html)
1) Copy and paste css/carousel_home.css
2) Copy and paste js/slider.js
3) Copy and paste img/slider_2/ folder
4) Copy and paste img/drag_icon.svg
V.1.7 (8 August 2022)
- Removed "get_magic_quotes_gpc" php function deprecated for latest PHP versions

How to update:
        
Update the following files: assets/contact.php or delete the following lines of code 

if(get_magic_quotes_gpc()) {
	$message_contact = stripslashes($message_contact);
}     
V.1.6 (14 January 2022)
- Updated documentation.

V.1.5 (18 February 2021)
- Updated documentation.

V.1.4 (15 December 2018)

Removed @import
Removed conditional css comments for IE 8/9 in the html pages
How to update from previous version:

in the head of every page please replace this line:

<!-- BASE CSS -->
<link href="css/base.css" rel="stylesheet">

with
<!-- BASE CSS -->
    <link href="css/bootstrap.min.css" rel="stylesheet">
    <link href="css/style.css" rel="stylesheet">
    <link href="css/menu.css" rel="stylesheet">
    <link href="css/responsive.css" rel="stylesheet">
    <link href="css/elegant_font/elegant_font.css" rel="stylesheet">
    <link href="css/fontello/css/fontello.css" rel="stylesheet">
    <link href="css/magnific-popup.css" rel="stylesheet">
V.1.3 (26 July 2016)
- Updated documentation on how to fix for possible coming issue related on Google map.

V1.2 23 June 2016
- Added Datepciker

V1.1 7 May 2015
- Added Blog section












Once again, thank you so much for purchasing this theme. Please take a moment to rate it from your Downloads page.
Need support?
For support contact me using the form on my profile page with subject [ThemeForest Support] Template name, or use the Support Tab on Envato item page. You will receive an answer within 24-48 hours (working days) GMT +1.
I only provide support for fixing bugs or small issues on my items.
I don't provide free support for additional custom modifications to the items.
Please provide your site link, screenshots and other information about your issue.
Read also here
Need customization or availability for freelance projects?
Just send an email via profile page form; please don't forget to specify:
if you are a company, agency or private user
all the information about your projects, needs, site urls, project sheet, etc..
from which country you are
if you have a deadline
if you have basic knowledge of HTML , CSS, JS, PHP
Ansonika

Go To Table of Contents

