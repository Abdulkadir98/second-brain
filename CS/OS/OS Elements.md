An operating sytem has 3 basic elements:
* Abstractions - processes, threads, file, socket, device management etc
* Mechanisms - way to operate on the abstractions such as scheduling of threads, allocating memory, interacting with hardware devices through drivers
* Policies - The policies determine how to apply the mechanisms - for eg. How many sockets can a program have access, how many threads can a porgram start etc

Application usually operate in user-land and OS executes in kernel/privileged land. User-land typically does not have access to hardware resources, applicatioons can access restricted resources using system calls offered by OS. There is context switching involved (some basic steps to transfer control from user-land to pivileged/OS level) which is not cheap and add some performance overhead