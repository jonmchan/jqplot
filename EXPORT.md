# Exporting Instructions

Instructions on how to export the latest version of jqplot from the original repo (https://bitbucket.org/cleonello/jqplot/downloads/) to github.

## Requirements

 * hg - http://mercurial.selenic.com
 * hg-git - http://hg-git.github.com

On OS X, I used brew to install both of these via ``` $ brew install hg hg-git```. I had to also install the python modules, don't really know if it was 100% necessary but I had some issues setting it up: ``` $ sudo easy_install gitpython mercurial hg-git```

Make sure you follow the steps on the hg-git website to add the hggit key to the extensions block in your ~/.hgrc.

## Commands

### Initial export
```bash
hg clone https://bitbucket.org/cleonello/jqplot
pushd jqplot
hg bookmark -r default master
hg push git+ssh://git@github.com:jonmchan/jqplot.git
popd
```


### Subsequent exports
```bash
pushd jqplot
hg pull
hg push git+ssh://git@github.com:jonmchan/jqplot.git
```
