# Polaris Catalog Search Links

[Polaris](http://www.iii.com/products/polaris) PowerPAC (OPAC) deep links are difficult to remember. The following URL shortcuts allow you to easily make short, easy-to-remember links to catalog searches. They are created through the use of Apache [mod_rewrite](http://httpd.apache.org/docs/current/mod/mod_rewrite.html) rules.

## How to Use

Add the Apache mod_rewrite rules (apache-mod_rewrite-rules.txt) to your Apache config or to an [.htaccess](http://httpd.apache.org/docs/current/howto/htaccess.html) file. *This is to be added to an Apache-based website (e.g. main library site), **NOT** the Polaris OPAC server (which uses IIS).*

## Search URL Patterns


Search Type | Pattern | Example
----------------|---------|--------
General Keyword | /**cat**/*keyword* | http://tscpl.org/cat/astronomy
Author | /cat/**au**/*author* | http://tscpl.org/cat/au/h+g+wells
Author Phrase | /cat/**aup**/*author+phrase* | http://tscpl.org/cat/aup/Wells,+H.+G.+(Herbert+George),+1866-1946
Title | /cat/**ti**/*title* | http://tscpl.org/cat/ti/time+machine
Title Phrase | /cat/**tip**/*title+phrase* | http://tscpl.org/cat/tip/The+time+machine+:+an+invention
Author + Title | /cat/**au**/*author*/**ti**/*title*, /cat/**ti**/*title*/**au**/*author* | http://tscpl.org/cat/au/wells/ti/time+machine, http://tscpl.org/cat/ti/hunger+games/au/egan
Subject | /cat/**su**/*subject* | http://tscpl.org/cat/su/mathematics
Subject Phrase | /cat/**sup**/*subject+phrase* | http://tscpl.org/cat/sup/holiday+cooking+--+Juvenile+literature
Series | /cat/**se**/*series* | http://tscpl.org/cat/se/ender+saga
Polaris Control Number | /cat/**cn**/*control_number* | http://tscpl.org/cat/cn/601537
Polaris Record Set | /cat/**rs**/*record_set_number* | http://tscpl.org/cat/rs/5522
ISBN | /cat/**isbn**/*isbn* | http://tscpl.org/cat/isbn/0060935464

## Complete Example

```html
For an excellent <a href="http://tscpl.org/cat/su/pirates">pirate adventure</a> story, 
be sure to read <a href="http://tscpl.org/cat/ti/treasure+island/au/stevenson">Treasure 
Island</a> by <a href="http://tscpl.org/cat/au/robert+louis+stevenson">Robert Louis 
Stevenson</a>.
```
> For an excellent [pirate adventure](http://tscpl.org/cat/su/pirates) story, be sure to read [Treasure Island](http://tscpl.org/cat/ti/treasure+island/au/stevenson) by [Robert Louis Stevenson](http://tscpl.org/cat/au/robert+louis+stevenson).

## Notes

*   Spaces should be replaced with "+" in URLs.