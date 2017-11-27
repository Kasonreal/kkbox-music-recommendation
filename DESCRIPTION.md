The 11th ACM International Conference on Web Search and Data Mining (WSDM 2018) is challenging you to build a better music recommendation system using a donated dataset from [KKBOX](https://www.kkbox.com/). WSDM (pronounced "wisdom") is one of the the premier conferences on web inspired research involving search and data mining. They're committed to publishing original, high quality papers and presentations, with an emphasis on practical but principled novel models.

Not many years ago, it was inconceivable that the same person would listen to the Beatles, Vivaldi, and Lady Gaga on their morning commute. But, the glory days of Radio DJs have passed, and musical gatekeepers have been replaced with personalizing algorithms and unlimited streaming services.

While the public’s now listening to all kinds of music, algorithms still struggle in key areas. Without enough historical data, how would an algorithm know if listeners will like a new song or a new artist? And, how would it know what songs to recommend brand new users?

[WSDM](https://www.kkbox.com/) has challenged the Kaggle ML community to help solve these problems and build a better music recommendation system. The dataset is from [KKBOX](https://www.kkbox.com/), Asia’s leading music streaming service, holding the world’s most comprehensive Asia-Pop music library with over 30 million tracks. They currently use a collaborative filtering based algorithm with matrix factorization and word embedding in their recommendation system but believe new techniques could lead to better results.

Winners will present their findings at the conference February 6-8, 2018 in Los Angeles, CA. For more information on the conference, click [here](http://www.wsdm-conference.org/2018/call-for-participants.html), and don't forget to check out the other KKBox/WSDM competition: [KKBox Music Churn Prediction Challenge](https://www.kaggle.com/c/kkbox-churn-prediction-challenge)



## Data Description

In this task, you will be asked to predict the chances of a user listening to a song repetitively after the first observable listening event within a time window was triggered. If there are recurring listening event(s) triggered within a month after the user’s very first observable listening event, its target is marked 1, and 0 otherwise in the training set. The same rule applies to the testing set.

KKBOX provides a training data set consists of information of the first observable listening event for each unique user-song pair within a specific time duration. Metadata of each unique user and song pair is also provided. The use of public data to increase the level of accuracy of your prediction is encouraged.

The train and the test data are selected from users listening history in a given time period. Note that this time period is chosen to be before the [WSDM-KKBox Churn Prediction](https://www.kaggle.com/c/kkbox-churn-prediction-challenge) time period. The train and test sets are split based on time, and the split of public/private are based on unique user/song pairs.

### Tables

#### train.csv

- msno: user id
- song_id: song id
- source_system_tab: the name of the tab where the event was triggered. System tabs are used to categorize KKBOX mobile apps functions. For example, tab `my library` contains functions to manipulate the local storage, and tab `search` contains functions relating to search.
- source_screen_name: name of the layout a user sees.
- source_type: an entry point a user first plays music on mobile apps. An entry point could be `album`, `online-playlist`, `song` .. etc.
- target: this is the target variable. `target=1` means there are recurring listening event(s) triggered within a month after the user’s very first observable listening event, `target=0` otherwise .

#### test.csv

- id: row id (will be used for submission)
- msno: user id
- song_id: song id
- source_system_tab: the name of the tab where the event was triggered. System tabs are used to categorize KKBOX mobile apps functions. For example, tab `my library` contains functions to manipulate the local storage, and tab `search` contains functions relating to search.
- source_screen_name: name of the layout a user sees.
- source_type: an entry point a user first plays music on mobile apps. An entry point could be `album`, `online-playlist`, `song` .. etc.

#### sample_submission.csv

sample submission file in the format that we expect you to submit

- id: same as `id` in `test.csv`
- target: this is the target variable. `target=1` means there are recurring listening event(s) triggered within a month after the user’s very first observable listening event, `target=0` otherwise .

#### songs.csv

The songs. Note that data is in unicode.

- song_id
- song_length: in ms
- genre_ids: genre category. Some songs have multiple genres and they are separated by `|`
- artist_name
- composer
- lyricist
- language

#### members.csv

user information.

- msno
- city
- bd: age. Note: this column has outlier values, please use your judgement.
- gender
- registered_via: registration method
- registration_init_time: format `%Y%m%d`
- expiration_date: format `%Y%m%d`

#### song_extra_info.csv

- song_id
- song name - the name of the song.
- isrc - [International Standard Recording Code](https://en.wikipedia.org/wiki/International_Standard_Recording_Code), theoretically can be used as an identity of a song. However, what worth to note is, ISRCs generated from providers have not been officially verified; therefore the information in ISRC, such as country code and reference year, can be misleading/incorrect. Multiple songs could share one ISRC since a single recording could be re-published several times.
