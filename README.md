# Journey to the centre of the computer

[⬅ Version FR](./README-FR)

You've already discovered a ton of useful commands in the quests and during the lesson on the
console.<br>
The problem is, it's going to be difficult for you to remember all of this in such a short time!

Don't worry, in this workshop you will just walk quietly around in your computer,
using only the console.<br>
You can go ahead and close your file manager, it will be totally useless for this trip.
Launch the Console and let it guide you.

If you are on Windows, use the `git bash` console.<br>
If you are on MacOS, your console application is called 'Terminal'.
{: .alert-warning}

## Before you travel, visit your own home

If you've just opened the console, you should be at home (in your user folder). To be sure of that, you can execute the following command:  
`cd ~`

- The `cd` command means change directory.
- The tilde `~` is a shortcut to your user folder.

This command is supposed to access a folder, but if you execute it with the parameter `~`, it allows you to teleport into your home!

Your command prompt should look something like this:

```bash
wilder@wilder-ThinkPad-T430:~$
```

- The first element before the code>@ is you! (your username).
- The second element after the `@` up to the colon `:` is the name of your computer.
- After the `:`, is your position in the computer (here the tilde `~`).
- After the `$` is where you can type your commands.

Caution, your user folder does not correspond to the deepest part of your computer. (This is called the root)  
If you want to know the actual path to your user folder, you can use the following command:

```bash
pwd
```

The command `pwd` is used to display the real path to the folder you are in. So, here you are in your user folder, represented by the tilde `~`, the path that appears should be something like this, depending on your computer:

```bash
/home/wilder
```

- `/home/` contains all user folders on this computer
- `wilder` (or your username) that contains your user folder

On Windows and OSX the path won't be the same, but you'll see a resemblance.
{: .alert-warning}

## Know your roots

Now that you know the `path` to your user folder, let's look at it again. You can see that the path starts with a slash `/` and each folder is separated by a `/`.

The first slash `/` represents the deepest path of your computer: the `root`.  
Go visit it! To do this, use the command that allows you to access a folder, specifying the path to the root:

```bash
cd /
```

And since it's dark in there, let's use the command that displays the list of files and folders:

```bash
ls
```

Wow, there's a bunch of files, all displayed next to each other! Not very convenient to get around or find. If you want to display the list of files vertically, and in more detail, use the following command:

```bash
ls -l
```

## Temporary files

You have previously seen all the places you can visit from the root. However, since some are more dangerous than others, you will start with the safest of the many places you can visit. Your machine: `/tmp` !  
Access the folder `/tmp` and displays everything it contains.  
It's a mess in there! In fact, this folder contains temporary files, which are sometimes used when installing or running programs on your computer.

You can safely delete or create anything you want in this folder. So you're going to create a file to pollute your computer a little more!

```bash
echo "Hello, world" > helloWorld.txt
```

Observe this command in detail:

- The `echo` command is used to display text in the console.
- The `>` symbol is used to store the result of a previous command in a file, specifying next. You can use it with anything you want, not only `echo`.

When displaying the list of files, you should see your new `helloWorld.txt`.  
If you want to display the contents of the file, you can use the following command:

```bash
cat helloWorld.txt
```

Let's change the content of the file now:

```bash
echo "Hello there" > helloWorld.txt
```

If you view the contents of the file, you can see that it has been overwritten by the new text.

Now we could change the file name to match the new text:

```bash
mv helloWorld.txt helloThere.txt
```

The `mv` command is used to move a file from one location to another, but it can also be used to rename a file.

We can now delete the file with the following command:

```bash
rm helloThere.txt
```

If you display the contents of the directory, the file is no longer there, it has been deleted. permanently.

There's not really any "trash" in terminal, so be careful what you delete files and folders because it will be extremely difficult to retrieve it!
{: .alert-warning}

## Software skyscrapers

Go to the place where it is usually advised to install the software on your computer:

- `/opt` for Linux
- `/usr/share` for Windows
- `/usr/local` for OSX

Just for fun, you'll try to create a folder here, using the command:

```bash
mkdir tacosfolder
```

You should have the following response:

```bash
mkdir: cannot create directory tacosfolder: Permission denied
```

