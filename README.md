# Hogwarts-Legacy-Dutch-text
As my daughters aren't fluent yet in English, they found it welcome to use Dutch text instead of English.

For native Dutch speakers:
Dit is een vertaling van alle text van Hogwarts Legacy in het Nederlands. 
1. De eerste versies zijn een directe vertaling uit het Duits naar het Nederlands door Google translate. 
2. Daarna zijn door scripten correcties of the syntax van het vertalingssysteem doorgevoerd. 
3. Uiteindelijk zijn we op het punt dat slechte vertalingen verbeterd worden door handmatige correcties. Zo werden bijvoorbeeld 'Butterbeer' en 'Charms' niet vertaald. Ook blijken idiomen onvertaald, zoals bijvoorbeeld het Engelse 'Copy that professor.' vertaald was als 'Kopieer die professor.' Blijkbaar zijn dus ook in de Duitse vertalingen idiomen oftewel onvertaald oftewel verkeerd vertaald.
Je kan de vertaling op je PC installatie van Hogwarts Legacy installeren, door Hogwarts Legacy in te stellen op Engels en in de map `Hogwarts Legacy/Phoenix/Content/Paks/~mods` het PAK-bestand te plaatsen dat onder `Releases` te vinden is op de `Code` pagina van deze `repository`. Deïnstallatie doe je door het bestand weer te verwijderen.

Als je mee wilt werken aan de verbetering van de vertaling is dat uiterst welkom. :)\
De tekst staat in twee bestanden, namelijk MAINnlNL.json en SUBnlNL.json. \
JSON is een format dat werkt met een Engels sleutelwoord tussen aanhalingstekens, gevolgd door een dubbele punt en spatie, gevolgd door een vervangingstekst tussen aanhalingstekens in de relevante taal en afgesloten door een komma. Bijvoorbeeld `"Chest": "Chest",` (Engels), `"Chest": "Trube",` (Duits) en `"Chest": "Kist",` (Nederlands).\
Als je een tekstfragment tegenkomt dat niet klopt, dan kan je het letterlijke fragment citeren en een vervangend fragment voorstellen. Dit door je door een `issue` te openen en de tekstfragmenten op te schrijven. Ik zal de issue's dan meenemen in de volgende versie van de bestanden.
Je kan ook deze 'repository' 'forken' en correcties maken in je eigen JSON-bestanden en deze als pull-requests indienen, welke ik alleen hoef te 'mergen' in de 'master'-bestanden. Ik stel het op prijs als je zelf de JSON-bestanden test, door ze met parseltongue te converteren naar bin-standen en in te pakken tot PAK-bestand met unrealpak. De handleiding voor deze middelen is herhaald onderaan deze pagina.


Look at the [releases](https://github.com/Markismus/Hogwarts-Legacy-Dutch-text/releases) to get the modded-pak file to use with your PC game of Hogwarts Legacy.

I used the explanation from [modding.wiki](https://modding.wiki/en/hogwartslegacy/developers/localisation).
(I repeated the contents at the bottom of this readme.)



1. I extracted the German binary text-files with FModel.
2. Converted them with parseltongue to json.
3. Cut the Json-file into 5k lines and saved them as docx-files.
4. Used Google translate to generate Dutch language files.
5. Appended everything in a plain json-file and fed it to parceltongue
6. Parceltongue gives exits with errors on line and character position.
7. Edited all syntax problems introduced by Google to json-format and refed it to parceltongue creating a binary-file.
8. Put the binary-files in the correct directory structure ( `packagename\Phoenix\Content\Localization\WIN64` ) and packaged it with compression to pak-file.

In this repository will be the json-files and the pak-file.
The pak-file should be in `Hogwarts Legacy/Phoenix/Content/Paks/~mods`. It will override any files that are identically named.









# Repeat of the explanation from modding.wiki:
<small>
<div style="font-size: smaller;"><p>This tutorial is courtesy of <a href="https://hamstersquad.github.io/" class="is-external-link">tucker</a> from the Hogwarts Legacy Modding discord server.</p> <h1 id="tools-needed" class="toc-header"><a href="#tools-needed" class="toc-anchor">¶</a> Tools needed</h1> <ul><li><a href="https://www.fluffyquack.com/tools/unrealpak.rar" class="is-external-link">UnrealPak’s fluffyquack</a> - for packing .pak file</li> <li><a href="https://github.com/4sval/FModel" class="is-external-link">https://github.com/4sval/FModel</a> - for extracting stuff from .pak</li> <li><a href="https://github.com/lordvoldem0rt/parseltongue" class="is-external-link">https://github.com/lordvoldem0rt/parseltongue</a> - for converting .bin files</li></ul> <h1 id="extracting-files-with-fmodel" class="toc-header"><a href="#extracting-files-with-fmodel" class="toc-anchor">¶</a> Extracting files with Fmodel</h1> <ol><li><strong>Open your Fmodel and select the game location</strong><br> <code>..\Steam\steamapps\common\Hogwarts Legacy</code></li> <li><strong>Go to pakchunk0-windowsNoEditor.pak</strong></li> <li><strong>Extract .bin and .ufont files by right-clicking &gt; Export Raw Data</strong><br>
.BIN files are located in <code>Phoenix\Content\Localization\WIN64</code><br>
.UFONT are located in <code>Phoenix\Content\UI\Fonts</code><br>
*<em>The game uses Hybrid for subtitles and UI texts, ColumnaCon for UI title/heading texts, FordsFolly for letters, and AscenderUni for your character name in the character-creating menu.</em></li> <li><strong>Your exported files should be in Output &gt; Exports</strong></li></ol> <h1 id="creating-a-folder-for-your-mod" class="toc-header"><a href="#creating-a-folder-for-your-mod" class="toc-anchor">¶</a> Creating a folder for your mod</h1> <p>Create a folder anywhere on your PC, naming it <code>whatever_P</code>. Copy your exported Phoenix folder and place it there. (This will keep the directory structure of .pak file)</p> <h1 id="editing-bin-and-ufont" class="toc-header"><a href="#editing-bin-and-ufont" class="toc-anchor">¶</a> Editing .BIN and .UFONT</h1> <h2 id="bin" class="toc-header"><a href="#bin" class="toc-anchor">¶</a> .BIN</h2> <p>Drag and drop .BIN files into <code>Parseltongue.exe</code> (one by one) and you will get a .JSON file. Try editing some of the texts that can be tested easily like “WARNING: Read before playing.” Save the files drag and drop them back into <code>Parseltongue.exe</code>, you’ll get .BIN files, and then replace the original files with them.</p> <h2 id="ufont" class="toc-header"><a href="#ufont" class="toc-anchor">¶</a> .UFONT</h2> <p>They are basically .TTF files. You can just find new .TTF fonts that support your language and change their extensions to .UFONT then replace the original files</p> <p>Personally, I use <a href="https://fontforge.org/en-US/" class="is-external-link">FontForge</a> to merge the original fonts with my fonts.</p> <h2 id="packing-pak-file" class="toc-header"><a href="#packing-pak-file" class="toc-anchor">¶</a> Packing .PAK file</h2> <p>Drag and drop your <code>whatever_P</code> folder into <code>UnrealPak-With-Compression.bat</code>, you ‘ll get <code>whatever_P.pak</code>.</p> <p>Put your .PAK in <code>\Hogwarts Legacy\Phoenix\Content\Paks\~mods</code></p> <h1 id="testing" class="toc-header"><a href="#testing" class="toc-anchor">¶</a> Testing</h1> <p>Run the game and see if it works</p></div>
</small>
