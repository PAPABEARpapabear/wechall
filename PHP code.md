PHP code
<?php

if (isset($_GET['which']))

{

	$which = $_GET['which'];

	switch ($which)

	{

	case 0:

	case 1:

	case 2:

		require_once $which.'.php';

		break;

	default:

		echo GWF_HTML::error('PHP-0817', 'Hacker NoNoNo!', false);

		break;

	}

}

?>


http://www.wechall.net/challenge/php0817/index.php?which=solution
