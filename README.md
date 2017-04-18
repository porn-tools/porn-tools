# porn-tools
Tools for downloading porn

Currently contains two scripts:
* **get**, a wrapper script to assist in downloading images/videos from various sites.
* **cb**, a script to assist in automatically downloading cams from chaturbate.  I created this because https://github.com/ohhdemgirls/CaptureBate didn't seem to work well for me.  This is a simple bash script to do the same thing.

**get** simply takes a list of URLs and tries to download the images/videos from them to the current directory.  It is a wrapper around several other commands:
* https://www.gnu.org/software/wget/
* https://rg3.github.io/youtube-dl/
* https://github.com/alexgisby/imgur-album-downloader

**cb** takes several arguments:
* **save** followed by a room name or URL will save a live room.  It will retry for some time if the room goes away, in case it returns shortly.
* **stalk** followed by a room name or URL will save a live room.  It will retry forever, until killed.
* **add** followed by a room or URL will add it to the download list.
* **remove** followed by a room or URL will remove it to the download list.
* **daemon** runs continually.  It looks at your download list, and tries to download each one, latest first.  If the room is not up, it goes on to the next.  It will not try to capture more than a set number (3 by default) of streams at once so as not to consume all of your bandwidth.  After a stream ends, it reencodes the audio to fix the A/V sync, and then optionally archives the file.  All of the configuration is in variables in the first few lines of the script.

cb will also optionally archive files to a remote location once finished.  Other configuration options are at the top of the script.

Requirements for cb:
* [rtmpdump](http://rtmpdump.mplayerhq.hu/) - needed for streamlink
* [streamlink](https://github.com/streamlink/streamlink). ([livestreamer](https://github.com/chrippa/livestreamer) will also work, but seems to be abandoned.)

Optionally useful tools for cb:
* [rclone](http://rclone.org) - archive to cloud storage

Other potentially useful tools for downloading video and pictures (some of these I haven't tested yet):
* https://github.com/soimort/you-get
* https://github.com/NSFWYui/Reddit-porn-downloader
* https://github.com/fake-name/DanbooruScraper
* https://github.com/0x33e/porndl
* https://github.com/LuPoYi/porn77-downloader
* https://github.com/gil9red/DownloadByPornSite
* https://github.com/C0MPAQ/porngalleryget
