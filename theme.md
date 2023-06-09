# Features
- The theme primarily includes a simple Header and a Footer.
- The Header consists of the Baizonn Learning Centre Logo and a navigation bar.
- The navigation bar includes links to five different pages:

  - [Home](https://cp3402-team-a.com/) 
  - [About Us](https://cp3402-team-a.com/about-us-2/)  
  - [Registration](https://cp3402-team-a.com/registration/)
  - [Schedule](https://cp3402-team-a.com/schedule/)
  - [Contact Us](https://cp3402-team-a.com/contact-us/)

- The Website Logo includes a link to the home page.
- The Footer includes the contact information for General Enquires.

# Files

## Relevant Files
- header.php: This file contains the code for creating the header of the theme. The following snippet of code is used to 
```php
<nav id="site-navigation" class="main-navigation">
			<button class="menu-toggle" aria-controls="primary-menu" aria-expanded="false"><?php esc_html_e( 'Primary Menu', 'baizonn' ); ?></button>
			<?php
			wp_nav_menu(
				array(
					'theme_location' => 'menu-1',
					'menu_id'        => 'primary-menu',
				)
			);
			?>
		</nav><!-- #site-navigation -->
```
- footer.php - This page contains the content for the footer. This following snippet of code is used to create the footer.
```php
footer id="colophon" class="site-footer">
		<div class="site-info">
			<a href="<?php echo esc_url( __( 'https://wordpress.org/', 'baizonn' ) ); ?>">
				<?php
				/* translators: %s: CMS name, i.e. WordPress. */
				printf( esc_html__( 'Proudly powered by %s', 'baizonn' ), 'WordPress' );
				?>
			</a>
			<span class="sep"> | </span>
				<?php
				/* translators: 1: Theme name, 2: Theme author. */
				printf( esc_html__( 'Theme: %1$s by %2$s.', 'baizonn' ), 'baizonn', '<a href="http://underscores.me/">Underscores.me</a>' );
				?>
		</div><!-- .site-info -->
	</footer><!-- #colophon -->
```
- functions.php - This page contains the code for all neccessary functions related to the theme. The following snippet of code is used to add theme support.
```php
add_theme_support( 'automatic-feed-links' );

	/*
		* Let WordPress manage the document title.
		* By adding theme support, we declare that this theme does not use a
		* hard-coded <title> tag in the document head, and expect WordPress to
		* provide it for us.
		*/
	add_theme_support( 'title-tag' );

	/*
		* Enable support for Post Thumbnails on posts and pages.
		*
		* @link https://developer.wordpress.org/themes/functionality/featured-images-post-thumbnails/
		*/
	add_theme_support( 'post-thumbnails' );
```
- page.php: This file contains the code for displaying all the pages by default. The following snippet of code is used to display the pages.
```php
<main id="primary" class="site-main">

		<?php
		while ( have_posts() ) :
			the_post();

			get_template_part( 'template-parts/content', 'page' );

			// If comments are open or we have at least one comment, load up the comment template.
			if ( comments_open() || get_comments_number() ) :
				comments_template();
			endif;

		endwhile; // End of the loop.
		?>

	</main><!-- #main -->
```
- style.css: This file contains the style templates. The following snippet of code is used for adding the correct text decoration in Chrome, Edge, IE, Opera, and Safari.
```css
abbr[title] {
	border-bottom: none;
	text-decoration: underline;
	text-decoration: underline dotted;
}
```
## Supporting files
- 404.php
- archive.php
- comments.php
- index.php
- search.php
- sidebar.php
- single.php
- composer.json
- package.json
# Design Decisions
- The Company logo is on the left side of the header 
