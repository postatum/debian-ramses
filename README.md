## Installation:

```shell
sudo add-apt-repository ppa:ramses-tech/ramses
sudo apt-get update
sudo apt-get install ramses
```

## Releasing new version of deb package:

(e.g. update ramses-X.X to ramses-Y.Y where X.X is the old version and Y.Y is the new one):

1. Clone this repo: `git clone git@github.com:ramses-tech/debian-ramses.git`
2. Rename "debian-ramses" to "ramses-Y.Y"
3. Enter the new version folder (ramses-Y.Y)
4. Edit `./debian` folder files if needed (e.g. `changelog` file)
5. Create .tar.gz: `dh_make -s --indep --createorig`
6. Build package: `debuild -S -sa`
7. Push package to Launchpad: `dput ppa:ramses-tech/ramses ../ramses_Y.Y_source.changes`
8. At Launchpad go to ramses PPA -> View package details -> Copy packages. Select new version of package. Destination PPA: This PPA.  Copy options: Copy existing binaries. And copy package to all supported series.
