sedit "s:python23:python2:" Makefile &&

LIBTTF=/usr/share/fonts/liberation-fonts-ttf &&

make build &&

prepare_install  &&

if [ ! -d $LIBTTF ] ; then
  mkdir -p $LIBTTF
fi  &&

if [ -d old.libraries ] ; then
  rmdir old.libraries
fi  &&

cp -f $MODULE-ttf/* $LIBTTF
