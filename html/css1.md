##css


##Cascading Properties
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

##Colors

1.background: #800000  /  #ff0;
2.background: rgb(128, 0, 0);
3.background: rgba(128, 0, 0, .25);
4.background: hsl(0, 100%, 25%); 
5.background: hsla(0, 100%, 25%, .25);

![](http://learn.shayhowe.com/assets/images/courses/html-css/getting-to-know-css/hexadecimal-syntax.png)

![](https://raw.githubusercontent.com/HuangFuFw/MarkDownFiles/master/res/color_html.png)

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

##width
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

##Display
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


##Box Model
#####the total width formula:
margin-right + border-right + padding-right + width + padding-left + border-left + margin-left

              
#####the total height formula:
margin-top + border-top + padding-top + height + padding-bottom + border-bottom + margin-bottom
             
![dd](http://learn.shayhowe.com/assets/images/courses/html-css/opening-the-box-model/box-model.png)

## margin:
div {
  margin: 20px; 
}
// all four sides

div {
  margin: 10px 20px;
}
// top and bottom first, then left and right

div {
  margin: 10px 20px 0 15px;
}
//top, right, bottom, and left


div {
  margin-top: 10px;
  padding-left: 6px;
}

##border

div {
  border: 6px solid #949599;
}

![border Type](https://raw.githubusercontent.com/HuangFuFw/MarkDownFiles/master/res/border_type.png)


div {
  border-bottom: 6px solid #949599;
}

div {
  border-bottom-width: 12px;
}


.border-rounded {
  border-radius: 5px;
}

.border-circle {
  border-radius: 50%;
}

.border-football {
  border-radius: 15px 75px;
}
// two values will round the top-left/bottom-right and top-right/bottom-left（对角）
//four values will round the top-left, top-right, bottom-right, and bottom-left corners in that order.(顺时针)


##Box Sizing

div {
  -webkit-box-sizing: content-box;
     -moz-box-sizing: content-box;
          box-sizing: content-box;
}
div {
  box-sizing: border-box;
}

div {
  box-sizing: padding-box;
}


![](http://learn.shayhowe.com/assets/images/courses/html-css/opening-the-box-model/box-sizing.png)

##float

section {
  float: left;
  width: 63%;
}

aside {
  float: right;
  width: 30%;
}

footer {
  clear: both;
  margin-bottom: 0;
}
####Relative Positioning
.offset {
  left: 20px;
  position: relative;
  top: 20px;
}

##font

[Google Fonts](https://fonts.google.com)

body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}

//In this case, Helvetica Neue is the preferred font to display. If this font is unavailable or not installed on a given device, the next font in the list—Helvetica—will be used, and so on.

body {
  font-size: 14px;
}


.special {
  font-style: italic;
}

//four keyword values: normal, italic, oblique, and inherit

.firm {
  font-variant: small-caps;
}

//hree values: normal, small-caps, and inherit

.daring {
  font-weight: bold;
}

//Keyword values include normal, bold, bolder, lighter, and inherit

.daring {
  font-weight: 600;
}

//The numeric values 100, 200, 300, 400, 500, 600, 700, 800, and 900

.btn {
  height: 22px;
  line-height: 22px;
}

html {
  font: italic small-caps bold 14px/22px "Helvetica Neue", Helvetica, Arial, sans-serif;
}


//font-style, font-variant, font-weight, font-size, line-height, and font-family.

p {
  letter-spacing: -.5em;
}

p {
  word-spacing: .25em;
}


a {
    color: #648880;
    text-decoration: none;
}
//字体装饰

a:hover h3 {
  color: #a9b2b9;
}

.btn-alt:hover {
  background: #fff;
  color: #648880;
}
//鼠标在文字上面的颜色设置

.btn{
	cursor: pointer;
}
//鼠标指针的样式

##background

div {
  background-color: #b2b2b2;
  background-color: rgba(0, 0, 0, .3);
}

div {
  background-image: url("alert.png");
  background-repeat: no-repeat;
  background-position: 20px 10px;	
}

![background-position](http://learn.shayhowe.com/assets/images/courses/html-css/setting-backgrounds-and-gradients/background-position.png)

#####Multiple Background Images
div {
  background:  url("foreground.png") 0 0 no-repeat, url("middle-ground.png") 0 0 no-repeat, url("background.png") 0 0 no-repeat;
}


#####eg:
div {
  background: #b2b2b2 url("alert.png") 20px 10px no-repeat;
}

#####Linear Gradient Background
div {
  background: #466368;
  background: -webkit-linear-gradient(#648880, #293f50);
  background:    -moz-linear-gradient(#648880, #293f50);
  background:         linear-gradient(#648880, #293f50);
}

div {
  background: #466368;
  background: linear-gradient(to right bottom, #648880, #293f50);
}


#####Radial Gradient Background
div {
  background: #466368;
  background: radial-gradient(#648880, #293f50);
}
#####Gradient Color Stops 
div {
  background: #648880;
  background: linear-gradient(to right, #f6f1d3, #648880, #293f50);
}

// declared as a length value 

div {
  background: #648880;
  background: linear-gradient(to right, #f6f1d3, #648880 85%, #293f50);
}

##Lists
#####Unordered Lists
<ul>
  <li>Orange</li>
  <li>Green</li>
  <li>Blue</li>
</ul>

#####Ordered Lists
<ol>
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>

<ol start="30">
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>

<ol reversed>
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>

<ol>
  <li>Head north on N Halsted St</li>
  <li value="9">Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>

#####Description Lists
  <dt>study</dt>
  <dd>The devotion of time and attention to acquiring knowledge on an academic subject, especially by means of books</dd>
  <dt>design</dt>
  <dd>A plan or drawing produced to show the look and function or workings of a building, garment, or other object before it is built or made</dd>
  <dd>Purpose, planning, or intention that exists or is thought to exist behind an action, fact, or material object</dd>
  <dt>business</dt>
  <dt>work</dt>
  <dd>A person's regular occupation, profession, or trade</dd>
</dl>


#####Nesting Lists 嵌套list
<ol>
  <li>Walk the dog</li>
  <li>Fold laundry</li>
  <li>
    Go to the grocery and buy:
    <ul>
      <li>Milk</li>
      <li>Bread</li>
      <li>Cheese</li>
    </ul>
  </li>
  <li>Mow the lawn</li>
  <li>Make dinner</li>
</ol>

####List Item Styling
**eg**:
ul {
  list-style-type: square;
  list-style-position: inside;
}

ul {
  list-style: circle inside;
  max-width: 400px;
}
ol {
  list-style: lower-roman;
}


List Style Type Value	Content
none					No list item
disc					A filled circle
circle					A hollow circle
square					A filled square
decimal	                Decimal numbers
decimal-leading-zero  	Decimal numbers padded by initial zeros
lower-roman				Lowercase roman numerals
upper-roman				Uppercase roman numerals
lower-greek				Lowercase classical Greek
lower-alpha / lower-latin	Lowercase ASCII letters
upper-alpha / upper-latin	Uppercase ASCII letters
armenian					Traditional Armenian numbering
georgian					Traditional Georgian numbering

#####Using an Image as a List Item Marker
**html**：
<ul>
  <li>Orange</li>
  <li>Green</li>
  <li>Blue</li>
</ul>

**css**：
li {
  background: url("arrow.png") 0 50% no-repeat;
  list-style-type: none;
  padding-left: 12px;
}

#####Horizontally Displaying List
li {
  display: inline-block;
  margin: 0 10px;
}

#####Floating List
li {
  float: left;
  margin: 0 20px;
}

#####Navigational List Example
**html**：

<nav class="navigation">
  <ul>
    <li><a href="#">Profile</a></li>
	<li><a href="#">Settings</a></li>
	<li><a href="#">Notifications</a></li>
	<li><a href="#">Logout</a></li>
  </ul>
</nav>

**css**：

.navigation ul {
  font: bold 11px "Helvetica Neue", Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  text-transform: uppercase;
}
.navigation li {
  display: inline-block;
}
.navigation a {
  background: #395870;
  background: linear-gradient(#49708f, #293f50);
  border-right: 1px solid rgba(0, 0, 0, .3);
  color: #fff;
  padding: 12px 20px;
  text-decoration: none;
}
.navigation a:hover {
  background: #314b60;
  box-shadow: inset 0 0 10px 1px rgba(0, 0, 0, .3);
}
.navigation li:first-child a {
  border-radius: 4px 0 0 4px;
}
.navigation li:last-child a {
  border-right: 0;
  border-radius: 0 4px 4px 0;
}


##Adding Media

#####Adding Images
<img src="dog.jpg" alt="A black, brown, and white dog wearing a kerchief">

img {
  height: 200px;
  width: 200px;
}

#####Adding audio

<audio src="jazz.ogg" autoplay></audio>

<audio src="jazz.ogg" controls></audio>

<audio controls>
  <source src="jazz.ogg" type="audio/ogg">
  <source src="jazz.mp3" type="audio/mpeg">
  <source src="jazz.wav" type="audio/wav">
  Please <a href="jazz.mp3" download>download</a> the audio file.
</audio>


#####Adding vedio

<video src="earth.ogv" controls></video>

<video src="earth.ogv" controls poster="earth-video-screenshot.jpg"></video>
//带有预览图的video

<video controls>
  <source src="earth.ogv" type="video/ogg">
  <source src="earth.mp4" type="video/mp4">
  Please <a href="earth.mp4" download>download</a> the video.
</video>


#####Adding Inline Frames
<iframe src="https://www.google.com/maps/embed"></iframe>




##未知









                
