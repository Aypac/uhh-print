<h1>UHH Physnet Printing script</h1>

This script is desinged for printing in the physnet remotely from your PC, preferably running linux (developed under Ubuntu).

To archive this, it will log into your account with ssh, scp the files up, print via lpr and check the queue with lpq. If you don't understand this, don't worry, you won't need to.

<h2>WHAT YOU'LL NEED</h2>
- The files you want to print as PDFs without password in one folder
- Your Physnet-Username (Usually first letter of your first- and first seven letters of
	your lastname; e.g. rvollmer for René Vollmer)
- The password
- Internet-Access


<h2>HOW TO INSTALL THE SCRIPT</h2>
<h3>Required libs</h3>
sudo apt-get install expect

sudo apt-get install expectk

more: http://www.cyberciti.biz/tips/execute-commands-on-multiple-hosts-using-expect-tool-part-iii.html

mkdir ~/UH\ PRINT/

Extract the zip into that folder. Then:

sudo chmod +x ~/UH\ PRINT/uhhprint.exp

scp ~/UH\ PRINT/remote_printScript_file.sh yourusername@asterix01.physnet.uni-hamburg.de:~/

create a file Deckblatt.pdf like the one in the zip inside this folder. You can use e.g. open office for this. Then:

scp ~/UH\ PRINT/Deckblatt.pdf yourusername@asterix01.physnet.uni-hamburg.de:~/print/

or just start the script and select s when asked for the Cover page.

<h3>Advanced</h3>
You can open the .exp-Files with an editor of your choice and edit the default values.

<h3>Recommended</h3>
sudo cp ~/UH\ PRINT/uhhprint.exp /bin/uhhprint

sudo chmod +x /bin/uhhprint

enables you to start the script with the command "uhhprint"

You have to repeat that with any change in default values or new versions.

<h3>Cool: Quickstarter for Ubuntu</h3>
sudo apt-get install gnome-tweak-tool gnome-panel

gnome-desktop-item --create-new ~/UH PRINT/launcher.desktop

Select:

*Aplication in Terminal

*uhhprint

*Name, icon and description desired

Drag and drop the icon into the starter on the left


<h2>Flattr me</h3>
This took me ages to programm and can save you eternities and many pages.

<a href="https://flattr.com/submit/auto?user_id=FetterChiller&url=https%3A%2F%2Fgithub.com%2FAypac%2Fuhh-print" target="_blank"><img src="//button.flattr.com/flattr-badge-large.png" alt="Flattr this" title="Flattr this" border="0"></a>
