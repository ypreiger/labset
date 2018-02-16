FROM openshift3/jenkins-slave-base-rhel7:latest

USER root

ENV INSTALL_PKGS="gdb valgrind cppunit vim gcc-g++ libstdc++ make automake autoconf OpenIPMI OpenIPMI-libs OpenIPMI-modalias fence-agents-ipmilan freeipmi freeipmi-bmc-watchdog freeipmi-ipmidetectd ipmitool OpenIPMI-devel-2.0.23-2.el7 freeipmi-devel-1.5.7-2.el7"

RUN yum repolist > /dev/null && \
    yum install -y --setopt=tsflags=nodocs \
      --enablerepo=rhel-7-server-extras-rpms \
      $INSTALL_PKGS && \
    rpm -V $INSTALL_PKGS && \
    yum clean all -y && \
    rm -rf /var/cache/yum

USER 1001
