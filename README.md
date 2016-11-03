A Ruby wrapper for the [arXiv API](http://arxiv.org/help/api/index). ArXiv is an open access pre-print server used primarily in physics, mathematics, computer science, quantitative biology, quantitative finance and statistics.

_This is not a complete wrapper around the arXiv API. We'll be making improvements as needed for our overlay journals. If you'd like something added, please create an issue or pull request._

### Fetching a manuscript
Grab a manuscript using the arXiv document id:

    manuscript = Arxiv.get('1202.0819')

And inspect it:

    manuscript.revision?  # => false
    manuscript.title      # => "Laser frequency comb techniques for precise astronomical spectroscopy"
    manuscript.abstract   # => "Precise astronomical spectroscopic analyses routinely assume..."
    manuscript.arxiv_id   # => "1202.0819"
    manuscript.version    # => 1
    manuscript.pdf_url    # => "http://arxiv.org/pdf/1202.0819v1"

### Authors
Look up a manuscript's authors:

    authors = manuscript.authors  # => an array of all the manuscript's authors
    authors.map(&:name)   # => ["Michael T. Murphy", "Clayton R. Locke", "Philip S. Light", "Andre N. Luiten", "Jon S. Lawrence"]

    # a single author
    authors.last.name           # => "Jon S. Lawrence"
    authors.last.affiliations   # => ["Australian Astronomical Observatory", "Macquarie University"]

### Categories
Look at a manuscript's categories:

    manuscript.categories                       # => an array of categories
    manuscript.categories.map(&:abbreviation)   # => ["astro-ph.IM", "astro-ph.CO", "astro-ph.EP"]

    # a single category
    manuscript.primary_category.name          # => "astro-ph.IM"
    manuscript.primary_category.description   # => "Physics - Instrumentation and Methods for Astrophysics"

### License
This is an open source project built by {Scholastica}[https://scholasticahq.com] under the {MIT-LICENSE}[https://github.com/scholastica/timber/blob/master/MIT-LICENSE].

