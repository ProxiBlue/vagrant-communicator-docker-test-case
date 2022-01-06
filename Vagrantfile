Vagrant.configure("2") do |config|
    config.vm.define "test-case", primary: false do |d|
        d.vm.communicator = 'docker'
        d.vm.provision :shell, :run => 'always', :path => "test_exec.sh", :privileged => true
        d.vm.provision :shell, :run => 'always', :path => "test_exec2.sh", :privileged => true
        d.vm.provider 'docker' do |box|
            box.image = "mysql:5.7"
            box.has_ssh = true
            box.remains_running = true
            box.env = { "MYSQL_ROOT_PASSWORD" => "booger" }
        end
    end
end
