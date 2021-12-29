<?php


Error_Reporting(0);



	$hostname				= "localhost";					// Õîñò

	$mysql_login			= "ËÎÃÈÍ";						// Ëîãèí ê ÁÄ

	$mysql_password			= "ÏÀÐÎËÜ";							// Ïàðîëü ê ÁÄ

	$database				= "ÁÀÇÀ";						// Áàçà äàííûõ

	$num					= 10;							// Êîë-âî âûâîäîâ íà ñòðàíèöó

	$cfgURL					= "ñàéò áåç http";						// URL ðåñóðñà

	$chmod					= "755";						// Ïðàâà ïàïêàì íà çàïèñü


// Äàííûå ëèöåíçèè. Ñëåäóþùèå ïåðåìåííûå ïîñëå óñòàíîâêè ñêðèïòà ÍÅ ÌÅÍßÒÜ!



  $licID				= 743;										// ID ëèöåíçèîííîé êîïèè

  $key					= "0W40-0N6E-W0HT-7863";					// Ëèöåíçèîííûé êëþ÷

  $mdhash				= "434dc8a33d7f9c85eb44fdf778619802";		// MD5 hash



// Ñîåäèíåíèå ñ ÁÄ
if (!($conn = mysql_connect($hostname, $mysql_login , $mysql_password))) {
	include "includes/errors/db.php";
	exit();
} else {
	if (!(mysql_select_db($database, $conn))) {
		include "includes/errors/db.php";
		exit();
	}
}
// Êîíåö ñîåäèíåíèÿ ñ ÁÄ

mysql_query("SET NAMES 'cp1251'");

set_magic_quotes_runtime(0);
@set_time_limit(0);
@ini_set('max_execution_time',0);
@ini_set('output_buffering',0);
$safe_mode = @ini_get('safe_mode');
$version = "1.24";

if(version_compare(phpversion(), '4.1.0') == -1) {
 $_POST   = &$HTTP_POST_VARS;
 $_GET    = &$HTTP_GET_VARS;
 $_SERVER = &$HTTP_SERVER_VARS;
}

if (@get_magic_quotes_gpc()) {
	foreach ($_POST as $k=>$v) {
		$_POST[$k] = stripslashes($v);
	}
	foreach ($_SERVER as $k=>$v) {
		$_SERVER[$k] = stripslashes($v);
	}
}

define('ACCESS', true);
?>
