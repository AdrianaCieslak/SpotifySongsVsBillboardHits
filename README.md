# Analyzing Trends Between Top Spotify Songs and Billboard 100 Hits

### Project Description

As a team completed an ETL project to create a dataset that allows for analysis of Spotify song popularity compared to the Billboard Top 100 charts. The main focus was to analyze the artist, song and number of weeks on the Top 100 charts. Specific song atrributes were also included, such as danciness, liveliness and duration.

#### Step 1: Extract
The ETL project focused on two datasets. The Billboard data provides the foundational data while the Spotify data provides better details on the unique attributes of the song.
* Billboard Charts CSV
  - CSV file available on Kaggle
  - Contains the weekly updated HOT100 section in Billboards charts from 2015 to 2019
  - Available data: Song, Artist, Weeks On #1, Weeks On Chart, Peak Rank
* Top Spotify songs from 2010-2019 - BY YEAR
  - CSV file available on Kaggle
  - Contains Spotify’s most popular songs in the world by year . The dataset includes 13 variables to analyze different song attributes
  - Available data: title, artist, top genre, song, bpm, nrgy, dnce, dB, live, val, dur, acous, spch, pop

#### Step 2: Transform
There were multiple steps taken to clean and transform the data to prepare it for the load stage. The first stage was to remove all unnecessary data. The Billboard data covers 2015-2019 and the Spotify data covered 2010-2019. Since there was no Billboard data to correspond to the 2010-2014 Spotify data we removed it from the data set.
Next we took out the columns we were not going to be using for the analysis. From the Spotify
data, we kept the following columns:
   - title
   - artist
   - dnce (Danceability - The higher the value, the easier it is to dance to this song.)
   - live (Liveness - The higher the value, the more likely the song is a live recording)
   - dur (Length - The duration of the song.)
We then updated the remaining columns to either match the Billboard tables, or be easier to
understand:
   - title > song
   - dnce > dance
   - live > live_rec
   - dur > duration
From the Billboard list we kept the following columns:
   - Song
   - Artist
   - Weeks On #1
   - Weeks On Chart
We then updated the title to remove spaces and match the case of the Spotify data:
   - Song > song
   - Artist > artist
   - Weeks On #1 > weeks_1
   - Weeks On Chart > weeks_chart
