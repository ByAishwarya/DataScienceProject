# Spotify Tracks Dataset

## Dataset Overview
This dataset contains track information and audio features from Spotify. Each row represents a single track with its metadata and audio characteristics.

## Data Dictionary

| Column Name | Data Type | Description | Range/Values |
|-------------|-----------|-------------|--------------|
| **track_id** | `string` | The Spotify ID for the track | Unique identifier |
| **artists** | `string` | The artists' names who performed the track | Artist names separated by `;` |
| **album_name** | `string` | The album name in which the track appears | |
| **track_name** | `string` | Name of the track | |
| **popularity** | `integer` | The popularity of a track | `0-100`<br>100 = most popular |
| **duration_ms** | `integer` | The track length in milliseconds | |
| **explicit** | `boolean` | Whether the track has explicit lyrics | `true` = explicit<br>`false` = not explicit/unknown |
| **danceability** | `float` | How suitable a track is for dancing | `0.0-1.0`<br>1.0 = most danceable |
| **energy** | `float` | Perceptual measure of intensity and activity | `0.0-1.0`<br>1.0 = high energy |
| **key** | `integer` | The key the track is in using Pitch Class notation | `-1 to 11`<br>`0` = C, `1` = C♯/D♭<br>`-1` = no key detected |
| **loudness** | `float` | Overall loudness in decibels (dB) | Typically `-60 to 0` dB |
| **mode** | `integer` | Modality (major or minor) | `1` = major<br>`0` = minor |
| **speechiness** | `float` | Presence of spoken words in a track | `0.0-1.0`<br>> `0.66`: speech-only<br>`0.33-0.66`: mixed<br>< `0.33`: music |
| **acousticness** | `float` | Confidence measure of whether track is acoustic | `0.0-1.0`<br>1.0 = high confidence acoustic |
| **instrumentalness** | `float` | Predicts whether track contains no vocals | `0.0-1.0`<br>1.0 = no vocal content |
| **liveness** | `float` | Presence of audience in recording | `0.0-1.0`<br>> `0.8`: likely live |
| **valence** | `float` | Musical positiveness conveyed by track | `0.0-1.0`<br>High = positive/happy<br>Low = negative/sad |
| **tempo** | `float` | Overall estimated tempo in BPM | |
| **time_signature** | `integer` | Estimated time signature | `3-7`<br>3 = 3/4, 4 = 4/4, etc. |
| **track_genre** | `string` | The genre in which the track belongs | |

## Detailed Column Descriptions

### Audio Features (Technical)

**danceability**
- Combines: tempo, rhythm stability, beat strength, overall regularity
- `0.0`: least danceable
- `1.0`: most danceable

**energy**
- Represents intensity and activity
- Example: Death metal = high energy, Bach prelude = low energy

**key**
- Standard Pitch Class notation mapping:
  - `0` = C
  - `1` = C♯/D♭
  - `2` = D
  - `3` = D♯/E♭
  - `4` = E
  - `5` = F
  - `6` = F♯/G♭
  - `7` = G
  - `8` = G♯/A♭
  - `9` = A
  - `10` = A♯/B♭
  - `11` = B
  - `-1` = No key detected

**loudness**
- Measured in decibels (dB)
- Typical range: `-60` to `0` dB
- Values are averaged across entire track

**speechiness**
- `> 0.66`: Tracks made entirely of spoken words (talk shows, audiobooks)
- `0.33-0.66`: Tracks with both music and speech (rap music)
- `< 0.33`: Music and non-speech tracks

**instrumentalness**
- Predicts absence of vocals
- "Ooh" and "aah" sounds treated as instrumental
- `1.0`: High confidence track has no vocal content

**liveness**
- `> 0.8`: Strong likelihood track was performed live
- Lower values indicate studio recording

**valence**
- Musical positiveness
- High valence: Happy, cheerful, euphoric
- Low valence: Sad, depressed, angry

**tempo**
- Beats per minute (BPM)
- Speed/pace of the track

### Metadata

**popularity**
- Algorithmically calculated based on:
  - Total number of plays
  - Recency of plays
  - Duplicate tracks rated independently
- Artist/album popularity derived from track popularity

**time_signature**
- Number of beats in each measure:
  - `3` = 3/4 time
  - `4` = 4/4 time (most common)
  - `5` = 5/4 time
  - `6` = 6/4 time
  - `7` = 7/4 time

## Notes

- Missing values are represented as `null` or `NA`
- Artist names are separated by semicolons (`;`) for collaborations
- Track popularity is calculated independently for different releases (single vs album versions)
- Audio features are provided by Spotify's API and are algorithmically generated

## Source
Data sourced from Spotify Web API. Audio features are calculated by Spotify's internal algorithms.
You can download the dataset from: [Kaggle Spotify Tracks Dataset](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset) 
