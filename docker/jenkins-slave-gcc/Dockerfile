FROM openshift3/jenkins-slave-base-rhel7:latest

USER root

ENV INSTALL_PKGS="gdb valgrind vim-enhanced gcc-c++ libstdc++ libstdc++-devel make automake autoconf OpenIPMI OpenIPMI-libs OpenIPMI-modalias fence-agents-ipmilan ipmitool OpenIPMI-devel cppunit cppunit-debuginfo cppunit-devel"

RUN yum repolist > /dev/null && \
    yum install -y --setopt=tsflags=nodocs \
      --enablerepo=rhel-7-server-optional-debug-rpms \
      --enablerepo=rhel-7-server-optional-rpms \
      --enablerepo=rhel-7-server-rpms \
      $INSTALL_PKGS && \
    rpm -V $INSTALL_PKGS && \
    yum clean all -y && \
    rm -rf /var/cache/yum

USER 1001
