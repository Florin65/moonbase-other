./configure --build=$BUILD \
            --prefix=/usr \
            --sysconfdir=/etc \
            --docdir=/usr/share/doc \
            --mandir=/usr/share/man \
            --enable-local-rebuild \
            --local-rust-root=$SOURCE_DIRECTORY/install &&

# disable docs because it broke the build
sedit 's|#docs = true|docs = false|' config.toml &&

make ${MAKES:+-j$MAKES} &&

prepare_install &&

python ./x.py install -v &&

./standalone/install.sh --prefix=/usr --components=cargo &&

# On a fresh install fails with no such file/dir /etc/bash_completion.d so lets make one.
mkdir -p /etc/bash_completion.d/ &&
install -Dm0644 standalone/cargo/etc/bash_completion.d/cargo /etc/bash_completion.d/
