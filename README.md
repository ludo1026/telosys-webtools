How to install
==========

* Download the JAR : telosys-monitoring.jar

* Put it in the application classpath or in the server classpath

* Add these lines in the web.xml of your application :

```xml
  <filter>
    <filter-name>Monitor</filter-name>
    <filter-class>org.telosys.webtools.monitoring.RequestsMonitor</filter-class>    
    <init-param>
    	<param-name>duration</param-name>
    	<param-value>1000</param-value> <!-- default is 1000 ( 1 sec )  -->
    </init-param>
    <init-param>
    	<param-name>logsize</param-name>
    	<param-value>100</param-value> <!-- default is 100 -->
    </init-param>
    <init-param>
    	<param-name>toptensize</param-name>
    	<param-value>10</param-value> <!-- default is 10 -->
    </init-param>
    <init-param>
    	<param-name>longestsize</param-name>
    	<param-value>10</param-value> <!-- default is 10 -->
    </init-param>
    <init-param>
    	<param-name>reporting</param-name>
    	<param-value>/monitoring</param-value> <!-- default is "/monitor" -->
    </init-param>
    <init-param>
    	<param-name>trace</param-name>
    	<param-value>false</param-value> <!-- default is false -->
    </init-param>
  </filter>
  <filter-mapping>
  	<filter-name>Monitor</filter-name>
  	<url-pattern>/*</url-pattern>
  </filter-mapping>
```

* Do not forget to restart your application server

* Navigate in your web application

### Monitoring Report page

* Go the monitoring report page. For that, add "/monitoring" at the end of the base URL of your application

_Example :_

if the base URL of your application is : http://my.application/web

then the URL of the report page is : http://my.application/web/monitoring

"/monitoring" can be redefined in the web.xml by the init-param "reporting" of the "telosys-monitoring" filter.

Actions
-------

You can change monitoring values with parameters in the "/monitoring" URL :
* ```action=clear``` : clear all logs
* ```duration=``` : request duration threshold
* ```logsize=``` : number of requests in the log
* ```topsize=``` : number of the top longuest requests
* ```longuestsize=``` : number of the longuest requests




Contact
---

Contact us at : [telosysteam@gmail.com](telosysteam@gmail.com)