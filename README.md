# Atom PHP Debugging Package

Debug PHP code using the [Xdebug PHP Extension](http://xdebug.org/).

# Features
- Interactive Console
- Breakpoints
- Watches
- Multiple Debug Sessions
- Path Mappings
- Step through debugging (Over, In, Out)
- Stack and Context views
- UTF8 Support
- Uses atom-debug-ui

This is currently an alpha release, and still in active development.

![](https://raw.githubusercontent.com/gwomacks/php-debug/master/screenshot.gif)

# Getting Started

## Install Xdebug ##
You may already have Xdebug installed. Check the results of the [phpinfo function](http://php.net/manual/en/function.phpinfo.php) for xdebug information.
If no xdebug section exists, you likely need to install this. *nix users can likely find it within their package manager of choice.
Alternative installation or compiling instructions are available [here](http://xdebug.org/docs/install).

## Setting up Xdebug ##

```
xdebug.remote_enable=1
xdebug.remote_host=127.0.0.1
xdebug.remote_connect_back=1    # Not safe for production servers
xdebug.remote_port=9000
xdebug.remote_handler=dbgp
xdebug.remote_mode=req
xdebug.remote_autostart=true
```

With these settings, PHP will connect to your editor for every script it executes.
The alternative is to switch xdebug.remote_autostart to false, and install an Xdebug helper extension for your browser of choice, such as:
 - [The easiest Xdebug](https://addons.mozilla.org/en-US/firefox/addon/the-easiest-xdebug/) for Mozilla Firefox
 - [Xdebug Helper](https://chrome.google.com/webstore/detail/xdebug-helper/eadndfjplgieldjbigjakmdgkmoaaaoc) for Google Chrome

These browser extensions will give you a button within your browser to enable/disable Xdebug. The extensions might have configuration options for an "IDE key" (which is used for an XDEBUG_SESSION cookie). The IDE key for Atom with PHP Debug is "xdebug-atom".

It is also possible to run a php script from the command line with Xdebug enabled.
You can find more information on this at the Xdebug documentation for [Starting The Debugger](http://xdebug.org/docs/remote#starting).
See can find a complete list and explanation of Xdebug settings [here](http://xdebug.org/docs/all_settings).

## Start Debugging ##

To begin debugging:

1. Open up your PHP file in atom
2. Add a breakpoint:

  Move the cursor to a line you want to break on and set a breakpoint by pressing `Alt+F9`, selecting Toggle Breakpoint from the Command Palette (`ctrl+shift+p`)or with the php-debug menu (`Packages -> php-debug->Toggle Breakpoint`).
  This will highlight the line number green, to indicate the presence of a breakpoint.

3. Open the debug view by pressing `ctrl+alt+d`, selecting 'Toggle Debugging' from the Command Palette or php-debug menu.
4. Start the script with Xdebug enabled. If everything is setup correctly, the entire line of the breakpoint will be highlighted in green, indicating the current line of the script.

If everything worked correctly, you can now use the various buttons/commands to step through the script.

# Settings

### Server Port ###
This is the port that the atom client will listen on.
Defaults to 9000

### Server Address ###
This is the address that the atom client will listen on.
Defaults to 127.0.0.1

### Xdebug DBGP Protocol Debugging ###
Outputs protocol debugging messages to the atom debug console

### Xdebug: Max Depth ###
Max depth for variable scopes

### Xdebug: Max children ###
Maximum number of array elements to show in variables

### Xdebug: Max Data ###
Maximum data for variables

### Display: Sort Arrays/Object alphabetically ###
Sort Arrays/Object alphabetically instead of by php default

### Display: Status Bar ###
Allow PHP Debug to be opened from the status bar

### Exceptions ###
Default exceptions and errors for PHP-Debug to break on

### Path Maps ###
Pathmaps are now configured for each project folder during connection
