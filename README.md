![Youtube](https://user-images.githubusercontent.com/103464869/198981301-f6403dad-6e67-4480-b7fb-62cce7a11906.png)

# YouTube_Trending_Analytics

This repo contains a full analysis of YouTube's trending videos dataset to provide insights for Content Creators on YouTube and advertisers to make the most of their resources

The insights from this project were presented inside MicroStrategy Workstation. For quick access, a summary of insights & screen shoots is available in this [**Slide Deck**](https://docs.google.com/presentation/d/1cj8jm1yx0AFdngpc1KHVYFfgpCTPsh0aUDGlOP8rPEc/edit?usp=sharing) 

## 1. Objectives
One of main objectives of this project was to support YouTubers and Sponsers to pressing questions. 
### For YouTubers, Questions like: 
1. What is the best time to publish a video on YouTube?
2. What is the most promising categories to create content for?  
3. Is there specific tags and keywords that might increase your views?

### For Sponsers, Questions like: 
1. What is the best channels to sponser on YouTube?
2. What is the most promising categories to sponser?  
3. What videos stay longest in trending?

The product of this analysis is a `Custom Dashboard` for YouTubers and Sponsers to allow them to feed the latest data to the system and be able to make optimal decisions.

## 2. Data Sources

The data analysed in this project are public data from [Kaggle](https://www.kaggle.com/datasets/rsrishav/youtube-trending-video-dataset), based on the work of [_RISHAV SHARMA_](https://www.kaggle.com/rsrishav) who is kindly using YouTube API to retrieve this data daily. 

### **Sample Data** 

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>video_id</th>
      <th>title</th>
      <th>publishedAt</th>
      <th>channelId</th>
      <th>channelTitle</th>
      <th>categoryId</th>
      <th>trending_date</th>
      <th>tags</th>
      <th>view_count</th>
      <th>likes</th>
      <th>dislikes</th>
      <th>comment_count</th>
      <th>thumbnail_link</th>
      <th>comments_disabled</th>
      <th>ratings_disabled</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>s9FH4rDMvds</td>
      <td>LEVEI UM FORA? FINGI ESTAR APAIXONADO POR ELA!</td>
      <td>2020-08-11T22:21:49Z</td>
      <td>UCGfBwrCoi9ZJjKiUK8MmJNw</td>
      <td>Pietro Guedes</td>
      <td>22</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>pietro|guedes|ingrid|ohara|pingrid|vlog|amigos...</td>
      <td>263835</td>
      <td>85095</td>
      <td>487</td>
      <td>4500</td>
      <td>https://i.ytimg.com/vi/s9FH4rDMvds/default.jpg</td>
      <td>False</td>
      <td>False</td>
      <td>Salve rapaziada, neste vídeo me declarei pra e...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>jbGRowa5tIk</td>
      <td>ITZY “Not Shy” M/V TEASER</td>
      <td>2020-08-11T15:00:13Z</td>
      <td>UCaO6TYtlC8U5ttz62hTrZgg</td>
      <td>JYP Entertainment</td>
      <td>10</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>JYP Entertainment|JYP|ITZY|있지|ITZY Video|ITZY ...</td>
      <td>6000070</td>
      <td>714310</td>
      <td>15176</td>
      <td>31040</td>
      <td>https://i.ytimg.com/vi/jbGRowa5tIk/default.jpg</td>
      <td>False</td>
      <td>False</td>
      <td>ITZY Not Shy M/V[ITZY Official] https://www.yo...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3EfkCrXKZNs</td>
      <td>Oh Juliana PARÓDIA - MC Niack</td>
      <td>2020-08-10T14:59:00Z</td>
      <td>UCoXZmVma073v5G1cW82UKkA</td>
      <td>As Irmãs Mota</td>
      <td>22</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>OH JULIANA PARÓDIA|MC Niack PARÓDIA|PARÓDIAS|A...</td>
      <td>2296748</td>
      <td>39761</td>
      <td>5484</td>
      <td>0</td>
      <td>https://i.ytimg.com/vi/3EfkCrXKZNs/default.jpg</td>
      <td>True</td>
      <td>False</td>
      <td>Se inscrevam meus amores! 📬 Quer nos mandar al...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>gBjox7vn3-g</td>
      <td>Contos de Runeterra: Targon | A Estrada Tortuosa</td>
      <td>2020-08-11T15:00:09Z</td>
      <td>UC6Xqz2pm50gDCORYztqhDpg</td>
      <td>League of Legends BR</td>
      <td>20</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>Riot|Riot Games|League of Legends|lol|trailer|...</td>
      <td>300510</td>
      <td>46222</td>
      <td>242</td>
      <td>2748</td>
      <td>https://i.ytimg.com/vi/gBjox7vn3-g/default.jpg</td>
      <td>False</td>
      <td>False</td>
      <td>Você se unirá aos Lunari e aos Solari em Targo...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>npoUGx7UW7o</td>
      <td>Entrevista com Thammy Miranda | The Noite (10/...</td>
      <td>2020-08-11T20:04:02Z</td>
      <td>UCEWOoncsrmirqnFqxer9lmA</td>
      <td>The Noite com Danilo Gentili</td>
      <td>23</td>
      <td>2020-08-12T00:00:00Z</td>
      <td>The Noite|The Noite com Danilo Gentili|Danilo ...</td>
      <td>327235</td>
      <td>22059</td>
      <td>3972</td>
      <td>2751</td>
      <td>https://i.ytimg.com/vi/npoUGx7UW7o/default.jpg</td>
      <td>False</td>
      <td>False</td>
      <td>Danilo Gentili recebe Thammy Miranda. Após pas...</td>
    </tr>
  </tbody>
</table>
</div>


## 3. Analysis

