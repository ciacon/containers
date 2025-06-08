FROM fedora:42

ARG VERSION=1.4.1 # renovate: datasource=github-releases depName=borgbackup/borg

RUN echo 'install_weak_deps=False' >> /etc/dnf/dnf.conf \
    && echo 'assumeyes=True' >> /etc/dnf/dnf.conf \
    && sed -i 's/enabled=1/enabled=0/g' /etc/yum.repos.d/fedora-cisco-openh264.repo \
    && dnf --refresh upgrade \
    && dnf install -y borgbackup-${VERSION} \
    && dnf clean all

ENV LANG=en_US.UTF-8
