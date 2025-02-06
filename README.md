# Music-Dashboard
Tags : ETL, API, Data visualization, Tableau, Data analysis

Time spent: 1 day and half

Important precision before starting : these are my first dashboards made with Tableau, I usually use PowerBI so I kept things pretty simple.

Content : https://public.tableau.com/views/MUSICDASHBOARD/MusicDashboard?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link
CONTEXT

As far as I can remember I have always listened some Rap. Even though i love this music, I felt that my playlist was drowned by it up to the point to become overwhelming. I decided to check this by diving into my Deezer personal data. Here is what I found! 
 

DATA GATHERING

First, I asked Deezer for my personal data. 3 days after I received my overall listening historic with: track name, artist name, Date, ISRC, listening time…
Problem is to properly analyse my consumption of rap, I was missing the genre associated with each track. 

To get this information, I used Spotify API to get the genre of each distinct track i listened and then map it with my listening historic. The code I used is availabale !

DATA CLEANING

The data given by Deezer was already cleaned. However, I had a problem: the important quantity of « Unknown genre ». After a closer look on it, I concluded 2 things: 
-	Unknown genre = House music: Most tracks registered as « Unknown genre » were actually House music. 
-	Music produced by small artists: maybe Spotify had not yet classified these emerging artists or maybe they were small enough so that when we look at their name in the app, another artist is retrieved first, and all the tracks are therefore unmatched according to the way i used the API to map genres. 

DATA TRANSFOMATION

-	Removing all tracks with a listening time < 30s to keep only the tracks I really listened according to the SNEP.
-	Kept only the first genre: Spotify’s API associated several genres to each track. To ease my classification, I kept only the first one which was often the most relevant.
-	Kept only the first artist: I decided to exclude featuring artists to ease the data interpretation. 

CONCLUSION

My feeling is now confirmed: for many years , rap wasp predominant in my playlist ( up to 88% in 2019). However,
-	 Its proportion has significantly decreased over time especially after 2022 corresponding to the year I ended my preparatory class synonym of opening to the world.
-	The subgenres of rap have also changed from mainstream rap to « nouvelle vague » an underground and emerging subgenre with a strong influence of tech music and a major place granted for lyrics.  

Now, how can be explained the predominancy of this genre? 
-	By rap itself: Rap was built as a contra culture in opposition to the societal norms so without positive references to other music or culture. It is often seen as a narrowing music, a closed universe. 
But i don’t think this is true at all. 
-	Music consumption model: I use a lot recommendation systems to listen music:  I choose a track and Deezer build a playlist with similar songs. This can lead to a certain inertia in what I listen by reducing discoverability of other genres.

