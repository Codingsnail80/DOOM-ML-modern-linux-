This is a small port of the original doom to a modern linux distro, I did not include the wad files neccesary to play the game you will have to get those yourself.
However if you are on a debian based linux distro (that includes ubuntu and raspberry pi os) you can install a package that gives you the doom1.wad file. run this:
sudo apt update && sudo apt install doom-wad-shareware
Just press y when it askes you. Do not be alarmed if you see a few apps installed on your computer its just doom and a knock of version of doom. The reason these are installed is because the computer thinks they are required to use the wad files but if your here chances are your going to compile the game yourself. You can delete these afterward if you would like however the "woof" version of doom that is installed is very well done and even uses a more modern control layout.
The next command you will need to run is:
find / -name "*.wad" 2>/dev/null
this command will give you a list of the installed wad files on  your system, you want the doom1.wad file, you will need this later to play the game so either copy it to a more memorable location or just come back to this command later.
Now you will need to actually compile the code. So your next step is to clone this repository onto your computer, for this you will either need to download the zip file or use the command:
git clone <the url for the project>
if you dont already have git installed install it with:
sudo apt install git
once you have the it downloaded you should see a folder called DOOM, in that folder there is another folder called linuxdoom-1.10 navigate into that folder.
there will be many files but you now need to install some tools to compile and run this. To do this you will need to run:
sudo apt install build-essential cmake libsdl2-dev libsdl2-mixer-dev libsdl2-net-dev libsdl1.2-dev xserver-xephyr
I know thats a lot of commands but its neccesary. At this point you are feeling uncomfterbal with what we have been doing you will probably want to stop here and just download a already made version. This is mostly for those who like a more hands on aproach and already have some experience with the terminal and commands. From this point forward if you dont already have some experience you might be a little bit overwhelmed. Now lets continue.
You should have everything you need to compile this now but be warned this isnt the most playable port to linux, the audio doesn't function and the way that I handle the old 8-bit color depth results in a small screen size for the game. But if you arn't swayed yet the next thing you need to do is go to the terminal and navigate to the linuxdoom folder I mentioned eairlier. Once in this folder you need to run:
