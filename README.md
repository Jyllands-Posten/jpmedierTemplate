JPMedier template scala, play and slick
=================================

This project is based on our current knowledge of how to best make a json restful api on scala, play and slick.
To create a new project, copy the contents of this project, delete the .git directory and create a new git repo.
For now this is the best way to start a new project, maybe in the future, we might create an activator template.

Database Access
===============
If you have an existing database, you can generate dataaccess classes by running `sbt gen-tables`. The classes will be generated under target/src_managed.
It is recommended to copy the generated files under app/models and delete the content in target.
A docker container, with mysql, can be started by running `./start_db`, this can be used for dev and test.


Controllers
===========

This template contains only one controller: The HealthController.
In this template you will find that is simply always returns ok, it is recommended to have the health endpoint also check that the services it needs are up and runing.



Components
==========

- Module.scala:

  Shows how to use Guice to bind all the components needed by your application.

Filters
=======
The LoggingFilter will log all requests.
 
 Best practices
 ===============
 - Unless you have a very good reason, you should always make your controller actions async.
 - The only place in your codebase where you should allow async.await is in tests/
 