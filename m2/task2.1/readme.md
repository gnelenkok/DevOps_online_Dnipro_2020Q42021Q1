# TASK 2 #
------
### Hypervisors ###
> What are the most popular hypervisors for infrastructure virtualization?  
>> Nowadays, the most popular hypervisors are VMWARE ESXi, Microsoft Hyper-V and KVM.  
>
> Briefly describe the main differences of the most popular hypervisors.  
>> VMWARE is an expensive solution, exempt free version the ESXi. It is possible to forward USB devices, hot add CPU cores.  
Hyper-V is cheaper, but cannot forward USB devices properly. Hyper-V can reduce disk partitions compare with VMWARE ESXi.  
KVM is a free hypervisor. KVM does not have technical support.  

### Vagrant file ###
    Vagrant.configure("2") do |config|
      config.vm.box = "hashicorp/bionic64"
      config.vm.box_version = "1.0.282"
      config.vm.network "private_network", type: "dhcp"
      config.vm.provider :virtualbox do |vb|
        vb.memory = "2048"
        vb.cpus = 2
      end
      config.vm.define :server do |srv|
        srv.vm.hostname = "vagrant-client-gnelenkok"
      end
      config.vm.define :client do |client|
        client.vm.hostname = "vagrant-client-gnelenkok"
      end
    end
