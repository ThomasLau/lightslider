this prj forked from sachinchoolur's lightslider. i used it to meet some requirements in my recent project.
some bug-fix or adustments will be added later

1, the gallery's navigater will be invisible if the hight of a photo over-flowes. here is a way to fix: 
```css
/** FF和Chrome下支持max-width和max-height样式 */
.myimg{ max-width:120px; max-height:120px; }
/** IE下通过expression设置样式 **/
#imgdiv img { 
	width:expression(this.width>120&&this.width>this.height?120:auto);
	height:expression(this.height>120?120:auto);
}
```

2, how to add some more phto intros tothe gallery:
```html
<div class="big_picture">
	<div class="introduction" style="position:absolute;z-index:9999;"></div>
	<div class="place_name" style="position:absolute;z-index:9999;">
		<h2><?php echo $imgtitle?></h2>
		<p><?php echo $imgintro?></p>
	</div>
	<ul id="lightSlider" class="gallery list-unstyled cS-hidden">
	<?php 
	foreach ($imgArr as $pic){
		echo '<li data-thumb="'.$ROOT.$pic["S"].'">
		<a href="#"><img src="'.$ROOT.$pic["L"].'"/></a> </li>';
	}
	?>
	</ul>
</div>
```
