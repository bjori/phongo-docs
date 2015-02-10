```
git clone git@github.com:php/web-php.git
svn checkout http://svn.php.net/repository/phpdoc/modules/doc-en/
git clone git@github.com:bjori/phongo-docs.git doc-en/en/reference/phongo

cd doc-en
cat en/reference/phongo/language-snippets.ent >> en/language-snippets.ent
## Open doc-base/manual.xml.in
## Locate &reference.mongo.book;
## Add "&reference.phongo.book;"  above it



# Repeat these after each change
php doc-base/configure.php
phd -P PHP -f php -d doc-base/.manual.xml
rm -rf ../web-php/manual/en && mv output/php-web ../web-php/manual/en
```
