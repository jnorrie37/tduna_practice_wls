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
    config.vm.define "db" do |db|
        db.vm.box = "generic/oracle7"
        db.vm.hostname = 'puppetmaster'
        db.vm.box.url  = "generic/oracle7"

        #Network Settings for db
        db.vm.network :private_network, ip: "192.168.40.100"

        #VM Settings for Oracle Linux Host
        db.vm.provider :virtualbox do |v|
            v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            v.customize ["modifyvm", :id, "--memory", 512]
            v.customize ["modifyvm", :id, "--name", "db"]
        end
    end

    #Setting up weblogic
    config.vm.define "weblogic" do |weblogic|
        weblogic.vm.box = "generic/oracle7"
        weblogic.vm.hostname = 'puppetmaster'
        weblogic.vm.box.url  = "generic/oracle7"

        #Network Settings for WebLogic
        weblogic.vm.network :private_network, ip: "192.168.40.100"

        #VM Settings for Oracle Linux Host
        weblogic.vm.provider :virtualbox do |v|
            v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
            v.customize ["modifyvm", :id, "--memory", 512]
            v.customize ["modifyvm", :id, "--name", "weblogic"]
        end
    end
end