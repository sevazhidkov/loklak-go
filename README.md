# Loklak Go
Simple Go wrapper for Loklak API. Currently not all functions implemented.
## Usage
```go
package main

import (
  "fmt"
  "github.com/sevazhidkov/loklak-go"
)

func main() {
  // All functions contain in 'loklak' package

  // Search function
  response, err := loklak.Search("@sevazhidkov")
  if err != nil {
    fmt.Println(err)
  } else {
    fmt.Println(response.Statuses)
  }
}
```
All json fields in loklak response is supported.
Example declaration of response struct:
```go
type SearchResponse struct {
	Readme0 string `json:"readme_0"`
	Readme1 string `json:"readme_1"`
	Readme2 string `json:"readme_2"`
	Readme3 string `json:"readme_3"`
	SearchMetadata struct {
		Itemsperpage string `json:"itemsPerPage"`
		Count string `json:"count"`
		CountTwitterAll int `json:"count_twitter_all"`
		CountTwitterNew int `json:"count_twitter_new"`
		CountBackend int `json:"count_backend"`
		CountCache int `json:"count_cache"`
		Hits int `json:"hits"`
		Period int `json:"period"`
		Query string `json:"query"`
		Client string `json:"client"`
		Time int `json:"time"`
		Servicereduction string `json:"servicereduction"`
		Scraperinfo string `json:"scraperInfo"`
	} `json:"search_metadata"`
	Statuses []struct {
		CreatedAt time.Time `json:"created_at"`
		ScreenName string `json:"screen_name"`
		Text string `json:"text"`
		Link string `json:"link"`
		IDStr string `json:"id_str"`
		CanonicalID string `json:"canonical_id"`
		Parent string `json:"parent"`
		SourceType string `json:"source_type"`
		ProviderType string `json:"provider_type"`
		RetweetCount int `json:"retweet_count"`
		FavouritesCount int `json:"favourites_count"`
		Images []interface{} `json:"images"`
		ImagesCount int `json:"images_count"`
		Audio []interface{} `json:"audio"`
		AudioCount int `json:"audio_count"`
		Videos []interface{} `json:"videos"`
		VideosCount int `json:"videos_count"`
		PlaceName string `json:"place_name"`
		PlaceID string `json:"place_id"`
		PlaceContext string `json:"place_context"`
		PlaceCountry string `json:"place_country"`
		PlaceCountryCode string `json:"place_country_code"`
		PlaceCountryCenter []float64 `json:"place_country_center"`
		LocationPoint []float64 `json:"location_point"`
		LocationRadius int `json:"location_radius"`
		LocationMark []float64 `json:"location_mark"`
		LocationSource string `json:"location_source"`
		Hosts []interface{} `json:"hosts"`
		HostsCount int `json:"hosts_count"`
		Links []interface{} `json:"links"`
		LinksCount int `json:"links_count"`
		Mentions []string `json:"mentions"`
		MentionsCount int `json:"mentions_count"`
		Hashtags []interface{} `json:"hashtags"`
		HashtagsCount int `json:"hashtags_count"`
		ClassifierLanguage string `json:"classifier_language"`
		ClassifierLanguageProbability float64 `json:"classifier_language_probability"`
		WithoutLLen int `json:"without_l_len"`
		WithoutLuLen int `json:"without_lu_len"`
		WithoutLuhLen int `json:"without_luh_len"`
		User struct {
			ScreenName string `json:"screen_name"`
			UserID string `json:"user_id"`
			Name string `json:"name"`
			ProfileImageURLHTTPS string `json:"profile_image_url_https"`
			AppearanceFirst time.Time `json:"appearance_first"`
			AppearanceLatest time.Time `json:"appearance_latest"`
		} `json:"user"`
	} `json:"statuses"`
	Aggregations struct {
	} `json:"aggregations"`
}
```
