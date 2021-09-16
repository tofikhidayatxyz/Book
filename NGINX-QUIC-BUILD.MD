https://www.alibabacloud.com/blog/how-to-build-nginx-from-source-on-ubuntu-20-04-lts_597793
https://blog.cloudflare.com/experiment-with-http-3-using-nginx-and-quiche/

./configure \
  --build="quiche-$(git --git-dir=../quiche/.git rev-parse --short HEAD)" \
  --prefix=/var/www/html \
  --sbin-path=/usr/sbin/nginx \
  --conf-path=/etc/nginx/nginx.conf \
  --http-log-path=/var/log/nginx/access.log \
  --error-log-path=/var/log/nginx/error.log \
  --with-pcre  \
  --lock-path=/var/lock/nginx.lock \
  --pid-path=/var/run/nginx.pid \
  --modules-path=/etc/nginx/modules \
  --with-http_v2_module \
  --with-stream=dynamic \
  --with-http_addition_module \
  --with-http_mp4_module \
  --with-http_ssl_module              	\
  --with-http_v2_module               	\
  --with-http_v3_module               	\
  --with-openssl=../quiche/deps/boringssl \
  --with-quiche=../quiche
