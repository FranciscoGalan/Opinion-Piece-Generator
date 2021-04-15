# Opinion Piece Generator

An neural network which writes opinion pieces based on recent news and the style of an author.

![](https://github.com/FranciscoGalan/Opinion_Piece_Generator/blob/main/Media/newspaper_cover.JPG)

NOTE: Although all the examples shown in this file are in Spanish, the model can be used for any language.

## What it does

The Opinion Piece Generator generates a rough draft of an opinion piece based on the style of one or various texts:

> El día pasado entre el segundo debate se encuentra en estas agencias que se enredó de acuerdo al INE. El alumno no es menor, pero en vez de invertir ninguno de sus términos en nuestro país. Pero es un gobierno en otro momento, cuando está de acuerdo. Los militares no son las propuestas ni lograrán crecimiento que nunca podemos predecir o ver las divisas en la mayoría de la sociedad. Ahora bien, el INE se decidió, la libertad y un 20% de la población más alta del país hoy que le volvió al expresidente de la del Superior de la Constitución. En su vez, el Estado de medicamentos en 2017 del viejo régimen de oprobio y a medio de un comportamiento de una semana de las personas estadounidenses, en otros ámbitos de la vida para el Instituto Nacional de Normalización y venta del Banco de la Revolución Pública, hacen de favor del partido. Pero es el que hoy ha hecho un acompañamiento heroico del artículo de Andrés Manuel López Obrador para su presidencia...
>

Fragments of the generated text could then be used for social media content or other marketing materials: 

![](https://github.com/FranciscoGalan/Opinion_Piece_Generator/blob/main/Media/dashboard_tweets.png)

Finally, the project includes metrics and visualizations to see how well the Generator imitates the style of the original texts. The following is a dashboard based on the articles of the Mexican columnist Denisse Dresser:

![](https://github.com/FranciscoGalan/Opinion_Piece_Generator/blob/main/Media/dresser_dashboard.JPG)



## How it is built

To create the  generator, we followed these five steps:

![](https://github.com/FranciscoGalan/Opinion_Piece_Generator/blob/main/Media/pipeline_diagram.JPG)

To demonstrate, we selected five prominent Mexican columnists and used their articles as a basis.

### Scraping 

We used [Selenium](https://selenium-python.readthedocs.io/) to extract all the links to the articles the authors, either from their personal website or a news & media website. Then, we extracted the body of the articles with [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/).

[^1]: The scrapers can be found in the /Scraping directory and the raw data is located in Data/Data_raw.

Here's a Notebook example: [scraper_Enrique_Krauze.ipynb](https://nbviewer.jupyter.org/github/FranciscoGalan/Opinion_Piece_Generator/blob/main/Scraping/scraper_Enrique_Krauze.ipynb)



### Cleaning

We then removed the html tags from the articles using RegEx. 

Here is the Notebook `hola.ipybn`, which contains all the cleaning functions:

- `function()`removes all html tags. 



### Analyzing

Link to modules:

- WordCloud
- Readability Index
- Syllables and sentence length
- Word frequency

Explain all the functions 

Tabla con las métricas

### Modeling



### Generating

We used a Neural Network LSTM and trained it with over 1000 epochs.



## Dataset

The dataset with all the scraped and cleaned articles from the authors (Denisse Dresser, Enrique Krauze, John Ackerman, Ricardo Raphael, and Valeria Moy) can be found in the /Data/Data_clean_csv directory.

| Dataset  | Location                                                     | Date of scraping |
| -------- | ------------------------------------------------------------ | ---------------- |
| Articles | https://github.com/FranciscoGalan/Opinion_Piece_Generator/blob/main/Data/Data_clean_csv/clean_dataframe.csv | 91-03-2021       |