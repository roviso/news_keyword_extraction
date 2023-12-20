# News Keyword Extraction
A terminal application to extract keywords from a corpus.

## Installation
- Clone the project into your local machine.
- Run `python -c 'import nltk; nltk.download('stopwords')'` from the terminal to download stopwords.
- Install project dependencies from `requirements.txt` using `pip` and `environment.yml` using `conda`.

## Instructions
### Command Line Interface
Navigate to `app/api` and run the following command to setup local packages.

    $ python setup.py install

Then navigate to the `app/api/extract_keywords/` directory and run `main.py` as per
 the following help (also accessible from the command line).
#### General Help
    $ python main.py -h
    
    usage: extract_keywords [-h] {extract,train} ...

    A program to extract the keywords from a nepali text.
    
    positional arguments:
    {extract,train}  available sub-commands
        extract        extract keywords from the provided texts
        train          train the idf value from the provided dataset

    optional arguments:
    -h, --help       show this help message and exit

#### Train Help
    $ python main.py train -h
    
    usage: extract_keywords train [-h] train_csv
    
    positional arguments:
    train_csv   .csv file containing the data for training the idf value
    
    optional arguments:
    -h, --help  show this help message and exit

#### Extract Help
    $ python main.py extract -h
    
    usage: extract_keywords extract [-h] [-n N] idf_json text_txt
    
    positional arguments:
    idf_json    .json file containing the pretrainied idf values
    text_txt    .txt file containing the text to extract keywords from
    
    optional arguments:
    -h, --help  show this help message and exit
    -n N        number of keywords to extract

### Web API
To run the this program as a Web API, head over to the `app` directory and start the uvicorn server as
    
    $ uvicorn --reload main:app

and go to `localhost:8000/docs` in your browser for further documentation on the API.