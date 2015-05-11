## Description ##
This project is what has commonly been referred to as "SingleMalt's DLL" on the winholdem.net forums.  It is an add-on library to the WinHoldem product (found at http://winholdem.net), and exposes a number of new WH-script symbols to the parent application.

It can also be used as a static library to which one's existing whuser.dll code could be linked (so-called DLL chaining), thus exposing the functions to your own whuser.dll code via standard WINAPI calls.

As a summary, the following new capabilities are exposed:
  * 82 PokerTracker symbols
  * 15 PokerTracker "aggregation" symbols
  * History for 133 WinHoldem symbols
  * 5 "action history" symbols
  * 7 "table stats history" symbols
  * 9 "action" symbols
  * 6 "My Hand" symbols
  * short circuiting symbol
  * "memory" symbols for user variables
  * built in WSEX Hand History converter - puts real names back in WSEX HH's
  * all capabilities are exposed as WinHoldem script symbols (i.e. dll$symbol), and are also exported from the DLL, to use within your own DLL
  * configuration for PokerTracker, WSEX HH, and History and Debug levels is all done via the WinHoldem GUI.  No .ini, .txt, or .parms files are needed.  Modern technology! (a new menu item "Extras" has been added to the WinHoldem menu)

Notes:
  1. To expose capabilities to your own "whuser.dll", simply:
    * rename whuser.dll to extras.dll
    * include extras.lib in your compiler settings
    * #include "extras.h" in your code
    * call LoadLibrary for extras.dll in your code (see template)
    * use exported functions
  1. DLL **must** be named either "whuser.dll" or "extras.dll".
  1. PokerTracker symbols are only valid for PostgreSQL databases. Microsoft Access databases for PokerTracker are not supported.
  1. Most symbols require a live table or a connection to ppro, and do not work properly in manual mode.

## License ##
GPL v3