Vagrant.configure("2") do |config|
    config.vm.box = "generic/fedora33"
    config.vm.synced_folder ".", "/vagrant", type: "rsync"

    # Prepare provisioning
    $script = <<-'SCRIPT'
        ansible --version || sudo dnf install -y ansible
        ansible-playbook /vagrant/install.yml --extra-var "install_vbox=no"
    SCRIPT

    # Run provisioning
    config.vm.provision "shell",
        inline: $script

    # Post-up message
    config.vm.post_up_message = "See https://github.com/neikei/fedora-workplace-setup for help and bug reports."
end
