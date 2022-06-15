# JDeveloper - specify JDK for IntegratedWebLogic

In fact, you have to go deep in configuration and startup scripts again. This time it is `setDomainEnv.sh` in domain's bin directory (`<system_directory>/DefaultDomain/bin/setDomainEnv.sh`).

Then just find the section where JAVA_HOME is set up and change accordingly. There are many ways how to do it from simple setting of JAVA_HOME beneath the whole section to precisely specifying JDK vendor, JDK type and so on. I chose the way of just changing what was already filled in:

```
if [ "${VM_TYPE}" = "JRockit" ] ; then
	JAVA_HOME="${BEA_JAVA_HOME}"
	export JAVA_HOME
else
	if [ "${JAVA_VENDOR}" = "Sun" ] ; then
		JAVA_HOME="${SUN_JAVA_HOME}"
		export JAVA_HOME
	else
		JAVA_VENDOR="Unknown"
		export JAVA_VENDOR
		JAVA_HOME="/opt/jvm/jdk1.8.0_251"
		export JAVA_HOME
		VM_TYPE=""
		export VM_TYPE
	fi
fi
```

Voila! The _IntegratedWebLogicServer_ starts with specified JVM...
