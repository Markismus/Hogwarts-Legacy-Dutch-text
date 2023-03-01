# Hogwarts-Legacy-Dutch-text
As my daughters aren't fluent yet in English, they found it welcome to use Dutch text instead of English.

So I used the explanation from here: https://modding.wiki/en/hogwartslegacy/developers/localisation
1. I extracted the German binary text-files with FModel.
2. Converted them with parseltongue to json.
3. Cut the Json-file into 5k lines and saved them as docx-files.
4. Used Google translate to generate Dutch language files.
5. Appended everything in a plain json-file and fed it to parceltongue
6. Parceltongue gives exits with errors on line and character position.
7. Edited all syntax problems introduced by Google to json-format and refed it to parceltongue creating a binary-file.
8. Put the binary-files in the correct directory structure ( packagename\Phoenix\Content\Localization\WIN64 )and packaged it with compression to pak-file.

In this repository will be the json-files and the pak-file.
The pak-file should be in the mods directory in the pak directory. It will override any files that are identically named.
