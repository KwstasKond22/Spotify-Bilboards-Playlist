# Spotify-Bilboards-Playlist
Create  a playlist  by  scraping  the  bilboards 100 by   YYYY-MM-DD  
Setting up Spotify authentication:

The spotipy library is imported, and SpotifyOAuth is used for user authentication.
SPOTIPY_CLIENT_ID and SPOTIPY_CLIENT_SECRET are your Spotify application's credentials.
SpotifyOAuth is instantiated with necessary parameters like scope, redirect URI, client ID, client secret, etc. This authentication flow is designed for the user to authorize the application to access their Spotify data.
Getting the current user's ID:

sp.current_user()["id"] fetches the current user's unique Spotify ID after successful authentication.
Searching for songs:

song_names seems to be a list of song names, and date appears to be a string in the format "YYYY-MM-DD".
The code extracts the year from the date string.
It iterates through the song_names list and searches for each song on Spotify using the sp.search method.
For each song, it attempts to extract the Spotify URI (Uniform Resource Indicator) of the first search result in the form spotify:track:TRACK_ID. This URI uniquely identifies the song on Spotify.
Creating a playlist:

The code creates a new playlist using sp.user_playlist_create.
The playlist is named based on the date variable and is set as a private playlist (public=False).
Adding songs to the playlist:

Finally, it uses sp.playlist_add_items to add the songs (retrieved as URIs) to the newly created playlist.
The script essentially does the following:

Authenticates the application to access the user's Spotify account.
Retrieves the user's ID.
Searches for songs based on names and year.
Creates a new private playlist named after the provided date.
Adds the found songs to the newly created playlist.
Please note that the success of this script depends on various factors such as the accuracy of song names, availability on Spotify, and the user's authentication/authorization process.
