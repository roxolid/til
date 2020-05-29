# JDeveloper - specify location for system directory

The default location is $HOME/.jdeveloper/<version>. This is also a location for system directory (named system<version>) which holds DefaultDomain directory where IntegratedWebLogic stores its domain. If you would like to hold this domain somewhere else, edit `$JDEVELOPER_HOME/jdeveloper/jdev/bin/jdev.boot` file and:

1. comment out the line:
    ```
    ide.user.dir.var = JDEV_USER_HOME,JDEV_USER_DIR
    ```

2. add another line:
    ```
    ide.user.dir = <your_desired_location>
    ```
    ie.
    ```
    ide.user.dir = /opt/mw/jdeveloper/12.2.1.4/user_home
    ```

Make sure the directory already exists!

The directories and files used by JDeveloper for many things (`SqlHistory`, `tmp`, `CodeTemplate.xml`), including the system directory (ie. `system12.2.1.4.42.190911.2248`) will be created here. And under system directory (besides many of JDeveloper modules directories) there is DefaultDomain directory, where the IntegratedWebLogic's domain lives.

My `jdev.boot` file contains:
```
...
...
#
# The ide.user.dir.var specifies the name of the environment variable
# that points to the root directory for user files.  The system and
# mywork directories will be created there.  If not defined, the IDE
# product will use its base directory as the user directory.
#
ide.user.dir = /opt/mw/jdeveloper/12.2.1.4.0/user_home
#ide.user.dir.var = JDEV_USER_HOME,JDEV_USER_DIR
...
...
```