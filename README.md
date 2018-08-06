# SwagLyrics-For-Spotify 
![PyPI](https://img.shields.io/pypi/v/swaglyrics.svg)

Fetches the currently playing song from Spotify on Windows and displays the lyrics from Genius on cmd.

Probably wasn't thinking when I put _Swag_ in the name (Imagine if this project ends on my CV) but 
I'm mainly trying to build this project as far as I can, mainly for practice and to learn stuff.

## Installation
```
pip install swaglyrics
```
Make sure to use a version >= 0.1.6 since the previous ones don't have the 'tab' option supported.

## Usage
`swaglyrics [-h] [-t] [-c]`

Either the tab or cli argument is required to output lyrics.

Arguments:
```
  -h, --help  show this help message and exit
  -t, --tab   Display lyrics in a browser tab.
  -c, --cli   Display lyrics in the command-line.
```

## Package Structure
```
.
|-- swaglyrics
    |-- static  # styling and the AJAX script needed to dynamically refrsh browser tab with new lyrics
    |-- templates  # template for the browser tab
    |-- __init__.py
    |-- __main__.py  # holds primary function that parses args and executes accordingly
    |-- cli.py  # defines functions to fetch lyrics from Genius
    |-- spotify.py  # defines functions to get currently playing song and artist from the Spotify app
    |-- tab.py  # Flask app to display lyrics in a browser tab
    |-- tests.py    # need overhauling
    |-- unsupported.txt  # to log unsupported songs, will be updated soon
|-- LICENSE.md
|-- MANIFEST.in
|-- README.md
|-- setup.py
```

## Improvements Planned
1. MacOS support
2. Better logging of unsupported songs, the isolated unsupported.txt is sub-optimal for multiple users since the
file will only update locally with songs which worked fine when it was just me but since I hope others use it too, I'll
try to add a better method with server support.
3. Better tests to test all of the functionality.
4. Perhaps a tiny app that could fit in your tray to be opened whenever you want lyrics for a song.
5. Supporting more songs, currently the program sometimes fails at remixes since while the lyrics are same as original,
 the artist is the remixer.
6. Documenting all the files.



