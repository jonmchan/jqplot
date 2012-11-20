# Exporting Instructions

Instructions on how to export the latest version of jqplot from the original mercurial repo (https://bitbucket.org/cleonello/jqplot/downloads/) to github.

## Requirements

 * hg - http://mercurial.selenic.com
 * hg-git - http://hg-git.github.com

On OS X, I used brew to install both of these via ``` $ brew install hg hg-git```. I had to also install the python modules ``` $ sudo easy_install gitpython mercurial hg-git```, but I don't really know if it was 100% necessary because I had some issues setting it up and tinkered with a lot of commands.  

Make sure you follow the steps on the hg-git website to add the hggit key to the extensions block in your ~/.hgrc.

## Commands

### Initial export
```bash
hg clone https://bitbucket.org/cleonello/jqplot
pushd jqplot
hg bookmark -r default master
hg pull git+ssh://git@github.com:jonmchan/jqplot.git # to grab the commits for the EXPORT.md
hg update
hg push git+ssh://git@github.com:jonmchan/jqplot.git
popd
```


### Subsequent exports
```bash
pushd jqplot
hg pull
hg pull git+ssh://git@github.com:jonmchan/jqplot.git # only if changes made to EXPORT.md
hg update
hg push git+ssh://git@github.com:jonmchan/jqplot.git
```
