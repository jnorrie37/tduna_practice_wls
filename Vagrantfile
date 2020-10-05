Vagrant.configure("2") do |config|

    #Setting up Puppet Master
    config.vm.define "puppetmaster" do |puppetmaster|
        puppetmaster.vm.box = "generic/oracle7"
        puppetmaster.vm.hostname = 'puppetmaster'
        puppetmaster.vm.box.url  = "generic/oracle7"

        #Network Settings for Puppet Master
        puppetmaster.vm.network :private_network, ip: "192.168.40.100"

        #VM Settings for Oracle Linux Host
        puppetmaster.vm.provider :virtualbox do |v|
            v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            v.customize ["modifyvm", :id, "--memory", 512]
            v.customize ["modifyvm", :id, "--name", "puppetmaster"]
        end
    end

    #Setting up DB
    config.vm.define "DB" do |DB|
        DB.vm.box = "generic/oracle7"
        DB.vm.hostname = 'puppetmaster'
        DB.vm.box.url  = "generic/oracle7"

        #Network Settings for DB
        DB.vm.network :private_network, ip: "192.168.40.100"

        #VM Settings for Oracle Linux Host
        DB.vm.provider :virtualbox do |v|
            v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            v.customize ["modifyvm", :id, "--memory", 512]
            v.customize ["modifyvm", :id, "--name", "DB"]
        end
    end

    #Setting up WebLogic
    config.vm.define "WebLogic" do |WebLogic|
        WebLogic.vm.box = "generic/oracle7"
        WebLogic.vm.hostname = 'puppetmaster'
        WebLogic.vm.box.url  = "generic/oracle7"

        #Network Settings for WebLogic
        WebLogic.vm.network :private_network, ip: "192.168.40.100"

        #VM Settings for Oracle Linux Host
        WebLogic.vm.provider :virtualbox do |v|
            v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            v.customize ["modifyvm", :id, "--memory", 512]
            v.customize ["modifyvm", :id, "--name", "WebLogic"]
        end
    end
end