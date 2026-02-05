This is a small port of the original doom to a modern linux distro, I did not include the wad files neccesary to play the game you will have to get those yourself.
However if you are on a debian based linux distro (that includes ubuntu and raspberry pi os) you can install a package that gives you the doom1.wad file. run this:
sudo apt update && sudo apt install doom-wad-shareware
Just press y when it askes you. Do not be alarmed if you see a few apps installed on your computer its just doom and a knock of version of doom. The reason these are installed is because the computer thinks they are required to use the wad files but if your here chances are your going to compile the game yourself. You can delete these afterward if you would like however the "woof" version of doom that is installed is very well done, and even uses a more modern control layout.
The next command you will need to run is:
find / -name "*.wad" 2>/dev/null
This command will give you a list of the installed wad files on  your system. You want the doom1.wad file. You will need this later to play the game so either copy it to a more memorable location or just come back to this command later.
Now you will need to actually compile the code. So your next step is to clone this repository onto your computer, for this you will either need to download the zip file or use this command:
git clone https://github.com/Codingsnail80/DOOM-ML-modern-linux-.git
If you dont already have git installed install it with:
sudo apt install git
Once you have the it downloaded you should see a folder called DOOM, in that folder there is another folder called linuxdoom-1.10 navigate into that folder.
There will be many files but you now need to install some tools to compile and run this. To do this you will need to run:
sudo apt install build-essential cmake libsdl2-dev libsdl2-mixer-dev libsdl2-net-dev libsdl1.2-dev
I know thats a lot of commands but its neccesary. At this point you are feeling uncomfortable with what we have been doing you will probably want to stop here and just download a pre-compiled version. This is mostly for those who like a more hands on aproach and already have some experience with the terminal and commands. From this point forward if you dont already have some experience you might be a little bit overwhelmed. Now lets continue.
You should have everything you need to compile this now but be warned this isnt the most playable port to linux, the audio doesn't function and the way that I handle the old 8-bit color depth results in a small screen size for the game. But if you aren't swayed yet the next thing you need to do is go to the terminal and navigate to the linuxdoom folder I mentioned eairlier. Once in this folder you need to copy the doom1.wad file to here then run:
export DOOMWADDIR=/entire/path/to/folder/where/wad/file/is
The file path can easily be obtained by just copying the file and pasting it into the terminal, just make sure you delete the actual file from the path you pasted, it needs to be just the folder its in. For example, if my file path was /root/home/username/doom1.wad then it would delete "/doom1.wad" so it would be come /root/home/username. Ensure you do not leave a "/" at the end of the path too because that can sometimes mess up programs. If you cant just copy the file and paste it then use your file manager to find the file path. There are plenty of videos on the internet to help with that. **Sizure warning!!!** this next command will flash a lot of text on the screen very quickly with lots of colors! Now that you are ready you need to run:
sudo make -e
Dont be alarmed! There should be lots of text flashing on your screen, that is normal. It is just giving details on the process but everything should work. If it is giving you warnings you can ignore those too. Warnings are quite common when compiling code and are not really important. Depending on how fast your computers processer is it will take from a litte less than a minute to several minutes. If you are on a really old computer this might take even longer because it depends on your cpu speed.
Once its done compiling your ready to play the game! Just run:
./linuxxdoom
If everything went correctly then you should see the game on the window we made earlier. If not refer back to previou steps.
----------------------------------------------------------------------------------------------------------------------------------------------------
Cretit goes to Diego Crespo for writing an artical documenting the process of porting Doom to linux, I used his tweaks and some of my own to the games code to acheive this. Here is his article: https://www.deusinmachina.net/p/lets-compile-linux-doom
