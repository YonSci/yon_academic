---
layout: archive
title: "Project & Research"
permalink: /Projects-Research/
author_profile: true
---

<img src="https://github.com/YonSci/yon_academic/blob/78b86dd6c2f4b519ec98eb380e339e252e5ea92b/images/b1.png?raw=true" width="300" height="300" />

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
<li class="mymultiplediv" id="one">Date: 18-01-2022</li>
<li class="mymultiplediv" id="two">Date: 19-01-2022</li>
<li class="mymultiplediv" id="three">Date: 20-01-2022</li>
<li class="mymultiplediv" id="fore">Date: 21-01-2022</li>
</ul>
</div>
<div class="mydiv" id="divone"><img src="https://github.com/YonSci/yon_academic/blob/master/images/day19.png?raw=true" width="300" height="300" alt="Date: 18-01-2022" class="img-responsive img-thumbnail"/><span>Manager</span></div>
<div class="mydiv" id="divtwo"><img src="https://github.com/YonSci/yon_academic/blob/22312f43733f3b9e910941e2cbb1b2a984e4958a/images/day19.png?raw=true" width="300" height="300" alt="Date: 19-01-2022" class="img-responsive img-thumbnail"/><span>HR</span></div>
<div class="mydiv" id="divthree"><img src="https://github.com/YonSci/yon_academic/blob/22312f43733f3b9e910941e2cbb1b2a984e4958a/images/day20.png width="300" height="300" " alt="Date: 20-01-2022" class="img-responsive img-thumbnail"/><span>Developer</span></div>
<div class="mydiv" id="divfore"><img src="https://github.com/YonSci/yon_academic/blob/22312f43733f3b9e910941e2cbb1b2a984e4958a/images/day21.png width="300" height="300" " alt="Date: 21-01-2022" class="img-responsive img-thumbnail"/><span>Designer</span></div>


{% include social-share.html %}
{% include comments.html %}
