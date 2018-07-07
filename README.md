# In Legal Terms

Legal dictionary containing thousands of legal terms and definitions.

##Contributing

##Building

- Clone repository
- `bundle install`
- `jekyll serve`

To generate:

`jekyll generate`

To import from csv:

~~~~

ruby -rubygems -e 'require "jekyll-import";
    JekyllImport::Importers::CSV.run({
      "file" => "sourcefile.csv"
    })'
~~~~

##Acknowledgements

This project makes use of [jekyll-algolia][1], which plugs into the default Jekyll theme. Source data is Black Law's dictionary.

[1]: https://community.algolia.com/jekyll-algolia/
