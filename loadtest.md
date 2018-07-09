# Loadtest
## Installation
> $ brew install jmeter

> $ cd ~/workshop/

> $ curl -O https://github.com/raladev/load/raw/master/JARs/pepper-box-1.0.jar

> $ mv pepper-box-1.0.jar /usr/local/Cellar/jmeter/4.0/libexec/lib/ext

> $ jmeter

- add "Thread group"
- add "paperbox plain text config"
- add schema template
- add java request
- select classname com.gslab.pepper.sampler.PepperBoxKafkaSampler
- fill in the configuration
- select Num of thread and loop count
