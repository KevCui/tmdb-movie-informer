---
Title: tmdb-movie-informer
Description: look up movie/TV series information from TMDb
Author: KrazyCavin
Tags: CLI, python, script
created:  26 Dec 2016
---

tmdb-movie-informer
===================

Show movie or TV series information, using API from [TMDB](https://developers.themoviedb.org/3/). It's really fast but it needs to register an [API KEY](https://developers.themoviedb.org/3/getting-started) first. Then put API KEY inside **config.ini** file

### What kind of information this script will display?
* Title: movie/TV series title
* Date: release date(day, month and year)
* Genre
* Length: run time(min)
* Rating: ratings from [TMDB](https://www.themoviedb.org/) and [IMDB](https://www.imdb.com)
* Links: links to TMDB and IMDB if available

### Requirement
* Python3
* beautifulsoup4
* texttable
* requests

### Install python package
* pip install -r requirements.txt

### How to use
```
usage: tmdb [-h] [-y [YEAR]] [-t] [-d] searchtext [searchtext ...]

positional arguments:
  searchtext            search text

optional arguments:
  -h, --help            show this help message and exit
  -y [YEAR], --year [YEAR]
                        year of release
  -t, --tv              search TV show
  -d, --debug           active debug log
```
:warning: With **-d**, a debug log file **tmdb.log** will be created in script-run-directory.

### Example
* List new star wars movie **Rogue One**
```bash
~ $ ./tmdb rogue one -y 2016
Find 2 results

+-----------------+------------+------------+------------+-----------------+------------------------------------------+
|      TITLE      |    DATE    |   GENRE    |   LENGTH   |     RATING      |                   LINK                   |
+=================+============+============+============+=================+==========================================+
| Rogue One: A    | 2016-12-14 | Action,    | 134        | TMDB: 7.4(848)  | https://www.themoviedb.org/movie/330459  |
| Star Wars Story |            | Adventure, |            | IMDB:8.2        | http://www.imdb.com/title/tt3748528      |
|                 |            | Sci-Fi     |            | (143,977)       |                                          |
+-----------------+------------+------------+------------+-----------------+------------------------------------------+
| The Rogue One:  | 2016-12-15 | Animation, | 3          | TMDB: 0.0(0)    | https://www.themoviedb.org/movie/431575  |
| A Star Wars Toy |            | Short,     |            |                 | http://www.imdb.com/title/tt6343680      |
| Story           |            | Comedy     |            |                 |                                          |
+-----------------+------------+------------+------------+-----------------+------------------------------------------+

```

* List **Game of Thrones** information
```bash
~ $ ./tmdb game of thrones -t
Find 1 result

+-----------------+------------+------------+------------+-----------------+------------------------------------------+
|      TITLE      |    DATE    |   GENRE    |   LENGTH   |     RATING      |                   LINK                   |
+=================+============+============+============+=================+==========================================+
| Game of Thrones | 2011-04-17 | Sci-Fi &   | [60]       | TMDB: 7.8(1420) | https://www.themoviedb.org/tv/1399       |
|                 |            | Fantasy,   |            |                 |                                          |
|                 |            | Action &   |            |                 |                                          |
|                 |            | Adventure, |            |                 |                                          |
|                 |            | Drama      |            |                 |                                          |
+-----------------+------------+------------+------------+-----------------+------------------------------------------+

```

* List episodes of **Season 3** in **Black Mirror**
```bash
~ $ ./tmdb black mirror -s 3
Find 6 results

+-----------------+------------+------------+------------+-----------------+------------------------------------------+
|      TITLE      |    DATE    |   GENRE    |   LENGTH   |     RATING      |                   LINK                   |
+=================+============+============+============+=================+==========================================+
| S3E1 Nosedive   | 2016-10-21 |            |            | TMDB: 7.667(3)  |                                          |
+-----------------+------------+------------+------------+-----------------+------------------------------------------+
| S3E2 Playtest   | 2016-10-21 |            |            | TMDB: 7.333(3)  |                                          |
+-----------------+------------+------------+------------+-----------------+------------------------------------------+
| S3E3 Shut Up    | 2016-10-21 |            |            | TMDB: 9.0(3)    |                                          |
| and Dance       |            |            |            |                 |                                          |
+-----------------+------------+------------+------------+-----------------+------------------------------------------+
| S3E4 San        | 2016-10-21 |            |            | TMDB: 8.0(4)    |                                          |
| Junipero        |            |            |            |                 |                                          |
+-----------------+------------+------------+------------+-----------------+------------------------------------------+
| S3E5 Men        | 2016-10-21 |            |            | TMDB: 7.5(2)    |                                          |
| Against Fire    |            |            |            |                 |                                          |
+-----------------+------------+------------+------------+-----------------+------------------------------------------+
| S3E6 Hated in   | 2016-10-21 |            |            | TMDB: 9.0(2)    |                                          |
| the Nation      |            |            |            |                 |                                          |
+-----------------+------------+------------+------------+-----------------+------------------------------------------+

```
