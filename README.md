# kisslib
A kiss principle ebook quick launcher application for Linux systems

#### Quick navigation

- [What is it about?](https://github.com/jrie/kisslib#whats-is-it-about)
- [But why? Doesnt ebook reader XY do that?](https://github.com/jrie/kisslib#but-why-there-are-tons-of-good-readers-like-xy-the-movivation-behind-kiss-ebook)
- [Show me! - Screenshot gallery link and previews](https://github.com/jrie/kisslib#show-me---screenshot-gallery)
- [Where does it work? - Tested on...](https://github.com/jrie/kisslib#where-does-it-work---tested-working-on)
- [I want to use it! - Not to compile...](https://github.com/jrie/kisslib#i-want-to-use-it-not-to-compile-heres-how)
- [Debian Jessie or Distros with older libraries (Jessie Version code)](https://github.com/jrie/kisslib#debian-jessie-or-distros-with-older-libraries)
- [Can I? - Is it easy to use? - File support and usage guide](https://github.com/jrie/kisslib#can-i-is-it-easy-to-use---file-support-and-usage-guide)
- [Compiling](https://github.com/jrie/kisslib#compiling)
- [Compiling of the "jessie" versions, not only Debian Jessie](https://github.com/jrie/kisslib#compilation-of-the-jessie-version-not-only-debian-jessie)
- [ToDos and future plans](https://github.com/jrie/kisslib#todo-and-future-plans)
- [Known issues](https://github.com/jrie/kisslib#known-issues)


## Whats is it about?
kisslib aka "KISS Ebook" or "KISS Ebook Starter" is a work in progress ebook launcher supporting .pdf, .epub, .mobi, .chm ebook files, works completely offline and helps you manage and launch your ebooks from a single place, giving you hints about the authors and tiles and the format of your ebooks.

Its not a ebook viewer of any kind, its whole purpose is to allow to quickly go through an ebook collection and launching an own defined viewer (if you like with commands) for the supported ebook types. While displaying general information about a ebook file like format, author and title.

### But why? There are tons of good readers, like XY... the movivation behind KISS Ebook
The motivation to write this application is simple. Most programs read out particular formats or maybe dont support all of them, so you need a special applciation to handle pdf, but not the same to handle chm files.

Kiss Ebook Starter simply allows you to read all supported ebook formats into Kiss Ebook and from there, launch the particular application you want, with the settings/commands you provide, for example opening all pdfs in full screen if you like that, if that is a feature supported by the viewer - for example through a command line option.

Kiss Ebook shows you therefore the format, the authors and the titles of the ebooks as possible, in order to allow you to quickly find a particular ebook and then, launch it, either by double clicking a starter icon or by using a keyboard shortcut.

You also can, edit the authors and details inside Kisslib, which allow you a quicker navigation. The ebook itself is untouched in this process and those informations are only stored in the database.

Please also see the future plans and ToDo list of what Kiss Ebook should be able to do in the future, to aid you in managing your ebook collection(s).


## Show me! - Screenshot gallery
The screenshots are taken under Debian Stretch using Xfce desktop with default settings and the dark screenshots with Debian Sid with Xfce Breeze theme.

A gallery with screenshots (also development steps), newest first, can be found here:
https://www.picflash.org/gallery.php?id=9RGDIIE7K8

Examples of KISS Ebook

[![Screenshot Kiss Ebook during import](https://www.picflash.org/img/2016/12/22/TB2e8osytx7rywios.png "Screenshot Kiss Ebook during import")] (https://www.picflash.org/viewer.php?img=2e8osytx7rywios.png)

And on default Xfce (Debian Testing):

[![Screenshot Kiss Ebook with opened edit ebook details-dialog](https://www.picflash.org/img/2016/12/29/TBtiobsygvs14u1mu.png "Screenshot Kiss Ebook with opened edit ebook details-dialog")] (https://www.picflash.org/viewer.php?img=tiobsygvs14u1mu.png)


## Where does it work? - Tested working on...
* Debian Sid/Unstable and Stretch/Testing (Tested 28.12.2016)
* Debian Jessie/Stable requires "kisslib-jessie" or related "kisslib-jessie.c" due to earlier library versions (Tested 28.12.2016)
* Fedora Workstation 25 - and can run with the "kisslib" binary (Tested 29.12.2016)
* CentOS 7 using "kisslib-jessie" and related files (Tested 29.12.2016)
* openSuse Tumbleweed (Tested 30.12.2016)
* Sparky linux (Tested 30.12.2016)
* your favourite Linux distro here! (please get in touch and I try to test it if it runs on your flavour)


## I want to use it, not to compile! Heres how:
Download "kisslib" which is a Linux 64bit binary and install the following dependencies to run it, please note that the library names may wary on your distribution.

* libzip4 
* libsqlite3
* libgtk-3-0

Then give kisslib executeable permissions and start it using:
```
chmod +x kisslib
./kisslib
```


### Debian Jessie or distros with older libraries
Please see also the known issues at the bottom, as there are slight issues with this version.

Download "kisslib-jessie" which is a Linux 64bit binary.

* libzip2
* libsqlite3
* libgtk-3-0

Then give kisslib executeable permissions and start it using:
```
chmod +x kisslib-jessie
./kisslib-jessie
```


## Can I..., is it easy to use? - File support and usage guide

Supported file types which are handled are:
* pdf
* epub
* mobi
* chm

In order to make use of KISS Ebook, you have to first import any supported ebook files.
Its possible to import files and folders using the menu "Import files and folders" or by dragging and dropping files and or folders onto the ebook list, data then is processed in order to display information like author, title and file format when available of the supported ebook file formats, for pdf-files if no title is found, the filename is used in the list view.

The data is then stored into the sqlite3 database "kisslib.db" and is then again available if you open kisslib.
Entries can be removed by pressing the "Del"-key.

In order to quickstart any ebook file, you have to go under the menu "Operations" and select "Set launcher applications".
In this dialog, you can enter for each ebook type a program name, for example "evince" for .pdf files.

After saving and doing so once pdfs and other set then can be opened by clicking in the "Open icon" in the "Open" column of the particular ebook in the list or by pressing "Control-S" when the ebook is selected. If thats a pdf, "evince /home/tux/YourPDF.pdf" becomes executed and should happily open the PDF for you in this viewer.

Please note, launcher applications can have now parameters added to them, for example "evince -f" would start evince in fullscreen when launched.

Also the author and title fields can be edited and are saved instantly in the table view or by pressing "Control-E", this will open the edit ebook details dialog, which is also available in "Operations" > "Edit ebook details".

In case a title is misleading, it is possible to get the actual file name into the field when editing in the table view. To do so, the field has to be emptied (meaning to remove all text in it) and if there is no data present, the actual filename becomes added to the list cell. If the author field is cleared in the table view, the generel placeholder "Unknown" is set and directly saved to the database.

For a quick search in the collection, it is possible to use type ahead find on the titles. Meaning, searching the titles can be done by simply typing in the application going with the first letters of the title as displayed in KISS Ebook.


## Compiling

### Requirements and compilation (kisslib non "jessie" version)
* libzip4/libzip-dev for compiling (used for epub support)
* libsqlite3-dev (as datastore)
* libgtk-3-dev (GUI)
* Linux like system (having GNU C extensions, for directory listing and exec)
* gcc - to compile

Compile using gcc:

```gcc kisslib.c kiss-front.c -Wall -std=c99 -O3 -g `pkg-config --cflags gtk+-3.0` -lzip -lsqlite3 `pkg-config --libs gtk+-3.0` -o kisslib```


Then "chmod +x kisslib" to allow the system to execute it.
And then run "./kisslib" to open kisslib.


### Compilation of the "jessie" version (not only Debian Jessie!)

The same may wary slightly, depending on your distro.

If you want to link against an earlier version, you need:
* libzip-dev/libzip2
* libsqlite3-dev

```gcc kisslib-jessie.c kiss-front-jessie.c -Wall -std=c99 -O3 -g `pkg-config --cflags gtk+-3.0` -lzip -lsqlite3 `pkg-config --libs gtk+-3.0` -o kisslib```

Then "chmod +x kisslib" to allow the system to execute it.
And then run "./kisslib" to open kisslib.


## ToDo and future plans

Striked out items are implemented already.

* ~~Introduce the usage of "content.opf" for epub reading, which includes the ebook title and the author(s)~~
* Add a option dialog, which has at least one option/setting (turned on by default) to ignore read out of already read out files
* Add the ability to sort by format, author and title
* Add a option to sort by default on format, authors or title on startup
* Add a search option to only show files with particular tile, author or format
* Add a check to detect "default readers" installed, which can access particular ebook formats, which are then set as default launchers (please propose your favorite readers by raising an issue or by email! I know only a mouthful and not every distro/flavour)
* your feedback and feature suggestions! (please open an issue or contact me by email)


## Known issues
* If you upgrade from a previous version and there are any sql errors while saving the launcher applications, you most likely once need to delete the "kisslib.db" so that all sqlite tables are properly recreated (due to changes for the launcher applications) - this is a one time action, but youve got to reimport your ebooks after this step
* In some cases the dialog for "import files and folders", "edit ebook details" and "set launcher applciations" are opened **behind** the main window. Please note that when those dialogs are open, and the main application state is set to background and not handle input at this time, so you must move the main window away in order to reach the dialogs, please report it if you see this happening on any distro mentioned
* found another issue? (please report it or email me)
