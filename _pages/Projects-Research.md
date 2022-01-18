---
layout: archive
title: "Project & Research"
permalink: /Projects-Research/
author_profile: true
---
Low cloud 6-hour (7:40am-1:40pm) animation from the EUMETSAT product over Ethiopia on  Wednesday, September 29th
<div><video src="https://i.windy.com/a/1v0pl/5efs1k.mp4" controls autoplay loop muted></video><div></div></div>

<style>
.mymultiplediv{
cursor:pointer;
}
.mymultiplediv{
width: 150px;
border: 1px solid #ccc;
margin: 10px;
padding: 10px;
color: #fff;
border-radius: 5px;
border: 1px solid #000;
background: #7d7474;
text-align: center;
}
.mydiv{
display:none;
padding:10px;
text-align:center;
}
.mydiv img{
margin: 0 auto;
}
.mydiv span{
text-align: center;
background: #ffdede;
padding: 6px 10px;
display: block;
width: 100px;
border: 1px solid #d47c7c;
margin: 8px auto;
}
</style>
<script>
$(document).ready(function(){
$('.mymultiplediv').mouseover(function() {
myvar = this.id;
$("div.mydiv").hide();
$('#div'+myvar).show();
});
});
</script>
<h2 class="text-center heading">Hover Below list Buttons to display div</h2>
<div class="text-center">
<ul class="list-inline">
<li class="mymultiplediv" id="one">Show Manager</li>
<li class="mymultiplediv" id="two">Show HR</li>
<li class="mymultiplediv" id="three">Show Developer</li>
<li class="mymultiplediv" id="fore">Show Designer</li>
</ul>
</div>
<div class="mydiv" id="divone"><img src="/images/user1.jpg" alt="Manager" class="img-responsive img-thumbnail"/><span>Manager</span></div>
<div class="mydiv" id="divtwo"><img src="/images/user2.jpg" alt="HR" class="img-responsive img-thumbnail"/><span>HR</span></div>
<div class="mydiv" id="divthree"><img src="/images/user3.jpg" alt="Developer" class="img-responsive img-thumbnail"/><span>Developer</span></div>
<div class="mydiv" id="divfore"><img src="/images/user4.jpg" alt="Designer" class="img-responsive img-thumbnail"/><span>Designer</span></div>


{% include social-share.html %}
{% include comments.html %}
