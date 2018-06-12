# prime-solr
Load the Solr index from content files

When setting up Solr to index a static web site, you can start by using 
wget to get html files from the site, then pushing the content to Solr using this project.

```bash
wget --wait=1  --random-wait -r -l 30 --convert-links --backup-converted --no-parent --rejected-log=logfile http://sitename.com
# now remove any unwanted files that wget has gotten.

# now clear the Solr core
python indexit.py --delete all

# now push content to the index
python indexit.py --dirname /home/me/sites/sitename.com
```
