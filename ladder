<?php


$file = file_get_contents("http://armory.warmane.com/ladder/2v2/Frostwolf");

$doc = new DOMDocument();

libxml_use_internal_errors(true);
$doc->loadHTML($file);
libxml_clear_errors();

$xpath = new DOMXpath($doc);
$nodes = $xpath->query("//*[@id=\"data-table-list\"]/tr");


foreach ($nodes as $node){

	echo "</br>Rank: " . $node->childNodes[1]->textContent;
	echo "</br>Name: " . $node->childNodes[3]->textContent;
	echo "</br>Guild: " . $node->childNodes[5]->textContent;
	$name = $node->childNodes[3]->textContent;
	$json_string	=	file_get_contents("http://armory.warmane.com/api/character/" . $name ."/Frostwolf/summary");
	$minfo			=	json_decode($json_string);
	echo "</br>Status: " . ($minfo->online > 0 ? "<font color='green'>Online</font>" : "<font color='red'>Offline</font>");
	echo '</br>';

}
?>
