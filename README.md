# Install & Setup [WordPress](http://wordpress.org) 

Author: [Anas Labzar](https://github.com/AnasLabzar)

##  How To Install WordPress 

## Synopsis

I was looking around for a useful script to speed up the setting-up process for a WordPress site.

After looking around, I found a couple of great scripts by [@snaptortoise](https://github.com/snaptortoise) and [@darlanrod](https://github.com/darlanrod). However I needed more features to speed up my day-to-day WordPress work, so I built on top of the fantastic work these guys did to get it to where I needed it to be.


# Installation

- First step : go to [Bitnami WordPress](https://bitnami.com/stack/wordpress) After entering the site, download wordpress.
- Second step : Install Bitnami Software

Plugin List
-----------
- All-in-One-SEO-Pack
- Sitemap Generator
- Secure WordPress
- Hierarchy Plugin
- Image Widgets (Why isn't this standard?)
- Super-cache
- W3 Total Cache (A little redundant with above, but hey, I like options.)
- Register Plus Redux (Good for membership-style sites)
- Regenerate Thumbnails (good for when you need to change custom thumb sizes late in a project)
- Taxonomy Taxi
- Custom Post Type UI 
- WordPress Importer
- Password Protect WordPress
- WP-Quick-Pages
- FeedWordPress
- BackWPup
- [Meta Box](http://wordpress.org/plugins/meta-box/)
- [Options Framework](http://wordpress.org/plugins/options-framework/)



## Plugins
The script installs the following WordPress plugins:

Advanced Custom Fields 
† ACF Content Analysis for Yoast SEO
Contact Form 7
Flamingo
W3 Total Cache
Wordfence Security
Yoast SEO
† I highly recommend purchasing the Pro version!

 # Create Plugin Copyright
 
 ## PHP / HTML / CSS
 1. create plugin et afficher
 
 ```php
<?php
/*
Plugin Name: Copyright editing
Description: "Copyright editing" une extension de wordpress Simple avec 2 sous menus : un pour les informations générale du plugin et un pour les settings.
Version: 1.0
Author: Anas labzar
License: GPLv2 or later
Text Domain: AL Copyright 
*/
```

 2. Exit if accessed directly
 
 ```php
if ( ! defined( 'ABSPATH' ) ) {
	exit; // Exit if accessed directly.
}
 ```
 
 3. Add management page & parameters details
 
  ```php
  
add_action('admin_menu', 'my_admin_menu');

function my_admin_menu () {
    
	 //parameters details
	 //add_management_page($page_title, $menu_title, $capability,$menu_slug, $function);
    
	 //add a new setting page udner setting menu
     //add_management_page('Description', 'Description', 'manage_options',__FILE__,'Description_admin_page');
     //add new menu and its sub menu 
    add_menu_page('Description title', 'AL Copyright ', 'manage_options','Description_page', 'Description_admin_page','dashicons-admin-home');
    add_submenu_page( 'Description_page', 'Page title', 'Settings','manage_options', 'Settings', 'mt_settings_page');
}
 ```
 
 4. Create Description page
 
  ```php
  
function Description_admin_page () {
    
  echo '<div class="wrap">
  <h1>Hello!</h1>
  <p>it is a plugin with two submenus. A page for the general description of my plugin.Configuration page an input text field, textarea for the description,
     an option list and a save button
  </p>
</div>';
}
 ```
 
 5. Displays the page content for the Test Settings submenu
 
  ```php
 // mt_settings_page()
function mt_settings_page() {
    echo "<h2>" . __( 'Settings Configurations', 'menu-test' ) . "</h2>";
	include_once('setting_page.php');
}
 ```
 
 6. Settings plugin (private)

## Thank you
 
