# Bookmarklets
JS bookmarklets (because they're cool)

## Avalaible bookmarklets
### Link viewer v1.2.2
Creates a picure-in-picture window for visiting links. (Not all will work)

Link:
`javascript:(function(l){    var s = document.createElement("script");     s.src = l;     document.body.append(s);})("https://cdn.jsdelivr.net/gh/ProgrammingParadox/bookmarklets@main/src/linkViewer.js");`

Note that if using a YouTube link, you'll need to edit it a little. https://www.youtube.com/watch?v=B3r4EgwLqMM turns into https://www.youtube.com/embed/B3r4EgwLqMM

### things that don't work
 - The minus button only hides the content. Working on making it shrink the height of the actual thing, too.
 - Sometimes it might be a little hard to resize the canvas :P
