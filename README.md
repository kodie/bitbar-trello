# BitBar Trello Plugin [![Build Status](https://travis-ci.org/kodie/bitbar-trello.svg?branch=master)](https://travis-ci.org/kodie/bitbar-trello)
A plugin for [BitBar](https://github.com/matryer/bitbar) that shows your unread [Trello](https://trello.com) notification count with a drop-down list of clickable recent notifications.

## Requirements
* [jq](https://github.com/stedolan/jq)

## Setup
1. Install BitBar Trello Plugin: ```bitbar://openPlugin?title=Trello%20Notifications&src=https://raw.githubusercontent.com/kodie/bitbar-trello/master/trello.15m.sh```
2. After the plugin is installed, it will automatically create the config file `~/.bitbar_trello`. You will need to fill out the `apiKey` and `apiToken` variables which we will be doing in the following steps.
3. Go to https://trello.com/app-key
4. The text under `Key:` is your API Key. Put it in the `apiKey` variable in your config file.
5. On that same page, click on the `Token` link.
6. You should be asked to "Let Server Token use your account?". Click the `Allow` button.
7. Your API Token should then be displayed. Put it in the `apiToken` variable in your config file.
8. Refresh BitBar Trello Plugin: ```bitbar://refreshPlugin?name=trello.*?.sh```

and that's it!

## Configurable Variables
When you first install the BitBar Trello Plugin, it will automatically create the config file `~/.bitbar_trello`. This file is where you put your API Key and Token, however there are additional variables that you can set in there to change the way the plugin looks and functions.

* `apiKey` - Your Trello API Key
	* Default: `""`
	* Example: `apiKey="c9ff119073ea2567730fb42e3a4fe805"`
	* **Required**

* `apiToken` - Your Trello API Token
	* Default: `""`
	* Example: `apiToken="gpD9HsYz2nJKaWz4Blr6JeVpv9Rct0PzeiwJyj9rwGZutmoSwDM5Hxl0x03ORGcT"`
	* **Required**

* `limit` - Number of recent notifications to display in the dropdown
	* Default: `"20"`
	* Example: `limit="50"`
	* Can be any number from 1 to 1000

* `readColor` - Read notification color
	* Default: `""`
	* Example 1: `readColor="red"`
	* Example 2: `readColor="#ff0000"`
	* Setting to blank will use the system default
	* Color names or HEX values can be used

* `readFont` - Read notification font
	* Default: `""`
	* Example: `readFont="Georgia"`
	* Setting to blank will use the system default

* `readSize` - Read notification font size
	* Default: `"15"`
	* Example: `readSize="12"`
	* Setting to blank will use the system default

* `unreadColor` - Unread notification color
	* Default: `"blue"`
	* Example 1: `unreadColor="orange"`
	* Example 2: `unreadColor="#ffa500"`
	* Setting to blank will use the system default
	* Color names or HEX values can be used

* `unreadFont` - Unread notification font
	* Default: `""`
	* Example: `unreadFont="Georgia-Bold"`
	* Setting to blank will use the system default

* `unreadSize` - Unread notification font size
	* Default: `"15"`
	* Example: `unreadSize="20"`
	* Setting to blank will use the system default

* `truncLength` - Number of characters before the notification text is truncated
	* Default: `"70"`
	* Example: `truncLength="30"`
	* Setting to blank will disable truncating

* `truncSuffix` - Text to use after truncating
	* Default: `"..."`
	* Example: `truncSuffix="..."`

* `useIcons` - Whether emoji icons should be displayed next to notifications or not
	* Default: `"1"`
	* Example: `useIcons="0"`
	* 0=no, 1=yes

* `unreadDisplay` - Unread display mode
	* Default: `"1"`
	* Example: `unreadDisplay="3"`
	* 0=none, 1=beside icon/title, 2=rotated with icon/title, 3=in dropdown

* `unreadEcho` - Unread count text
	* Default: `"(%unread%)"`
	* Example: `unreadEcho="Unread: %unread%"`
	* `%unread%` will be replaced with unread count number

* `title` - Text to be displayed on system bar
	* Default: `""`
	* Example: `title="Trello"`
	* Can be set to blank to display icon only.
	* If both `title` and `icon` are set to blank, `title` will automatically be set to "Trello.

* `icon` - Base64 icon to use in system bar
	* Default: (The Trello logo in Base64)
	* Example: `icon=""`
	* Can be set to blank to disable icon

* `nIcon_$notificationType` - Emoji Icon to display next to the notification
	* Default: (Depends on `$notificationType`)
	* Example: `nIcon_cardDueSoon="🕓"`

* `nText_$notificationType` - Text to be displayed for notification
	* Default: (Depends on `$notificationType`)
	* Example: `nText_addedToCard="%name% added you to the card %card%"`
	* `%name%` will be replaced with the person's name
	* `%card%` will be replaced with the card name
	* `%board%` will be replaced with the board name
	* `%organization%` will be replaced with the organization name

## License
MIT. See the License file for more info.
