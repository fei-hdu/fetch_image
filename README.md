## Automatically fetch images in the list from google, flickr, and bing (.com)

### google
    
    fork from https://gist.github.com/crizCraig/2816295
    
    ref https://developers.google.com/image-search/v1/jsondevguide

### flickr

    ref https://secure.flickr.com/services/api/misc.urls.html
    
    ref https://secure.flickr.com/services/api/flickr.photos.search.html
    
    ref https://secure.flickr.com/services/api/explore/flickr.photos.search

### bing

because there is no appid for bing.com

#### dirty hacker

    bing.com/images/search?q=lisa&count=10&first=1

    re.compile('(?<=a href="/images/search\?q=' + query + '\&amp;view=detail&amp;id=).+?(?=\&amp;FORM=    IDFRIR)')

#### following 

    re.compile('(?<=<a id="m_fsi" href=").+?(?=" target)')

get full size link

## Useage:

### 1. edit list.lst

- contents: two column query and num
- if num is empty, num is default 50.
- multiwords split by one space ' ' words and num split by more then two spaces 

### 2. and then

	$python2 fetch.py

which website you need, please uncomment it in `fetch.py`.

### Depands:

**wget**  or  **aria2c** or none

which downloader you have, please uncomment it in `gl.py`, `fkr.py`, and `bg.py`.

**Notice:**

IF flickr `api_key` is Error, please modify `fkr.py` following the comment

## TODO

    add UTF8 support                   ----ok!
    add update flickr api_key method   ----ok!
    add try exception else             ----ok!
    add multiwords support             ----ok!
    add interior download without need other download addition     ----ok!
    add bing image search fetch        ----ok!
    add aria2 to download the image    ----ok!
    add flikr image search fetch       ----ok!
    add read words form list.lst       ----ok!
    add wget to download the image     ----ok!
    add google image search fetch      ----ok!

enjoy it!

power by lvzongting AT gmail.com & gaofeihifly AT gmail.com

[西电开源社区](http://linux.xidian.edu.cn/)

