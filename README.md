#### ansible-newrelic
New Relic Server, APM, Nginx and MySQL Monitor Ansible role

#### ---USAGE ####
### Playbook ###
```Yaml
- hosts: yourhost
  roles:
    - newrelic
```
### group/host vars ###
```Yaml
# License key
nr_license: 'YOUR_LICENSE_KEY'
# Set the ones you want as 'true', they are all set 'false' by default
monitor_server: true
monitor_apm: true
monitor_nginx: true
monitor_mysql: true
```
#### ---NOTES ####
Remember to add *-javaagent: /opt/newrelic/newrelic.jar* to your JVM startup environment variables.

e.g.:
  For Tomcat, edit the bin/setenv.sh file and add the above javaagent option to the CATALINA_OPTS variable:
```Shell
  export CATALINA_OPTS="${CATALINA_OPTS} -javaagent: /opt/newrelic/newrelic.jar"
```
