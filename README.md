# LMAndroid-search

##### Introduction
LMAndroid-search is a little library which allows you to create a material design search top bar.<br />
I've got Hamburguer icon from <a hregf="http://callmenick.com/post/animating-css-only-hamburger-menu-icons" target="_blank">this web</a>; and search icon from <a href="https://material.io/icons/" target="_blank">google's icon database</a>.

##### Installation
<b>This library needs <a href="https://jquery.com/" target="_blank">Jquery</a> to use it.</b> Don't be a fool and go to jquery site and download the latest version<br />
```javascript
    <script src="https://code.jquery.com/jquery-2.2.3.min.js" integrity="sha256-a23g1Nt4dtEYOj7bR+vTu7+T8VP13humZFBJNIYoEJo=" crossorigin="anonymous"></script>
```

Next Javascript lines are the controller for hamburguer icon and the click in search icon (you should implement the functionality by yourself =D).
```javascript
$(document).ready(function() {
  $('.c-hamburger').click(function() {
    if($("#top-bar").hasClass('searched')) {
      $(this).toggleClass('is-active');
      $('#top-bar').removeClass('searched');
      $('.search').show();
      $('.search-input').hide(100).val('');
    }
  });

  $('.search').click(function() {
    $('#top-bar').addClass('searched');
    $(this).hide(100);
    $('.c-hamburger').toggleClass('is-active');
    setTimeout(function() {$('.search-input').css('display', 'inline-block').focus();}, 125);
  });
});
```

And the last step is copy next html into your body: (HTML included has all this lines)
```html
<div id="top-bar">
	<button class="c-hamburger c-hamburger--htla">
	    <span>toggle menu</span>
	</button>

	<input type="text" class="search-input" placeholder="Search...">

	<div class="search">
	</div>
</div>
```

That's all. You are free to clone the repository and fork it in order to improve :D. (The html file)
