# FunInstaller

THIS IS NOT READY TO TRY YET:
I have this here to modify into a Funtoo or Gentoo Linux distribution installer. This is from the installer used for elementary OS.

The aim of this project is to eventually allow users to install Funtoo Linux onto their PC, as easy as it is to install elementary OS onto their PC.

There will clearly be a lot of differences between this installer, and the elementary OS installer's current code. The current code is 100% elementary OS's installer code. I'm just starting with this so that I can see how some things are done, and to save me some work for things that the current code will be fine to use for. I imagine most of the code is going to be completely removed, and replaced with code that will allow the installation of Funtoo, but we'll see, since I don't yet know. The elementary OS logo images are going to be replaced with Funtoo ones, if I am allowed to use those images.





# Why I am doing this:

- To make me understand a lot more about how things work.
- To give people an easy way to have a super fast source code based distribution on their own systems.
- To provide people with an easy way to set up a system that they never have to erase just because of some release schedule.
- I also wanted a really convienient way to be able to set up Funtoo on new computers that I get, so that I can just walk away and let it install everything.

I got tired of having to wipe my Fedora and Ubuntu distributions on my PC's everytime they went out of support. Plus I had always wanted my systems to be as fast as possible, so that's why I switched over to Funtoo. I figured this could be a cool way to introduce people to a different kind of Linux distribution, one that they'll never have to erase just because of some kind of release schedule, one that's really fast, and one that is using stable versions of software.




# Goals:


I will later build, or probably just modify, a separate software center front-end program to use with emerge, so that users can install programs as easily as it would be to install them from a more common distribution's software center. But this will come after I feel like this installer works decently for Funtoo.


While I'm not really a fan of the Gnome Desktop Environments since version 3, it seems to be the most stable to use with software made lately, at least in my experience. So this is what the installer is going to use for it's Desktop Environment. Once everything works well, I'll later look into including window managers, and other desktop environment options. 


Also; this is just for fun in my freetime. I have no idea when I'll have something ready that works.



# Current elementary OS Readme page (from March 5th, 2022, when I cloned the repo):
[![Translation status](https://l10n.elementary.io/widgets/installer/-/svg-badge.svg)](https://l10n.elementary.io/projects/installer/?utm_source=widget)

> Note: this is the installer for elementary OS 6 and newer. For the elementary OS 5.1 and older installer, see [Ubiquity](https://wiki.ubuntu.com/Ubiquity).

![Screenshot](data/screenshot-progress.png?raw=true)

An installer for open-source operating systems. See the [wiki](https://github.com/elementary/installer/wiki) for goals, design spec, user flow, and details about each step.

## Building, Testing, and Installation

You'll need the following dependencies:

 - meson
 - desktop-file-utils
 - gettext
 - gparted
 - libgnomekbd-dev
 - libgranite-dev >= 0.5
 - libgtk-3-dev
 - libgee-0.8-dev
 - libhandy-1-dev
 - libjson-glib-dev
 - libpwquality-dev
 - libxml2-dev
 - libxml2-utils
 - [distinst](https://github.com/pop-os/distinst/)
 - valac

Run `meson build` to configure the build environment. Change to the build directory and run `ninja test` to build and run automated tests.

    meson build --prefix=/usr
    cd build
    ninja test

To install, use `ninja install`, then execute with `io.elementary.installer`. Note that listing drives and actually installing requires root.

    sudo ninja install
    io.elementary.installer

You can also use `--test` mode for development to disable destructive behaviors like installing, restarting, and shutting down:

    io.elementary.installer --test

For debug messages, set the `G_MESSAGES_DEBUG` environment variable, e.g. to `all`:

    G_MESSAGES_DEBUG=all io.elementary.installer

