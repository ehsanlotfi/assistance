# wp-nav-walker-simple
```
wp_nav_menu( array(
'theme_location' => 'footernav',
'container' => '',
'items_wrap' => '%3$s',
'walker' => new  Div_Nav_Walker()
) );
```
```
class  Div_Nav_Walker  extends  Walker_Nav_Menu {
	public  function  start_lvl( &$output, $depth = 0, $args = array() ) {
		$output  .=  "";
	}

	function  end_lvl( &$output, $depth = 0, $args = array() ) {
		$output  .=  "";
	}

	function  start_el(&$output, $item, $depth=0, $args=array(), $id = 0) {
		// active menu
		$classes = "";
		if(array_search('current-menu-item', $item->classes) != 0){
		   $classes .= " active";
		}
		$output  .=  '<a class="'.$classes.'" href="'.$item->url.'">'.$item->title;
	}
	
	function  end_el(&$output, $item, $depth=0, $args=array()) {
	   $output  .=  "</a>\n";
	}
}
```

