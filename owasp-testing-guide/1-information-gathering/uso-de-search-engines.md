# Uso de search engines

## Conduct Search Engine Discovery Reconnaissance for Information Leakage

### Robots.txt

Se utiliza el archivo **robots.txt** presente en muchas paginas para que los navegadores determinen que elementos aparecen en ellos. Ahora de no estar bien configurados puede aparecer elementos indeseables.

### Buscando elementos expuestos

**Navegadores a considerar**

* [Baidu](https://www.baidu.com/), China’s [most popular](https://en.wikipedia.org/wiki/Web_search_engine#Market_share) search engine.
* [Bing](https://www.bing.com/), a search engine owned and operated by Microsoft, and the second [most popular](https://en.wikipedia.org/wiki/Web_search_engine#Market_share) worldwide. Supports [advanced search keywords](http://help.bing.microsoft.com/#apex/18/en-US/10001/-1).
* [binsearch.info](https://binsearch.info/), a search engine for binary Usenet newsgroups.
* [Common Crawl](https://commoncrawl.org/), “an open repository of web crawl data that can be accessed and analyzed by anyone.”
* [DuckDuckGo](https://duckduckgo.com/), a privacy-focused search engine that compiles results from many different [sources](https://help.duckduckgo.com/results/sources/). Supports [search syntax](https://help.duckduckgo.com/duckduckgo-help-pages/results/syntax/).
* [Google](https://www.google.com/), which offers the world’s [most popular](https://en.wikipedia.org/wiki/Web_search_engine#Market_share) search engine, and uses a ranking system to attempt to return the most relevant results. Supports [search operators](https://support.google.com/websearch/answer/2466433).
* [Internet Archive Wayback Machine](https://archive.org/web/), “building a digital library of Internet sites and other cultural artifacts in digital form.”
* [Startpage](https://www.startpage.com/), a search engine that uses Google’s results without collecting personal information through trackers and logs. Supports [search operators](https://support.startpage.com/index.php?/Knowledgebase/Article/View/989/0/advanced-search-which-search-operators-are-supported-by-startpagecom).
* [Shodan](https://www.shodan.io/), a service for searching Internet-connected devices and services. Usage options include a limited free plan as well as paid subscription plans.

Both DuckDuckGo and Startpage offer some increased privacy to users by not utilizing trackers or keeping logs. This can provide reduced information leakage about the tester.

* `site:` will limit the search to the provided domain.
* `inurl:` will only return results that include the keyword in the URL.
* `intitle:` will only return results that have the keyword in the page title.
* `intext:` or `inbody:` will only search for the keyword in the body of pages.
* `filetype:` will match only a specific filetype, i.e. png, or php.

Considerar busquedas:

```text
site:owasp.org
cache:owasp.org
```

### Google Hacking - Dorking

Apoyado en esos comandos buscamos obtener elementos deseables desde los navegadores.

```text
intitle:admbook intitle:Fversion filetype:php 
```

Ubicaria la version deseada.

```text
intitle:index.of mp3
```

 `intitle:index.of` followed by a search keyword. This can give a list of files on the servers. For example, `intitle:index.of mp3` will give all the MP3 files available on various types of servers

#### Google hacking database - buscar alguno

{% embed url="https://www.exploit-db.com/google-hacking-database" %}

#### Diggity program

{% embed url="https://resources.bishopfox.com/resources/tools/google-hacking-diggity/" %}



