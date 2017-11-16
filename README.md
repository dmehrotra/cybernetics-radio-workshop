# Spectrum Investigations...

You don't need to be a computer scientist to leverage technology to investigate systems of power and control. This workshop will provide students with hands on examples that they can use to understand the signals that surround them. From cross referencing airplane transponder broadcasts with FAA data, to analyzing the contents of shipping containers, a software defined radio is an invaluable research tool that can yield unexpected results. In this class we will approach the SDR as a general purpose tool for investigating your surroundings. Some tools and concepts introduced will be RTL-SDR, GQRX, and scraping the web for government contracts. This workshop includes the price of a $20 RTL-SDR that participants will be able to take home.
- Plan
  - Introductions
  - Radio Concepts
  - Spectrum Allocation / FCC licenses
  - ADS-B eavesdropping
  - NOAA Weather Images

### Resources
* [Secret Life Of Machines](https://www.youtube.com/watch?v=2roG4jIjvEk) - A great and very British video about the history of radio. 
* [What is a radio](https://www.youtube.com/watch?v=jqGAneO79lY) - The theory and operation of early radio.
* [Spectrum Video](https://www.youtube.com/watch?v=cfXzwh3KadE) - Science@NASA: An Introduction To The Electromagnetic Spectrum
* [FCC Allocation Chart](https://www.nasa.gov/sites/default/files/thumbnails/image/january_2016_spectrum_wall_chart.jpg) - FCC Spectrum Allocation Chart
* [Licenses near me](https://fcc-licenses-near.me/) - FCC licenses near me.  Use lightly
* [Reboot.FCC](http://reboot.fcc.gov/spectrumdashboard/) - A better way to interact with spectrum allocation chart.
* [GQRX](http://gqrx.dk/) - Open source software to get started making sense of radio.
* [Dump1090](https://github.com/antirez/dump1090) - Dump1090 is a simple Mode S decoder for RTLSDR devices
* [Flight Radar 24](https://www.flightradar24.com/) 
* [FAA Aircraft Registrations](http://registry.faa.gov/aircraftinquiry/name_inquiry.aspx)
* [Satellite Sounds](http://satellite-sounds.dhruvmehrotra.info) - Sniffing Satellite Imagery

### Investigations
* [Spies in the Sky](https://www.buzzfeed.com/peteraldhous/spies-in-the-skies?utm_term=.cn52DRVlOq#.sfe94QxvnX) - Peter Aldhous + Charles Seife
* [Extraordinary Rendition](http://www.nytimes.com/2005/05/31/us/cia-expanding-terror-battle-under-guise-of-charter-flights.html) - Margot Williams
* [Wifi Sniffing at Mar-a-lago](https://gizmodo.com/any-half-decent-hacker-could-break-into-mar-a-lago-we-1795276155) - Jeff Larson, Surya Mattu, and Julia Angwin


### Installation of Dump1090

Install the dependencies + homebrew.

```sh
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
$ brew install cmake
$ brew install libusb
$ brew install pkgconfig
$ brew install sox
```
Install rtl_sdr...

```sh
$ cd ~/ # or another suitable place you'd like to keep the repos
$ git clone git://git.osmocom.org/rtl-sdr.git
$ cd rtl-sdr/
$ mkdir build
$ cd build/
$ cmake ../
$ make
$ sudo make install
$ rtl_test -t # You should see output like 'found 1 device(s)'
```
Install dump1090...

```sh
$ cd ~/ # or another suitable place you'd like to keep the repos
$ git clone https://github.com/antirez/dump1090.git
$ cd dump1090
$ make
$ ./dump1090 --interactive
```

