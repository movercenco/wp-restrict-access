=== Restrict Access ===

To activate the plugin must do the following steps:

1. Go to dashboard / plugins and add plugin after that enable it.

2. You need to add follow code to page-restrict_access.php:

<div class="restrict_access_container">

	<?php	
    $errors = restrict_access_get();
    if(is_wp_error($errors)){
        $error_string = strtok($errors->get_error_message(), '.');
        echo '<p class="error">' . $error_string . '</p>';
    }
    ?>
    <form method="post" autocomplete="off">
        <input type="text" class="username" autocomplete="off" name="email" placeholder="Username...">
        <input type="password" class="password" autocomplete="off" name="password"  placeholder="Password...">
        <input type="submit" value="Login" name="restrict_access_submit">
    </form>
	<p>
       If you would like to access the website BUT do not have a username please email: <br> <a href="mailto:overcencomarin@gmail.com">overcencomarin@gmail.com</a>
    </p>
</div> 