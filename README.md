# porn-tools
Tools for downloading porn

Currently contains two scripts:
* **get**, a wrapper script to assist in downloading images/videos from various sites.
* **cb**, a script to assist in automatically downloading cams from chaturbate.  I created this because https://github.com/ohhdemgirls/CaptureBate didn't seem to work well for me.  This is a simple bash script to do the same thing.

**get** simply takes a list of URLs and tries to download the images/videos from them to the current directory.  It is a wrapper around several other commands:
* https://www.gnu.org/software/wget/
* https://rg3.github.io/youtube-dl/
* https://github.com/alexgisby/imgur-album-downloader
* https://github.com/althonos/instaLooter

**cb** takes several arguments:
* **save** followed by a room name or URL will save a live room.  It will retry for some time if the room goes away, in case it returns shortly.
* **stalk** followed by a room name or URL will save a live room.  It will retry forever, until killed.
* **add** followed by a room or URL will add it to the download list.
* **remove** followed by a room or URL will remove it to the download list.
* **archive** uploads a recording to remote storage. This will accept files with a local path, or files which have been automatically uploaded.  This allows you to have a separate incoming directory from the final storage place.
* **daemon** runs continually.  It has one option, **search**, which will search for cams matching cams from a chaturbate url.  Without this option, it looks at your download list, and tries to download each one, latest first.  If the room is not up, it goes on to the next.  It will not try to capture more than a set number (3 by default) of streams at once so as not to consume all of your bandwidth.  After a stream ends, it reencodes the audio to fix the A/V sync, and then optionally uploads the file to remote storage.  All of the configuration is in variables in the first few lines of the script.

cb will also optionally archive files to a remote location once finished.  Other configuration options are at the top of the script.

Requirements for cb:
* [rtmpdump](http://rtmpdump.mplayerhq.hu/) - needed for streamlink
* [streamlink](https://github.com/streamlink/streamlink). ([livestreamer](https://github.com/chrippa/livestreamer) will also work, but seems to be abandoned.)

Optionally useful tools for cb:
* [rclone](http://rclone.org) - archive to cloud storage

Other potentially useful tools for downloading video and pictures (some of these I haven't tested yet):
* https://github.com/4pr0n/ripme - great for downloading stuff from reddit, imgur, others
* https://github.com/soimort/you-get
* https://github.com/NSFWYui/Reddit-porn-downloader
* https://github.com/fake-name/DanbooruScraper
* https://github.com/0x33e/porndl
* https://github.com/LuPoYi/porn77-downloader
* https://github.com/gil9red/DownloadByPornSite
* https://github.com/C0MPAQ/porngalleryget
