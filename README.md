# Open Legal Dictionary

[Open Legal Dictionary](https://www.openlegaldictionary.com) is an open source legal dictionary containing thousands of legal terms and definitions.

The code for this app is available on [Github](https://github.com/digitallawyer/openlegaldictionary). This app is hosted on Github Pages, and makes use of:

* Jekyll (including various plugins)
* Algolia ([instantsearch.js](https://community.algolia.com/instantsearch.js/))
* Google Ngram Viewer ([books.google.com/ngrams](https://books.google.com/ngrams))

Data for the definitions was sourced from:

* Black Law's Dictionary 2nd Edition (2010)
* The US Courts Glossary ([uscourts.gov/glossary](http://www.uscourts.gov/glossary))

Data from Black Law's Dictionary 2nd Edition still has many issues, including missing records and typo's as a result of the OCR process. Whilst working with this data is not exactly convenient, the effort required was much alleviated as a result of the work of various individuals and organizations:

* [LexPredict](https://www.lexpredict.com), which made available a version of Black Law's Dictionary 2nd Edition [on Github](https://github.com/LexPredict/lexpredict-legal-dictionary).
* [Wikisource](https://en.wikisource.org/), which hosts a [scanned version](https://en.wikisource.org/wiki/Index:Black%27s_Law_Dictionary_(Second_Edition).djvu) of Black Law's Dictionary 2nd Edition with partial validation.

Cleaned up source files can be downloaded from the Github repository of this project:

* US Courts Glossary ([json](https://github.com/digitallawyer/openlegaldictionary/blob/master/_data/usc.json)) 
* Black Law's Dictionary 2nd Edition (2010) ([json](https://github.com/digitallawyer/openlegaldictionary/blob/master/_data/bld.json)) 

## Contributing

### Contributing definitions

openlegaldictionary.com is an open database of legal definitions. Contributions are welcomed and will be shared with the community at large. To contribute to the legal definitions on openlegaldictionary.com:

- make a clone of this repository
- make any changes or corrections you'd like to the definition files (usc.json and bld.json)
- commit your changes and submit a pull request

Not sure where to start but keen to contribute to this open dataset? Contact me via [www.pietergunst.be](https://www.pietergunst.be).

### Contributing code

Pull requests are always welcome. To keep things clean, please create a feature branch for any new code you submit.

## Building

Experimentation and tinkering are encouraged, and there are many ways in which this app and the data pipeline can be optimized. 

- Clone this repository
- run `bundle install`

App configuration values are housed in `_config.yml`. Before you proceed,  you'll need to create an algolia account, and update the following values in `_config.yml`:

* `application_id`
* `index_name`
* `search_only_api_key`

To import data from one of the dictionaries, point to the dictionary file by updating the `source:` value in `_config.yml`. Note that the `bld,json` file housing the data from Black Law's Dictionary 2nd Edition is quite large, and will require a paying Algolia account to house the entire dataset.

The command to convert the definition file in separate pages, which can subsequently be read by Algolia, is:

`bundle exec jekyll pagemaster definitions`

Once you've imported a dictionary, you can run the application using:

- run `jekyll serve`

Once the application is running, you can run the following command (make sure to replace 'admin-key' with your Algolia admin key) to sync the definitions you imported with Algolia. 

- `ALGOLIA_API_KEY='admin-key' jekyll algolia`