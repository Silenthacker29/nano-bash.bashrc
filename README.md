# bash.bashrc
# bashrc

config.ru
# File: /web_apps/example_rack_app/config.ru

use Rack::ContentLength

app = lambda { |env| [200, { 'Content-Type' => 'text/html' }, 'Hello World'] }
run app

monit-nginx.conf
# File: /etc/monit/conf.d/nginx.conf

check process nginx
  with pidfile /var/run/nginx.pid
  start program = "/etc/init.d/nginx start"
  stop program = "/etc/init.d/nginx stop"
  group nginx
  
  
