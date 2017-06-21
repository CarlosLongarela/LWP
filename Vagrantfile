ENV["LC_ALL"] = "es_ES.UTF-8"
ENV["PYTHONUNBUFFERED"] = "1"
ENV["ANSIBLE_FORCE_COLOR"] = "true"

Vagrant.configure("2") do |config|
    # Intentamos prevenir avisos 'stdin is not a tty'
    config.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"

    puts ""
    puts ""
    puts "   \033[38;5;118m______       \033[38;5;33m___       __   \033[38;5;206m________ "
    puts "   \033[38;5;118m___  /       \033[38;5;33m__ |     / /   \033[38;5;206m___  __ \\"
    puts "   \033[38;5;118m__  /        \033[38;5;33m__ | /| / /    \033[38;5;206m__  /_/ /"
    puts "   \033[38;5;118m_  /___      \033[38;5;33m__ |/ |/ /     \033[38;5;206m_  ____/ "
    puts "   \033[38;5;118m/_____/      \033[38;5;33m____/|__/      \033[38;5;206m/_/      "
    puts ""
    puts "   \033[38;5;118mLord         \033[38;5;33mWord           \033[38;5;206mPress"
    puts ""
    puts "   \033[4;36mLord of WordPress. One WordPress to rule them all.\033[0m"
    puts ""
    puts "   \033[0mv: 0.0.1a"
    puts "   \033[0mBy: Carlos Longarela"
    puts ""
    puts "   \033[0mLogo generated from: \033[38;5;33mhttp://patorjk.com/software/taag/#p=display&h=1&v=0&f=Speed&t=L%20W%20P"
    puts ""
    puts "   \033[38;5;220mDocs:                https://github.com/CarlosLongarela/lwp/wiki"
    puts ""
    puts ""
    puts "\033[0m"

    # Box
    config.vm.box = "ubuntu/xenial64"

    # Configuración de red
    # Para poder acceder por nombre debemos tener instalado Vagrant::Hostsupdater
    # Instalamos con $ vagrant plugin install vagrant-hostsupdater
    # Actualizamos con $ vagrant plugin update vagrant-hostsupdater
    config.vm.network :private_network, ip: "192.168.50.96"
    config.vm.hostname = "lwp.test"
    config.hostsupdater.aliases = ["stable.wordpress.test", "nightly.wordpress.test"]
#    config.hostsupdater.aliases = ["wordpress.test", "wordpress2.test"]

    # Si queremos mapear algún puerto
    #config.vm.network "forwarded_port", guest: 80, host: 8383
    #config.vm.network "forwarded_port", guest: 3306, host: 3366


    # Directorios compartidos
    config.vm.synced_folder "./www", "/home/webs",
        owner: "www-data",
        group: "www-data",
        mount_options: ["dmode=775,fmode=644"],
        create: true

#    config.vm.synced_folder "./www/logs", "/home/webs/wordpress.test/logs",
#        owner: "www-data",
#        group: "www-data",
#        mount_options: ["dmode=755,fmode=755"],
#        create: true

    # Configuración específica del Provider
    config.vm.provider "virtualbox" do |vb|
        vb.memory = 1024
        vb.cpus = 2
    end

    # Ejecutamos Ansible desde la máquina virtual para provisionar el software
    config.vm.provision "ansible_local" do |ansible|
        ansible.playbook = "provisioning/lwp.yml"
#        ansible.galaxy_role_file = "provisioning/requirements.yml"
        ansible.provisioning_path = "/vagrant"
    end
end