Indeed, this folder (and several others) is protected, as you didn't specify who you were, Linux doesn't let you get to it. You can, however, as long as you have the correct rights, force commands using the following command: `sudo`

On Windows, the `sudo` command does not exist. But don't panic, you can set it up! Execute the following command: `curl -s https://raw.githubusercontent.com/imachug/win-sudo/master/install.sh | sh`  
Then reboot your console and you'll have access to the command!\_ Alone, the command is not useful, you have to place it in front of the command you want to force. Try to combine it with the previous command.
{: .alert-warning}

Rather than retyping the whole command, use the up arrow on your keyboard. The up/down arrows will allow you to browse through the history of commands you have already typed. Use the left arrow to go back to the beginning of the line and type `sudo` (and a space).  
You can also use the shortcuts `Ctrl+A` and `Ctrl+E` to automatically place your cursor at the beginning and end of the line.

You should have the following line:

```bash
sudo mkdir tacosfolder
```

The console should ask you for your password to check your privileges:

```bash
[sudo] password for wilder:
```

When you enter a password in the console, nothing appears on the screen: this is normal, but rest assured, what you type is taken into account.

Let's take a look at this new folder.

```bash
cd tacosfolder
```

Now, let's delete that empty folder. This is done in the parent folder: rather than having to retype the path each time, uses the following shortcut:

```bash
cd ..
```

This command allows you to go up from a folder in the tree structure.

Under Linux, a single dot `.` represents the current folder and two dots `..` represents the parent folder.
If you write the command:

```bash
cd .
```

You're accessing the current file, so it doesn't matter!

Now that you're sure you're in the right place, delete the folder using the following command:

```bash
sudo rm -r tacosfolder
```

- the `sudo` command is used to force the hand, because you are in a protected folder
- the `rm` command allows you to delete a file
- the `-r` parameter is used to specify that you want to delete a file and everything it contains

## Mountains of documents

To end off this workshop, go back to your user folder, then to its subfolder `Documents`.

Rather than having to type all of it manually, and knowing that the shortcut to your file user is the tilde `~`, you can use the command:

```bash
cd ~/Documents
```

Take this opportunity to use the command that allows you to see the real path from where you are.  
Here we'll have all the rights to have fun building a little cottage for the holidays!  
Start by creating a `chalet` folder.

While remaining in `~/Documents`, create an empty `armchair1` file using the following command:

```bash
touch armchair1
```

Move the `armchair1` file into the `chalet` folder using the following command:

```bash
mv armchair1 chalet
```

Create the following folders in the `~/Documents/chalet` subfolder:

- `armour`
- `cabinets`
- `cupboards`

Then, access the `chalet` folder and start writing the following command (without pressing on the `Enter` key at the end):

```bash
cd c
```

At the end of the line, press `Tab` twice: the console should show you all folders beginning with `c`.

Complete your order with:

```bash
cd ca
```

Then press `Tab`. The console should complete the whole command.  
We call it autocomplete!

Execute the command to go to the `cabinets` folder, then uses the command to go back to the previous file.

Finally, we'll add some chairs to our `chalet`, one is not enough!  
Use the following command to copy a file:

```bash
cp armchair1 armchair2
```

Display the contents of the directory and you'll find two chairs!

Finally, still in your `chalet` folder, create a file `trinkets`.
Access the `cabinets` folder. Move the `trinkets` file from the previous directory to your current folder. To do this, uses the following command:

```bash
mv ../trinkets .
```

As seen previously, the two dots `..` represent the parent folder and the dot `.`. represents the current file.

When the `trinkets` file is present in your `cabinets`, don't move from there, copy this file into the `cupboards` folder, present in `chalet`.
Finally, we will observe the contents of your `chalet`. To do this, go back to `~/Documents`.
Try the following command:

```bash
find chalet
```

If you've done your homework, your cottage will look like this:

```bash
chalet   chalet/armchair1   chalet/cabinets   chalet/cabinets/trinkets   chalet/armour   chalet/armchair2   chalet/cupboards   chalet/cupboards/trinkets
```

Congratulations! You can continue to have fun with your cottage. Remember to delete it later (using the command line) when you're done playing!
