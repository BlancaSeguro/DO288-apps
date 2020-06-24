# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent
<pre># Change the port to 8080
EXPOSE 8080

# Labels consumed by OpenShift
LABEL io.k8s.description=&quot;A basic Apache HTTP Server child image, uses ONBUILD&quot; \
      io.k8s.display-name=&quot;Apache HTTP Server&quot; \
      io.openshift.expose-services=&quot;8080:http&quot; \
      io.openshift.tags=&quot;apache, httpd&quot;

# Change web server port to 8080
RUN sed -i &quot;s/Listen 80/Listen 8080/g&quot; /etc/httpd/conf/httpd.conf

# Permissions to allow container to run on OpenShift
RUN chgrp -R 0 /var/log/httpd /var/run/httpd &amp;&amp; \
    chmod -R g=u /var/log/httpd /var/run/httpd

# Run as a non-privileged user
USER 1001
</pre>
