> Get the source of currently playing video element in a browser.

## Usage
 1. Save the [bookmarklet](../../raw/master/bookmarklet.txt) source as a bookmark in your browser
   ```
   javascript:(function()%7Bfunction%20f(e)%7Btry%7Bvar%20r%3De.document.getElementsByTagName(%22video%22)%3Bfor(var%20i%20in%20r)if(r%5Bi%5D.readyState%3E0%26%26!r%5Bi%5D.paused)return%20prompt(%22Copy%20video%20source%20URL%3A%22%2Cr%5Bi%5D.currentSrc)%2C!1%7Dcatch(t)%7B%7Dreturn!0%7Dif(f(window))%7Bfor(var%20c%3D0%3Bc%3Cwindow.frames.length%26%26f(window.frames%5Bc%5D)%3B)c%2B%2B%3Bif(c%3E%3Dwindow.frames.length)%7Bvar%20i%3Dwindow.document.querySelector(%22iframe%5Ballowfullscreen%5D%22)%2Ct%3D%22Can't%20detect%20currently%20playing%20video.%22%3Bi%26%26i.src%26%26window.location.href!%3Di.src%3Fconfirm(t%2B%22%20Retry%20inside%20iframe%3F%22)%26%26(window.location.href%3Di.src)%3Aalert(t)%7D%7D%7D)()
   ```
 2. Open a page and start a video / stream, then wait until it starts playing
 3. Hit the bookmark previously created, and copy the source URL

If the playing video can't be found, but an iframe used for videos is available, you can redirect to it's source and try again.
