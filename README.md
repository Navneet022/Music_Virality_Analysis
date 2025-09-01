# Music_Virality_Analysis

Few days back i was listening to music and while looking for a good song browsing spotify a thought came into my mind,. How are thes songs rated who and what decides this song is a hit. I mean what makes a hit song? Is there a pattern in there or am not?

Dataset :
For the analysis I needed a dataset so I went searching after looking at many dataset that did not full fil my curiosity or weren't comprehensive to solve the answers I was looking for ,I fianlly founf a spotify data set. It has approx 21K records and most of it is that it contains the audio features I was looking for. So i got to work.

Hypothesis:
After looking at the data I have few question or hypothesis I want to clarify:
- These are the factors that I want to evaluate and see whether they have any corelation with a song being a hit or not:
  a. Having a license?
  b. Duration of the song?
  c. Streaming services?
  d. Does having a video or not have an affect?
  e. Does any specific audio feature like dancebility, energy, liveness, tempo etc have an effect?

What do i mean by a hit song?
Just saying "hit song" is too vague, so let's give a definition to it. Either A song which is among top 20% of the engagement ratio or among top 20% of streams is considered a hit song for this analysis. Similarly the botton 20% of either of these is considered a flop.

Analysis steps:

1. EDA : I performed exploratory data analaysis and foudn out how many nulls where there along with will they affect the analysis or not. I found that none of the missing values or nulls affect the analysis and choose not to remove them as it is still early and i don't want to get stuck later on , if they hinder i can remove them later.
- Few Findings :
  a. The streams which have nulls r zero values are all played on Youtube (likely due to wrong data collection or soemthing else will have to look deeper to undertsand this)
  b. Some songs even though they have a video still have 0 views, like or comments and same is for the songs without any videos. This proves that video has no correlation to "hit " factor.
  c. Songs which have licence definetly have video but vice-versa is not true.

2. SQL :(Analysis and Customer segementation)
   a. Calculated the engagement ratio then found the top and bottom 20% of the enagagement ratio and streams.
   b. Then went to segment the data into four categories :-

    i) WHEN stream_percentile <= 0.2 AND engagement_percentile <= 0.2 THEN 'Hit'
      ->Top 20% streams (popular songs by listens).
       Top 20% engagement (people replay, like, share, etc.).
       ✅These are your true hits → both popular and highly engaging.

    ii) WHEN stream_percentile <= 0.2 AND engagement_percentile >= 0.8 THEN 'Shallow (Hype but low engagement)'
      ->Top 20% streams (people listened a lot).
        Bottom 20% engagement (but didn’t actually engage).
       🚨 These are hype tracks – high streams, but people don’t stick with them.

   iii) WHEN stream_percentile >= 0.8 AND engagement_percentile <= 0.2 THEN 'Hidden Gem'
      ->Bottom 20% streams (not many listens).
        Top 20% engagement (but those who did listen, loved it).
       🌟 These are hidden gems – not mainstream, but with strong fan connection.

   iv) WHEN stream_percentile >= 0.8 AND engagement_percentile >= 0.8 THEN 'Flop'
      -> Bottom 20% streams (not popular).
         Bottom 20% engagement (and even those who listen don’t care).
        ❌ These are flops.

   v) ELSE 'Normal / Mid'
     -> Everything else that doesn’t fit the extremes.
        Just average or in-between songs.

   c. Aggregate Summary:
    i) Total stream per song/ artist
    ii) Avg stream per song/artist

   d. Ranking top N:
     i) Top 10 songs
     ii) Top 10 artist

   e. License, video, and Platform affect
   g. Duration bucket:
    i) Short:- Duration <3 mins
   ii) Medium: Duration between 3-5 mins
  iii) Long: Duration >5mins

3. Python Analysis:
   a. Feature correlation with streams
   <img width="1004" height="594" alt="image" src="https://github.com/user-attachments/assets/643ca283-3ee2-414b-9a94-238627133af6" />

   b. Feature correlation with engagement_ratio
   <img width="1010" height="602" alt="image" src="https://github.com/user-attachments/assets/85d1b862-faff-432b-9027-0ba14b99ef18" />

       
