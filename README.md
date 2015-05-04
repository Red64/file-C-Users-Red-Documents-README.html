<!doctype html>
<html lang="fr">
<head>
	<meta charset="utf-8" />
	<title>README</title>
	<!-- HTML5 Shim -->
	<!--[if lt IE 9]><script src="http://html5shim.googlecode.com/svn/trunk/html5.js"></script><![endif]-->
	<!-- Modernizr -->
	<script src="modernizr.js"></script>
	<!-- Webforms2 -->
	<script src="webforms2/webforms2-p.js"></script>
	<!-- jQuery  -->
	<script src="js/jquery-1.4.3.min.js"></script>
	<script src="js/jquery-ui-1.8.5.min.js"></script>
	<!-- Feuille de style -->
	<link rel="stylesheet" href="styleFormulaire.css">
	<!-- jQuery Color Picker -->
	<link rel="stylesheet" href="colorpicker.css">
	<script src="colorpicker.js"></script>
	<!-- jQuery Numeric Spinner -->
	<script src="spinner.js"></script>
 
	<!-- jQuery Placehol -->
	<script src="jquery.placehold-0.2.min.js"></script>
 
	<!-- Demo page layout  -->
	<link rel="stylesheet" href="html5forms.layout.css">
	<script src="html5forms.js"></script>
	<script src="html5forms.fallback.js"></script>
 
 
</head>
<body>
    <!-- Script DATE  -->
	<script>
	var initDatepicker = function() {
    $('input[type=date]').each(function() {
        var $input = $(this);
        $input.datepicker({
            minDate: $input.attr('min'),
            maxDate: $input.attr('max'),
            dateFormat: 'yy-mm-dd'
        });
    });
};
 
if(!Modernizr.inputtypes.date){
    $(document).ready(initDatepicker);
};
  </script>
 
  <!-- Script COLOR  -->
  <script>
  var initColorpicker = function() {
    $('input[type=color]').each(function() {
        var $input = $(this);
        $input.ColorPicker({
            onSubmit: function(hsb, hex, rgb, el) {
                $(el).val(hex);
                $(el).ColorPickerHide();
            }
        });
    });
};
 
if(!Modernizr.inputtypes.color){
    $(document).ready(initColorpicker);
};
  </script>
 
 
 
 
 
	<h1>
     	README
	</h1>
 
 
	<form>
	<fieldset>
 
 
 
		<p><label for="range">Slider</label>
		<input type="range" name="range" id="slider" class="slider" min="0" max="5" step="1" value="0" style="width:220px;" onchange="showValue(this.value)" />
<span id="range">0</span>
<script type="text/javascript">
function showValue(newValue)
{
	document.getElementById("range").innerHTML=newValue;
}
</script>
 
		<p><label for="text">Champ de texte avec placeholder</label>
		<input type="text" name="text" id="text" placeholder="Inserer votre texte ici"></p>
 
		<p><label for="url">Champ d'Url</label>
		<input type="url" id="url" name="url" placeholder="http://www.41mag.fr" required></p>
 
		<p><label for="email">Champ Email</label>
		<input type="email" id="email" name="email" placeholder="votre@dresse.fr" required></p>
 
		<p><label for="numeric">Format numerique</label>
		<input type="number" name="numeric" id="numeric" value="2"></p>
 
		<p><label for="date">Format date</label>
		<input type="date" name="date" id="date" value="2012-03-01"></p>
 
		<p><label for="color-picker">Choix de la couleur</label>
		<input type="color" name="color-picker" id="color-picker" value="ff0000"></p>
 
		<p class="centerAlign"><button type="submit" class="boutonSubmit" role="button" aria-disabled="false">
			Soumettre le formulaire
		</button></p>
		<div class="clear"></div>
	</fieldset>
	</form>
 
	<footer>
		<p>
      		Copyright - <a href="http://www.41mag.fr">41Mag</a>
		</p>
	</footer>
<h2>#!/bin/sh</h2>
 
REPOS="$1"
REV="$2"
 
SUBJECT=`\
  echo -n "[SVN commit] R-$REV Log:";\
  svnlook log --revision \
        $REV /home/README/htdocs/repository | head -n1`
<h3>MESSAGE=`\</h4>
  echo -n "REPOS:$REPOS ; REV:$REV ; AUTHOR:";\
  svnlook author --revision $REV /home/README/htdocs/repository; \
  echo ; echo "LOG:";\
  svnlook log --revision $REV /home/README/htdocs/repository;\
  echo;echo "LISTE DES FICHIERS:";echo "-------------";\
  svnlook changed --revision $REV /home/README/htdocs/repository`
 
/usr/local/bin/sendEmail.pl -f subversion@kitpages.com \
  -t webmaster@kitpages.com \
  -u "$SUBJECT" -m "$MESSAGE" >> /dev/null 
 </body>
</html>
