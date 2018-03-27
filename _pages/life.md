---
layout: archive
title: "Haha"
permalink: /life/
author_profile: true
redirect_from:
  - /haha
---

<div id="loginbox" class="lightbox" >
<div class="horizontal">
<div class="vertical">
<div class="box">				
	<input style="margin: 16px; text-align: center;" id="password" type="password" placeholder="password" /> <br />
	<button id="loginbutton" type="button">Enter</button>
		<p id="wrongPassword" style="display: none">wrong password</p>
</div>
</div>
</div>
</div>



<script type="text/javascript" src="https://code.jquery.com/jquery-1.12.0.min.js">
</script>
	 

<script type="text/javascript" src="https://cdn.rawgit.com/chrisveness/crypto/master/sha1.js"></script>

<script type="text/javascript">
	"use strict";
	function loadPage(pwd) {
		
		var hash= pwd;
		hash= Sha1.hash(pwd);
		var url= hash + "/index.html";
			
		$.ajax({
			url : url,
			dataType : "html",
			success : function(data) {
				window.location= url;
			},
			error : function(xhr, ajaxOptions, thrownError) {
			
				parent.location.hash= hash;
				//$("#wrongPassword").show();
				$("#password").attr("placeholder","wrong password");
				$("#password").val("");
			}
		});
	}
	 
	$("#loginbutton").on("click", function() {
		loadPage($("#password").val());
	});
	$("#password").keypress(function(e) {
		if (e.which == 13) {
			
			loadPage($("#password").val());
		}
	});
	$("#password").focus();
		
</script>