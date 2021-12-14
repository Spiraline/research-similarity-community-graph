# Research Similarity Community Graph based on affiliation

Numerous graduate school laboratories research their fields and submit papers to appropriate conferences/journals. However, it is not easy for them to know what kind of research is being conducted in other laboratories and which laboratory conducts research similar to theirs. In this project, we propose a research similarity metric between laboratories based on affiliation to meet the needs of the target users and implement a community graph based on the similarity using React and D3. Through this, professors, graduate students, and undergraduate students wishing to enter graduate school can obtain the information they want.

### Frontend (Community Graph)
- Community graph implementation using nodes and links information
~~~
$ cd front/community_graph
$ yarn add react-scripts rc-slider
$ yarn start
~~~

**[Overview]**

![overview](https://user-images.githubusercontent.com/44594966/145974635-ba3d4a55-2449-4777-8d18-d4baea9bf1e3.JPG)

**[School View]**

![schoolview](https://user-images.githubusercontent.com/44594966/145974641-f11c34d0-33c2-41fc-99c9-0f71905ea355.JPG)

**[Link Clicked]**

![link_clicked](https://user-images.githubusercontent.com/44594966/145974647-17efd07d-2332-4e17-874b-6e66dc329112.JPG)

### Backend (Crawler)
- Crawl data with python package ```selenium```
1. Install selenium package for python with command ```pip3 install selenium requests bs4```
2. Download chrome driver for your chrome version.
3. Locate chrome driver in your execution path.

- `crawl_conference.py` : Crawl conference name and metadata from **research.com**
- `crawl_journal.py` : Crawl journal name and metadata from **research.com**
- `crawl_homepage.py` : Crawl lab information from each graduate school homepage
- `crawl_paper_title.py` : Crawl paper title from professor's title from **google scholar** (need output of `crawl_homepage.py`)
- `get_bibtex_from_title.py` : Crawl paper bibtex from paper title from **semantic scholar** (need output of `crawl_paper_title.py`)
- `json_gen.py` : Format crawled data into json file (need output of `crawl_conference.py`, `crawl_journal.py`, `crawl_homepage.py`, `get_bibtex_from_title.py`)
