# Week 5 breakout

Download the music database [here](https://drive.google.com/file/d/1IhKAQYmMxcUUig1cy2vrOn1_R9mx1tZy/view?usp=sharing). Open it in DB Browser and  try the following queries. The section below is a short recap on JOIN queries.

1. List all tracks in the 'Rock' genre
2. Select all tracks in the playlist named 'Classical 101 - The Basics'
3. List all playlists with the number of tracks in them
4. List all albums by the artist 'Led Zeppelin'
5. List all tracks by the artist 'Queen' (bonus for making them unique)

## JOIN queries

Multiple tables can be joined together by specifying the fields to join them on. This query joins the *tracks* and *genres* table, specifying the *GenreId* field that exists on both tables.
```
SELECT t.name, g.name
FROM tracks t
JOIN genres g ON t.GenreId = g.GenreId
```
You can specify multiple JOINs to join many tables together in this same way.