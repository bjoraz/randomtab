# Random page in category

Tool created by [Ahecht](https://en.wikipedia.org/wiki/User:Ahecht). Source available at [source.php](https://randomincategory.toolforge.org/source.php) or on [Gitlab](https://gitlab.wikimedia.org/toolforge-repos/randomincategory/).

The [RandomInCategory](https://randomincategory.toolforge.org) tool is a replacement for [Special:RandomInCategory](https://en.wikipedia.org/wiki/Special:RandomInCategory) that actually chooses a page randomly. Includes options for filtering results by namespace and type. To use on a wiki, replace `[[Special:RandomInCategory/CATEGORY_NAME]]` with `[[toolforge:RandomInCategory/CATEGORY_NAME]]` or `[[toolforge:RandomInCategory/CATEGORY_NAME&OPTIONAL_PARAMETERS]]`.

Multiple categories can be specified by adding the `category2=`, `category3=`, etc. parameters to the url, e.g. `[[toolforge:RandomInCategory/Fish&category2=Whales&category3=Crabs&category4=Plankton]]`.

By default, the script assumes the category is from [en.wikipedia.org](https://en.wikipedia.org/wiki/). This can be overridden by adding the `server=` parameters to the url, e.g. `&server=commons.wikimedia.org`. Do not include "https://" in the site name. The server must at one of the following Wikimedia-owned domains:

* mediawiki.org
* toolforge.org
* wikibooks.org
* wikidata.org
* wikimedia.org
* wikinews.org
* wikipedia.org
* wikiquote.org
* wikisource.org
* wikiversity.org
* wikivoyage.org
* wiktionary.org

Results can be filtered by namespace and type by adding the `namespace=` and `type=` parameters to the url, e.g. `&namespace=2|118&type=page`. These parameters are documented as `cmnamespace` and `cmtype` at [https://www.mediawiki.org/wiki/API:Categorymembers](https://www.mediawiki.org/wiki/API:Categorymembers), but the "|" between namespaces can optionally be replaced with a ";" or "!" for compatibility with wikilinks.

For performance reasons, the list of items is cached for 10 minutes. To manually refresh the cache, set the `purge=` parameter to any value. Also, any categories with more than 100,000 pages will either redirect to [Special:RandomInCategory](https://en.wikipedia.org/wiki/Special:RandomInCategory) or, if multiple categories were requested, return an error message.

Set the `returntype=` parameter to `article` or `subject` to return the associated subject page if the randomly chosen page is a talk page. Similarly, `returntype=talk` will return the associated talk page if the randomly chosen page is a subject page. If the associated page does not exist, the original randomly chosen page will be returned.

The script will return the URL of the article and other debugging data instead of actually performing the redirect if the `debug=` parameter is set to any value.

Any other parameters in the URL will be passed on to the target page.

#### Examples:

Pending enwiki AFC Drafts in Draft: or User: namespaces:
: [/Pending_AfC_submissions?server=en.wikipedia.org&namespace=2|118&type=page](https://randomincategory.toolforge.org/Pending_AfC_submissions?server=en.wikipedia.org&namespace=2|118&type=page)

Categories about US States:
: [/States_of_the_United_States?&type=subcat](https://randomincategory.toolforge.org/States_of_the_United_States?&type=subcat)

Featured pictures on Wikimedia Commons:
: [/Featured_pictures_on_Wikimedia_Commons?server=commons.wikimedia.org&type=file](https://randomincategory.toolforge.org/Featured_pictures_on_Wikimedia_Commons?server=commons.wikimedia.org&type=file)

Page with the Wikiproject Medicine banner on its talk page:
: [/All WikiProject Medicine articles?returntype=article](/All WikiProject Medicine articles?returntype=article)

Edit an article about a primary color:
: [/Primary_colors?type=page&action=edit](https://randomincategory.toolforge.org/Primary_colors?type=page&action=edit)

---

The MIT License

Copyright © 2020-2026 [Ahecht](https://en.wikipedia.org/wiki/User:Ahecht)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.