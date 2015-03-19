# Package Build Repository for Igbinary

This repository was initially forked from https://github.com/igbinary/igbinary in order to add the debian folder used to package the extension to Debian/Ubuntu packages. We now use the watch file to download the sources directly from PECL and use dh_phppear to get all the maintainer's infos from package.xml.

## Update 

First, check for a newer update

    uscan --verbose

If a newer version is found, unzip it:

    tar xzf ../igbinary-X.X.X.tgz

Now build the package (replace PGP_KEY with your pgp key hash)

    dpkg-buildpackage -S -sa -rfakeroot -kPGP_KEY
    sudo pbuilder build ../*.dsc

## APT Repository

We also provide the packages in our PPA repositories:

* [PPA for PHP 5.5](https://launchpad.net/~ufirst/+archive/ubuntu/php55)
* [PPA for PHP 5.4](https://launchpad.net/~ufirst/+archive/ubuntu/php5-oldsable)


