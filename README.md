# http2

This will contain HTTP/2 experiments with Golang (gophertiles etc.)

# compile

apt-get install  gcc g++ git golang docker.io make autotools
apt-get install autotools-dev screen

git clone https://github.com/bradfitz/http2

make # 4 minutes

service apache2 stop


go version  # shall be 1.5 ?


cd http2
go build .

cd /root/go/src
git clone https://camlistore.googlesource.com/camlistore
cd camlistore
go run make.go

# needed : camlistore.org/pkg/singleflight
cd ..
mv camlistore camlistore.org
cd /root/http2/h2demo
mkdir -p /root/go/src/github.com/bradfitz
mv /root/http2 /root/go/src/github.com/bradfitz/
cd /root/go/src/github.com/bradfitz/http2/h2demo
make

# run

./h2demo.linux -verbose=true -addr="46.101.243.92:443" -httpaddr="46.101.243.92:80"


# test

https://46.101.243.92/gophertiles


https://chrome.google.com/webstore/detail/http2-and-spdy-indicator/mpbpobfflnpcgagjijhmgnchggcjblin?utm_source=chrome-app-launcher-info-dialog

https://addons.mozilla.org/en-us/firefox/addon/spdy-indicator/

