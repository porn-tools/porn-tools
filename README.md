# porn-tools
Tools for downloading porn

Currently contains a script to assist in automatically downloading cams from chaturbate.  I created this because https://github.com/ohhdemgirls/CaptureBate didn't seem to work well for me.  This is a simple bash script to do the same thing.

The script is named cb and takes several arguments. 
* **save** followed by a room name or URL will save a live room.  It will retry for some time if the room goes away, in case it returns shortly.
* **"add** followed by a room or URL will add it to the download list.
* **daemon** looks at your download list, and tries to download each one, latest first.  If the room is not up, it goes on to the next.  It will not try to capture more than a set number (3 by default) of streams at once so as not to consume all of your bandwidth.  After a stream ends, it reencodes the audio to fix the A/V sync, and then optionally archives the file.  All of the configuration is in variables in the first few lines of the script.

Both save and daemon will also optionally archive files to a remote location once finished.

Requirements:
* [rtmpdump](http://rtmpdump.mplayerhq.hu/) - needed for streamlink
* [streamlink](https://github.com/streamlink/streamlink).  ([livestreamer](https://github.com/chrippa/livestreamer) will also work, but seems to be abandoned.)

Optionally useful tools:
* [rclone](http://rclone.org) - archive to cloud storage

Other potentially useful tools for downloading video and pictures (some of these I haven't even tested):
* https://rg3.github.io/youtube-dl/
* https://github.com/soimort/you-get
* https://github.com/alexgisby/imgur-album-downloader
* https://github.com/NSFWYui/Reddit-porn-downloader
* https://github.com/fake-name/DanbooruScraper
* https://github.com/0x33e/porndl
* https://github.com/LuPoYi/porn77-downloader
* https://github.com/gil9red/DownloadByPornSite
* https://github.com/C0MPAQ/porngalleryget

