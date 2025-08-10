# alx-project-0x14
## API ouverview
### Collection of information for movies, tv-shows, actors. Includes youtube trailer url, awards, full biography, and many other usefull informations. This api provides complete and updated data for over 9 million titles ( movies, series and episodes) and 11 million actors / crew and cast members. Support developers:
# API Endpoints Documentation

> **Note:**  
> - Every endpoint returns an object with a `results` key.  
> - Endpoints with pagination also include `page`, `next`, and `entries`.  
> - **All query parameters are optional** unless otherwise stated.

---

## **Titles**

### **Titles - Multiple**
- **Path:** `/titles`  
- **Description:** Returns an array of titles according to filters/sorting query parameters provided.  
- **Query Parameters:**  
  - `list` — unique parameter that sets the collection you want to query (options available in **Utils → Titles Lists**).  
  - Multiple other filters possible.  
- **Model:** `title`

---

### **Titles - By List of IDs**
- **Path:** `/x/titles-by-ids`  
- **Description:** Returns an array of titles according to the provided array of IDs.  
- **Query Parameters:**  
  - `list` — unique parameter for collection (options in **Utils → Titles Lists**)  
  - `idsList` — array of strings representing IDs.  
- **Model:** `title`

---

### **Title**
- **Path:** `/titles/{id}`  
- **Path Parameter:**  
  - `id` — IMDb ID of title (required)  
- **Description:** Returns title according to filters/sorting query parameters.  
- **Query Parameters:**  
  - `info`  
- **Model:** `title`

---

### **Title Rating**
- **Path:** `/titles/{id}/ratings`  
- **Path Parameter:**  
  - `id` — IMDb ID of title (required)  
- **Description:** Returns title rating and vote count.  
- **Query Parameters:** none  
- **Model:** `rating`

---

## **Seasons & Episodes**

### **Series Episodes**
- **Path:** `/titles/series/{id}`  
- **Path Parameter:**  
  - `id` — IMDb ID of series (required)  
- **Description:** Returns an array of episodes with only `episode id`, `episode number`, and `season number` in ascending order.  
- **Query Parameters:** none  
- **Model:** `light episode`

---

### **Seasons Number**
- **Path:** `/titles/seasons/{id}`  
- **Path Parameter:**  
  - `id` — IMDb ID of series (required)  
- **Description:** Returns the number of seasons (integer).  
- **Query Parameters:** none  

---

### **Episodes by Season**
- **Path:** `/titles/series/{id}/{season}`  
- **Path Parameters:**  
  - `id` — IMDb ID of series (required)  
  - `season` — season number (required)  
- **Description:** Returns an array of episodes (only for given season) with `episode id`, `season number`, and `episode number`.  
- **Query Parameters:** none  
- **Model:** `light episode`

---

### **Episode**
- **Path:** `/titles/episode/{id}`  
- **Path Parameter:**  
  - `id` — IMDb ID of episode (required)  
- **Description:** Returns episode details according to filters/sorting.  
- **Query Parameters:**  
  - `info`  
- **Model:** `title`

---

## **Upcoming Titles**
- **Path:** `/titles/x/upcoming`  
- **Description:** Returns upcoming titles according to filters/sorting.  
- **Query Parameters:** multiple  
- **Model:** `title`

---

## **Search**

### **Titles by Keyword**
- **Path:** `/titles/search/keyword/{keyword}`  
- **Path Parameter:**  
  - `keyword` — search term (required)  
- **Description:** Returns titles matching keyword with filters/sorting.  
- **Query Parameters:** multiple  
- **Model:** `title`

---

### **Titles by Title**
- **Path:** `/titles/search/title/{title}`  
- **Path Parameter:**  
  - `title` — full or partial title (required)  
- **Description:** Returns titles matching provided title with filters/sorting.  
- **Query Parameters:**  
  - multiple  
  - `exact` — boolean; exact lookup if `true` (default `false`)  
- **Model:** `title`

---

### **Titles by Aka's**
- **Path:** `/titles/search/akas/{aka}`  
- **Path Parameter:**  
  - `aka` — alternate title (case-sensitive, exact match) (required)  
- **Description:** Returns titles matching aka with filters/sorting. Works only for exact matches.  
- **Query Parameters:** multiple  
- **Model:** `title`

---

## **Actors**

### **Actors List**
- **Path:** `/actors`  
- **Description:** Returns actors according to filters.  
- **Query Parameters:**  
  - `limit`  
  - `page`  
- **Model:** `actor`

---

### **Actor by ID**
- **Path:** `/actors/{id}`  
- **Path Parameter:**  
  - `id` — IMDb ID of actor (required)  
- **Description:** Returns actor details.  
- **Model:** `actor`

---

## **Utils**

### **Title Type**
- **Path:** `/title/utils/titleType`  
- **Description:** Returns array of title types.

---

### **Genres**
- **Path:** `/title/utils/titleType` *(Possibly intended as `/title/utils/genres`)*  
- **Description:** Returns array of genres.

---

### **Titles Lists**
- **Path:** `/title/utils/lists`  
- **Description:** Returns array of lists (for `list` query parameter).
