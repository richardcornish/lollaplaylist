# Lollaplaylist

[![Screenshot](https://raw.githubusercontent.com/richardcornish/lollaplaylist/master/docs/screenshot.png)](https://www.youtube.com/playlist?list=PLfFIa4m9ZTA1y0hHkU_U7Y6twjyuiiIyI)

This repository contains the code to create a YouTube playlist containing the most popular video of each of the artists of the [Lollapalooza](https://www.lollapalooza.com/) 2017 lineup.

I made this because I feel old and disconnected from today's youth what with their loud music and what not. Also, I'm lazy and sure as hell wasn't going to manually search for every band's popular song on YouTube.

If you're lazier than I am, just go to the [Lollapalooza 2017 playlist](https://www.youtube.com/playlist?list=PLfFIa4m9ZTA1y0hHkU_U7Y6twjyuiiIyI) that I made.

## How did you make this?

First I created a [JSON file](https://raw.githubusercontent.com/richardcornish/lollaplaylist/master/lollaplaylist/lineup.json) of the lineup from the [Wikipedia page](https://en.wikipedia.org/wiki/List_of_Lollapalooza_lineups_by_year#Lollapalooza_7) because one didn't exist.

Then I spent a lot of time in the [Google Developers Console](https://console.developers.google.com/), registering an app, setting a callback of `http://localhost:8080/`, and downloading the `client_secrets.json` file.

Next I stumbled around in the [YouTube Data API documentation](https://developers.google.com/youtube/v3/getting-started) in a haze until I figured out I had to install the [Google API Client Library for Python](https://pypi.python.org/pypi/google-api-python-client) along with some decent [Python sample code](https://github.com/youtube/api-samples/blob/master/python/playlist_updates.py) on GitHub. After that it was simply a matter of [creating a new playlist](https://developers.google.com/youtube/v3/docs/playlists/insert), [searching for the videos of each artist](https://developers.google.com/youtube/v3/docs/search/list), and then [adding the video to the playlist](https://developers.google.com/youtube/v3/docs/playlistItems/insert).

## I want to do this on my own

Remember to register an app in the [Google Developers Console](https://console.developers.google.com/) as mentioned above.

```
mkvirtualenv lollaplaylist
git clone git@github.com:richardcornish/lollaplaylist.git
cd lollaplaylist/
pip install -r requirements.txt
cd lollaplaylist/
python youtube
```