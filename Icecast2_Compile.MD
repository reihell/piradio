[![WEB](https://img.shields.io/badge/compile-icecast-green)](https://www.reihell.se/)

 Orginal: https://jksinton.com/articles/rpi-compiling-icecast-support-openssl
 ```
 Fresh Pie Buster
 sudo apt-get update
 sudo apt-get upgrade
 sudo apt install icecast2
 onfigure hostname and passwords
 sudo apt remove icecast2

 Check if configfiles still there ls -l /etc/init.d/ /etc/ | grep icecast

 To Build icecast 2 with SSL
  sudo apt install git gcc build-essential (usually alredy installed)
  sudo apt install libcurl4-openssl-dev libxslt1-dev libxml2-dev libogg-dev libvorbis-dev libflac-dev libtheora-dev libssl-dev
  sudo apt install pkgconf autoconf dh-autoreconf libtool autogen
  optional sudo apt install libspeex-dev
  
  cd (or cd ~)
  mkdir git
  cd git
  git clone --recursive https://git.xiph.org/icecast-server.git
  cd icecast-server
  ./autogen.sh
  ./configure --with-curl --with-openssl --without-speex --enable-yp=no
  make -j4
  sudo make install
  
 sudo ln -s /usr/local/bin/icecast /usr/bin/icecast2
 sudo ln -s /usr/local/share/icecast /usr/share/icecast2

```
  create a cert, sudo chown icecast2:icecast /etc/icecast2/ssl/icecast.pem, fix icecast2.xml according to youre needs.
  or use certbot and Letsencrypt


  Read the comments in the orginal article at https://jksinton.com/articles/rpi-compiling-icecast-support-openssl
  

