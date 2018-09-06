## Project Ceruleus


![Imgur](https://i.imgur.com/0m2ew3A.png)

Ceruleus is my experiments with Jermolene's Tiddlywiki. It is never recommended for use by a third person. It is intended as a learning experience and has no backward compatibility with earlier editions of TW5.

This is the list of changes I have made to this project compared to the TW 5.15 master branch.

- Added **modalClass** param object for *tm-modal* message which sets the root class of modal.
- Added scripts area for loading external scripts with "$:/tags/Script".
- Changed "tiddlywiki.info" to "init.json" for easier manipulation by external editors and programs
- Added the following configuration options to "tiddlywiki.info"
	- **wikiTiddlersSubDir** : This string configures the default directory tiddlywiki reads and writes.
	- **includeDirs**: This array configuration is similar to "includewikis" -  without the necessity that folder has to have a "tiddlywiki.info" associated with it.
		- So far, the "read-only" option of "includewikis" have not been replicated.


Example init.json

```javascript
{
    "wikiTiddlersSubDir": "./contents",
    "includeDirs": ["./templates", "./functions"],
    "plugins": [
        "tiddlywiki/tiddlyweb",
        "tiddlywiki/filesystem",
        "tiddlywiki/highlight"
    ],
    "themes": [
        "tiddlywiki/vanilla",
        "tiddlywiki/snowwhite"
    ],
    "build": {
        "index": [
            "--rendertiddler",
            "$:/plugins/tiddlywiki/tiddlyweb/save/offline",
            "index.html",
            "text/plain"
        ]
    }
}

```


- In [tiddlywiki.files](https://tiddlywiki.com/#tiddlywiki.files%20Files "TiddlyWiki.com"), the directories object now scans the paths recursively.



Changed Files

1. boot/boot.js -  Look for comment //CHANGE
1. core/modules/commands/init.js. - Look for comment //CHANGE
1. core/modules/commands/server.js. - Look for comment //CHANGE
1. core/templates/tiddlywiki5.html.tid - Added area for $:/tags/Scripts - Look for comment //CHANGE
1. core/modules/startup/rootwidget.js - Added modalclass - Look for //CHANGE
1. core/modules/utils/dom/modal.js - Added modal class - Look for //CHANGE