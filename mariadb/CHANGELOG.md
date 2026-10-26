- Properly close s6 notification file descriptors (#3)

* Properly close s6 notification file descriptors

* Close the s6 notification fd &3 in the client so it is not inherited

Co-authored-by: Laszlo Magyar <lmagyar1973@gmail.com>
Co-authored-by: Stefan Agner <stefan@agner.ch>
