# In Legal Terms

Legal dictionary containing thousands of legal terms and definitions.

## Contributing

### Contributing definitions

inlegalterms.com is an open database of legal definitions. Contributions are welcomed and will be shared with the community at large. To contribute to the legal definitions on inlegalterms.com:

- make a copy of definitions.csv
- make any changes or corrections you'd like
- make sure to update the date
- submit a pull request

### Contributing code

Pull requests are always welcome. To keep things clean, please create a feature branch for any new code you submit.

## Building

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

## Acknowledgements

This project makes use of [jekyll-algolia][1], which plugs into the default Jekyll theme. Source data is Black Law's dictionary.

[1]: https://community.algolia.com/jekyll-algolia/
