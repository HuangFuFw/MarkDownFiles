##css


####Cascading Properties
1.
p {
  background: orange;
}

2.
<div class="hotdog">
  <p>...</p>
  <p>...</p>
  <p class="mustard">...</p>
</div>

.hotdog p {
  background: brown;
}

组合属性： 只有用hotdog父属性下的<p>的mustard属性背景是黄色
.hotdog p.mustard {
  background: yellow;
}

3.
<p id="food">...</p>           
 #food {
  background: green;
}

4.
Multiple Clesses:

<a class="btn btn-danger">...</a>
`

####Colors

1.background: #800000  /  #ff0;
2.background: rgb(128, 0, 0);
3.background: rgba(128, 0, 0, .25);
4.background: hsl(0, 100%, 25%); 
5.background: hsla(0, 100%, 25%, .25);

![](http://learn.shayhowe.com/assets/images/courses/html-css/getting-to-know-css/hexadecimal-syntax.png)

Color	Name	Hex Values	RGB Values	HSL Values
black	#000000	rgb(0, 0, 0)	    hsl(0, 0%, 0%)
silver	#c0c0c0	rgb(192, 192, 192)	hsl(0, 0%, 75%)
gray	#808080	rgb(128, 128, 128)	hsl(0, 0%, 50%)
white	#ffffff	rgb(255, 255, 255)	hsl(0, 100%, 100%)
maroon	#800000	rgb(128, 0, 0)	    hsl(0, 100%, 25%)
red	    #ff0000	rgb(255, 0, 0)		hsl(0, 100%, 50%)
purple	#800080	rgb(128, 0, 128)	hsl(300, 100%, 25%)
fuchsia	#ff00ff	rgb(255, 0, 255)	hsl(300, 100%, 50%)
green	#008000	rgb(0, 128, 0)		hsl(120, 100%, 25%)
olive	#808000	rgb(0, 255, 0)		hsl(120, 100%, 50%)
lime	#00ff00	rgb(128, 128, 0)	hsl(60, 100%, 25%)
yellow	#ffff00	rgb(255, 255, 0)	hsl(60, 100%, 50%)
navy	#000080	rgb(0, 0, 128)		hsl(240, 100%, 25%)
blue	#0000ff	rgb(0, 0, 255)		hsl(240, 100%, 50%)
teal	#008080	rgb(0, 128, 128)	hsl(180, 100%, 25%)
aqua	#00ffff	rgb(0, 255, 255)	hsl(180, 100%, 50%)

[Adobe Kuler](https://color.adobe.com/)

####width
1.
.col {
  width: 50%;  //50% of the parent element’s width.
}

2.
.banner {
  font-size: 14px;
  width: 5em;//
}
注释：
The em unit is represented by the em unit notation, and its length is calculated based on an element’s font size the width would equal 70 pixels (14 pixels multiplied by 5).

####Display
p {
  display: block;
}

p {
  display: inline;
}

p {
  display: inline-block;
}

div {
  display: none;
}


####Box Model
#####the total width formula:
margin-right + border-right + padding-right + width + padding-left + border-left + margin-left

              
#####the total height formula:
margin-top + border-top + padding-top + height + padding-bottom + border-bottom + margin-bottom
             
![dd](http://learn.shayhowe.com/assets/images/courses/html-css/opening-the-box-model/box-model.png)


div {
  margin: 20px;
}

div {
  margin: 10px 20px;
}

div {
  margin: 10px 20px 0 15px;
}
