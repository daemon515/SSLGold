SSLGold
=======

The original Gold linker source from binutils2.24 with my experimental updates
If you want to use this:

-> Download the binutils2.24.tar.gz from http://ftp.gnu.org/gnu/binutils/. [The gold modifications are based on 2.24 binutils version]

-> We want to replace the gold folder in the downloaded binutils (e.g. binutils2.24/gold) and build with the modified version of the gold linker. Follow the below sequence of steps

$ git clone https://github.com/SajoSG/SSLGold.git

$ rm -rf binutils2.24/gold

$ mv SSLGold/gold binutils2.24

$ cd binutils2.24

$ ./configure –prefix=$(specify_where_to_store_bins) –enable-gold –enable-plugins

$ make

$ make install

-> Use the ld.gold found in $(specify_where_to_store_bins)/bins as the default linker

-> PLT randomization build options:
--plt-random-size=SIZE → SIZE by which to increase each plt entry size
-z, plt-random-sequence → changes the sequence order of the PLT entries
--plt-boobytrap-frequence=COUNT → Add booby trap for every COUNT PLT entries
