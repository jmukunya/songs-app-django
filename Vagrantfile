Vagrant.configure(2) do |config|
  config.vm.box = "django-v1.0.0"
  config.vm.box_url = "http://boxes.gajdaw.pl/django/django-v1.0.0.box"
  config.vm.network :forwarded_port, guest: 8000, host: 8000, host_ip: "127.0.0.1"

$script = <<SCRIPT

cd /vagrant/songs
python manage.py runserver 0.0.0.0:8000 >/dev/null 2>&1 &

SCRIPT

  config.vm.provision "shell", inline: $script, run: "always"

  config.vm.post_up_message = "The application is available at http://127.0.0.1:8000"
end
