The guys who make one of my favorite applications, [TextExpander](http://www.smileonmymac.com/TextExpander/), posted a great [tip](http://smileonmymac.net/blog/2008/10/20/get-trim-with-textexpander/) a while back to automatically shorten urls that are on the clipboard with the [tr.im](http://tr.im/) service.

It works wonderfully, except there is no way to track how many people click your shortened urls because you're not logged into your tr.im account when the urls are shortened. There is a crazy easy way to log in to your tr.im account when TextExpander shortens your urls.

* Add this line as a new TextEpxander snippet and set it as an Applescript. Fill in your username and password where it says `username:password`.

    do shell script "curl --basic -u username:password http://tr.im/api/trim_url.xml?url=`pbpaste` | tr '>' '\n' | tr '<' '\n' | grep -m 1 -A 1 url | tail -1"

* You can also simply download this TextExpander [snippet](http://tricky.nu/7891) to add to TextExpander. You still must put your username and password where it says `username:password`. :)

* Set the shortcut to something like "trm" or similar. 

Thats it! Anytime you want to shorten a url in any application, copy the url to the clipboard. Next go to where you'd like to paste the url. Type in "trm" or your shortcut, and it will paste the shortened url automatically. 