Vagrant.configure("2") do |config|

  # This is a common base box with a 40GB hard drive. Bento is a Chef project
  # and can be generally trusted. 
  config.vm.box = "bento/ubuntu-16.04"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.33.10"

  # Mount the colonel project it the expected production web root.
  config.vm.synced_folder "./", "/opt/company", 
    owner: "www-data", group: "www-data"
  
  # Configure Virtualbox parameters around certain desired attributes
  # of the guest.
  config.vm.provider "virtualbox" do |vb|
    # We need 2GB memory to allow the database to run properly.
    vb.memory = "2048"
  end

  # Ansible will run when we provision the box. 
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.verbose = 'vvv'
  end
end