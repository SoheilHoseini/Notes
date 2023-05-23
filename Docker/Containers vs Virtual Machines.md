There two techs are different ways of achieving virtualization (procedure where software is used to create an abstraction layer) and VMs are called *hardware virtualization* since it happens at hardware level but containers happen at the OS level.
For VMs, the abstraction layer is called hypervisor which is something that helps the VM to emulate a physical computer. The hypervisor manages the allocation of resources between different VM on the single physical host. Each VM has its own hardware, like virtual CPU virtual storage etc. 
In Docker, instead of virtualizing HW(hardware) like what HV (hypervisor) is doing for VM, containers virtualize the OS.


Using VMs we achieve isolation of machines and we can do like for example one server is several machines, relatively independent from each other not knowing the others exist.
In containers we have process isolation. When we normally run apps on our system, they can communicate with each other and are aware of the other existence but containers are separate and an application running in a container can only see what it needs to be run. Containers share the same OS, same Kernel but it seems to them that have their own

In VMs the hypervisor manages the access to the hardware and makes different machines out of a system and so we have more flexibility using hardware; Like we specify how mush CPU, RAM, etc. we need when creating a VM





### References
[IBM Technology-YouTube](https://www.youtube.com/watch?v=cjXI-yxqGTI)
[IBM Technology2-YouTube](https://www.youtube.com/watch?v=a1M_thDTqmU)
