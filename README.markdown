# CakePHP LESS CSS Plugin
* Author: Ben Auld (http://www.benauld.com)

The purpose of the CakePHP Less plugin is to easily use LESS CSS within your
CakePHP 2.0.x apps. This plugin can not only compile LESS files, but also
minify and combine if enabled.

# Installation
First clone plugin into app/Plugin/Less

	git clone git://github.com/benauld345/CakePHP-LESS-CSS-Plugin.git app/Plugin/Less
	
Then you will need to enable the plugin from within your app boostrap file (app/Config/bootstrap.php):

	CakePlugin::load('Less');
	
Then in your AppController or your Controller add the helper to your helpers array like so:

	public $helpers = array('Less.Less');
	
Then in your layout, add the following line:

	<?php echo $this->Less->link(array('global.less', 'styles.less')); ?>
	
And that's it! By default the Less Helper will minify and combine your files. You can switch these off, see options below.

# Options

	<?php
	echo $this->Less->link('file.less', array(
		'minify' => true // Set to true to minify CSS output
		'combine' => true // Set to true to combine all files into one
		'output_directory' => 'ccss/' // Output directory in your webroot
	));
	?>
