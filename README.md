crystal
=======

Cloud native configuration management


## Design doc

### preface

If you've kept up with how Netflix is operating in the cloud, then you've certainly seen some good ideas. They've 
Come up with, and written about a number of technologies they use to be "cloud native".

Cloud native means working within the infrstructure rather than against it by treating it as a typical datacenter.
For example, after accepting that instances are inherintley ephemeral, you would create a system to make sure
you could easily clone and bring up new instances.

One way you could do that is by running chef on each node after it comes up. However, that starts to take a toll on
chef-server if you end up doing this all the time. Or what happens if you chef-server happens to be down when you need
to add more capacity as soon as possible?

Netflix solve this problem by pre-baking AMIs with [AMInator](http://techblog.netflix.com/2013/03/ami-creation-with-aminator.html)


### problem

the existing tools are over complicated and are for the most part not built for scale or for the cloud.

Netflix has an amazing suite of tools for running a cloud infrastructure. However, the tools work 

Chef is the platform I have the most experience with, so I will be picking on it.

Below is enumerated all the current design constraints which I would like to remove.


*todo: list problems*

### solutions

* first class support for interacting with aws services
* use a language which is fully homoiconic so that we control the order of execution of the DSL
* opinionated testing
* output is an image (ami)
