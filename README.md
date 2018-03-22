# Django_user
python3下安装django mezzanine pip3
python manage.py collectstatic 
pip3 install uwsgi
uwsgi --http :8000 --module Django_auth_example.wsgi
nginx.conf
uwsgi.ini
uwsgi_params

#nginx.conf

server {
  listen 80;
  server_name .aaa.top;
  charset utf-8;
  
  location /static {
    alias /var/www/Djan/static;
    
    }
    
  location / {
    uesgi_pass django;
      include /var/www/uwsgi_params;
      }
  }
  
  #uwsgi.ini
  
  chdir =/var/www/Djan
  model = D_a_e.wsgo
  home = /var/www/env27
  master = true
  processes = 10
  
  socket = :8001
  chmod-socket = 666
  vacuum =true
  
  #uwsgi_params  side
  
  nginx.conf文件放在enable
  rm default
  ll 查看
  链接
  
ln -s /var/www/nginx.conf Django_user
ls

重启
/etc/init.d/nginx restart


cd /var/www
uwsgi --ini uwsgi.ini

vi etc/re.rocal
/user/local/bin/uwsgi --ini /var/www/uwsgi.ini
:wq

外部装uwsgi

