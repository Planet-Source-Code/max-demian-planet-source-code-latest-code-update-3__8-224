<div align="center">

## Planet Source Code Latest Code \*UPDATE \#3\*


</div>

### Description

Get the latest code from www.pscode.com (Planet Source Code), from any world. Makes use of looping & regular expressions (the hard part), since psc's latest code ticker had the code on 2 lines & had to use 2 regular expressions & 2 loops for each code, not easy. But bettter than most codes you see that will just grab the whole ticker code, mine parses & just takes the links. *UPDATE*, I changed it form lngWID=# to world=# (just seems easier), & now you dont just have to put the number in, you can put like: world=vb or world=c . *UPDATE #2*, Does the EXACT same thing as the first update but I changed it so it doesnt have the code to get & parse the source 9 times, I made it into a funtion (psccode) so it can just do psccode(number); example: psccode(1); would be for vb. Cuts the code down ALOT, bout 1/3 the size now. *UPDATE #3* lets you choose what PSC URL you want to use (only changed function and how it is used). hopefully ill get it working where you can choose how many urls you want to get & have 0 get them all done soon.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Max Demian](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/max-demian.md)
**Level**          |Advanced
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__8-9.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/max-demian-planet-source-code-latest-code-update-3__8-224/archive/master.zip)





### Source Code

```
<?
// Planet Source Code Latest Code *UPDATE #3*
// Writer: Max - Demian Net
// E-Mail: Max@Wackowoh.com
// WebSite: http://www.DemianNet.com http://www.Wackowoh.com
// Language: PHP
// Usage:
// include("psc.php?world=World+Number+or+Name");
// or
// require "psc.php?world=World+Number+or+Name";
// examples
// include("psc.php?world=1");
// require "psc.php?world=vb";
// Worlds:
// Visual Basic = 1 or vb
// Java/Javascript = 2 or java
// C/C++   = 3 or c
// ASP/VBScript = 4 or asp
// SQL    = 5 or sql
// Perl   = 6 or perl
// Delphi   = 7 or delphi
// PHP    = 8 or php
// PSC URLs:
// www.planet-source-code.com
// www.planetsourcecode.com
// www.pscode.com
// www.1aspstreet.com
// www.1activeserverpagesstreet.com
// www.1cstreet.com
// www.1cplusplusstreet.com
// www.1delphistreet.com
// www.1javastreet.com
// www.1javascriptstreet.com
// www.1perlstreet.com
// www.1phpstreet.com
// www.1sqlstreet.com
// www.1vbstreet.com
// www.1visualbasicstreet.com
// www.cpluspluscode.com
// Variables:
$url = "www.planet-source-code.com";
// None of this needs to be edited
function psccode($sec, $thesite) {
 $buffer = implode("", file("http://".$thesite."/vb/linktous/ScrollingCode.asp?lngWId=".$sec));
 preg_match_all("|(<a target[^>]+>)|U", $buffer, $psccodeurl, PREG_PATTERN_ORDER);
 preg_match_all("|([a-zA-z].*</a></b></font>)|U", $buffer, $psccodename, PREG_PATTERN_ORDER);
 $i = 0;
 echo "<base href=\"http://".$thesite."\">\n";
 for ($i = 0; $i < count($psccodeurl[1]);$i++){
 echo "{$psccodeurl[1][$i]}{$psccodename[1][$i]}<br>\n";
 }
}
if ((1 > $world) or ($world > 8)) {
 if ($world == "vb") {
 psccode(1, $url);
 } elseif ($world == "java") {
 psccode(2, $url);
 } elseif ($world == "c") {
 psccode(3, $url);
 } elseif ($world == "asp") {
 psccode(4, $url);
 } elseif ($world == "sql") {
 psccode(5, $url);
 } elseif ($world == "perl") {
 psccode(6, $url);
 } elseif ($world == "delphi") {
 psccode(7, $url);
 } elseif ($world == "php") {
 psccode(8, $url);
 } else {
 echo "No World or Invalid World Entered. Format:<BR>\nhttp://".$HTTP_HOST.$PATH_INFO."?world=(World Number)";
 }
} else {
 psccode($world, $url);
}
?>
```

