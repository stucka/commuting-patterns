## U.S. Census Bureau commuting pattern parser

This takes commuting data from the U.S. Census Bureau, summarizes it to county or county-like geographies, then tries to build a couple useful reports out of it. Counties are handled by FIPS codes, a five-character identification system.

### county-highlights.json
For a given county, what counties are important to it?

This is generated using `get-commuting-data.ipynb`. Supporting counties are shown in rough order of importantance, if they either represent at least 10 percent of the workforce in that county, or that county supplies at least 20 percent of its workforce (e.g., bedroom communities).

You can directly access that file at https://raw.githubusercontent.com/stucka/commuting-patterns/master/county-highlights.json

### us-county-commuters.json
This contains data for every county that supports another, even if it's a single employee. Don't ignore the 'meta' tree.

### get-commuting-data.ipynb
A Jupyter Notebook that downloads and processes the data. You may not need to run this, unless you want to change the cutoff points for the file you're probably looking for, `county-highlights.json`

This will download about 1gb of GZIPped files from the U.S. Census Bureau; combine them in an awful way to create about 8gb of data; and then begin processing it to create the above files. This takes a while.

### parsed folder
Within the `parsed` folder are state-level reports, including the total number of commuters and total number of workers from each county. You're even less likely to need this.
