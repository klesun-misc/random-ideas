### Github Crawler for Code Fragment Search

See https://stackoverflow.com/questions/13321936/code-search-on-github-com

I always get sad when I need to find the source code given a known class name or a function name and fail because google does not index github code,
and github itself only allows a [limited search](https://docs.github.com/en/github/searching-for-information-on-github/searching-code) by file name.

The idea from user perspective should be dead simlpe: you open a webpage, there is a text area input - you paste code fragment, hit "Search" and get
the list of repositories that have this code occurences.

Will need to implement a crawler for that:
- Iteratively collect a list of repositories, most popular to be processed first
    - (https://github.com/search/advanced should greatly assist in that. When done with super popular repos, can iteratively get less popular by selecting small date windows)
    - (https://pygithub.readthedocs.io/en/latest/github.html#github.MainClass.Github.get_repos may come in handy as well)
- Clone each of them, collect text files of less than `X` KiB (for example 300) to exclude minified `/dist/` files and stuff. Files above `X` size should be stored as name list somewhere for analyzing and adjusting the `X` value.
- Build an index for exact text search. Most full-text search engines I managed to google seem to specialize on word search, though I believe elasticsearch provided an option to search by exact text. I remember we were working on an optimized text search in progmeistars, maybe that will help: https://github.com/klesun/Progmeistars_tasks/tree/master/SpecB_C-Data_SergeyIlich/g12-substring-partial-match. There was some simple, but effective concept, though it probably had to scan whole text file, so a 3rd party engine should be still beter...
- Implement the API for the web page to communicate with the text index engine
