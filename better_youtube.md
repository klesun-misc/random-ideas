As you all know, youtube sucks.

https://support.google.com/youtube/answer/6054623?hl=en

Copyrighted content removal grows, useful features shrink. Recommendations are also garbage.

_Better Youtube™_ would be a wrapper around youtube (like niconico once was), either as an extension, or as a separate web site, that would add all the good
stuff youtube lacks and remove all the the bad stuff youtube forces on you.

### Good Stuff Youtube Lacks
- Contributed captions.
- Playlists of 200+ videos (not sure, maybe this is possible nowadays)
- Filter to limit recommendations to only music

### Bad Stuff Youtube Forces
- Recommended damn popular meme videos even if you mark them as "Not Interested -> I don't like the video" nonstop.
It also bases recommentation on a video you watched, even if you "dislike"d it
- Stupid comments, new ones prioritized over good ones, no way to get them in strict chronological order either.
- Filter out videos by category. Like remove "today we are going to build a chair" kind of vidoes, "top 10 x" kind of videos, videos that are shorter than one minute, etc...
- When I hide videos I obviously won't like with a userscript based on title and duration, js main thread freezes, can only guess youtube runs some really heavy code when it tries to load more entries ([sync http requests](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Synchronous_and_Asynchronous_Requests#synchronous_request) perhaps? =-D). So now I'm seriously considering making a separate web page that would crawl youtube and just show this same content, but with a better User Experience, without freezes.

Basically, let user adjust the content he sees to his preferences, not adjust his preferences to the content.

_____________________________________

Upd.: apparently, better youtube already exists, it's called LBRY. Better focus on improving it than on fixing youtube: https://github.com/klesun-misc/random-ideas/blob/master/lbry_search_rust.md
