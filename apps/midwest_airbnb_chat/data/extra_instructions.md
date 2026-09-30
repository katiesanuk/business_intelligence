# Extra Instructions

Rules the LLM follows when it writes SQL for `listings`.

- `price` is the nightly price in U.S. dollars. When the user asks what something costs, use `price` and round money to whole dollars in the answer.
- `host_is_superhost` and `instant_bookable` use `'t'` and `'f'` instead of true booleans. Filter using `'t'` or `'f'` (e.g., `filter(host_is_superhost == "t")`).
- `city` values are `'Chicago'`, `'Columbus'`, or `'Twin Cities'`. Filter using exact matches (e.g., `filter(city == "Chicago")`).
- `name` is the listing title. Search for text in titles using string matching (e.g., `filter(str_detect(name, "keyword"))`).
- `review_scores_rating` contains `NA` values for unrated listings. Use `mean(review_scores_rating, na.rm = TRUE)` inside `summarise()` to calculate average ratings.

<!-- Add more rules below (Assignment 05 asks for at least three). Good candidates:
     `host_is_superhost` and `instant_bookable` are the text values 't' and 'f',
     not booleans; how to match a city name the user types; how to search `name`
     case-insensitively; and whether to ignore rows whose `review_scores_rating`
     is NULL when averaging ratings. -->
