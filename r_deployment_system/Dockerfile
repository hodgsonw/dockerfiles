FROM centos:7
MAINTAINER Wilson Hodgson <wilson.hodgson@canada.ca>

#RUN yum install -y git make rpm-build && \
#  git clone --depth 1 https://github.com/AAFC-BICoE/MBB-Bio-Roll.git /home/MBB-Bio-Roll

## extend-compute pkgs as of Feb 1 2019
RUN yum install -y \
emacs \
evince \
firefox \
gedit \
gnuplot \
nano \
vim-enhanced \
bzr \
cvs \
git-all \
mercurial \
rcs \
subversion \
subversion-devel \
autoconf \
automake \
binutils \
bison \
flex \
gcc \
gcc-c++ \
gettext \
libtool \
make \
patch \
redhat-rpm-config \
pkgconfig \
rpm-build \
rpm-sign \
byacc \
cscope \
ctags \
diffstat \
doxygen \
elfutils \
gcc-fortran \
indent \
intltool \
patchutils \
swig \
systemtap \
ElectricFence \
ant \
babel \
chrpath \
cmake \
compat-gcc-44 \
compat-gcc-44-c++ \
dejagnu \
expect \
gcc-gnat \
gcc-objc \
gcc-objc++ \
imake \
javapackages-tools \
nasm \
perltidy \
rpmdevtools \
rpmlint \
golang \
java-1.6.0-openjdk \
java-1.6.0-openjdk-devel \
java-1.7.0-openjdk \
java-1.7.0-openjdk-devel \
java-1.8.0-openjdk \
java-1.8.0-openjdk-devel \
maven \
maven-release \
maven-source \
maven-site-plugin \
maven-surefire-plugin \
maven-war-plugin \
ruby \
ruby-devel \
rubygems \
qt3-designer \
tcl \
tcl-devel \
texlive \
texinfo \
texinfo-tex \
tk \
tk-devel \
GraphicsMagick \
GraphicsMagick-c++ \
ImageMagick \
ImageMagick-devel \
ImageMagick-perl \
OpenEXR \
OpenEXR-devel \
bzip2-devel \
blas \
blas-devel \
blas-static \
boost \
boost-devel \
boost-static \
cairo \
cairo-devel \
expat \
expat-devel \
gd-devel \
ghostscript \
ghostscript-devel \
glibc \
glibc-devel \
glibc-static \
glib2 \
glib2-devel \
glib2-static \
gmp \
gmp-devel \
gsl \
gsl-static \
gsl-devel \
ilmbase-devel \
ilmbase \
jasper \
jasper-libs \
jasper-devel \
lapack \
lapack-devel \
libX11 \
libX11-devel \
libcurl \
libcurl-devel \
libdrm \
libdrm-devel \
libjpeg-turbo \
libjpeg-turbo-devel \
libidn \
libidn-devel \
libmpc \
libmpc-devel \
libstdc++ \
libstdc++-devel \
libstdc++-static \
libtiff \
libtiff-devel \
libwmf \
libwmf-devel \
libwmf-lite \
libpng \
libpng-devel \
libxml2 \
libxml2-devel \
libxml2-python \
libxml2-static \
libxslt \
libxslt-devel \
libXmu \
libXmu-devel \
libXp \
libXp-devel \
libXpm \
libXpm-devel \
lzo-devel \
mariadb-devel \
mariadb-lib \
mesa-libEGL \
mesa-libEGL-devel \
mesa-libGL \
mesa-libGL-devel \
mesa-libGLES \
mesa-libGLES-devel \
mesa-libGLU \
mesa-libGLU-devel \
mesa-libOSMesa \
mesa-libOSMesa-devel \
mesa-libgbm \
mesa-libgbm-devel \
mesa-libglapi \
mesa-libglapi-devel \
mpfr \
mpfr-devel \
ncurses-libs \
ncurses-devel \
openssl-libs \
openssl-devel \
pcre \
pcre-devel \
pcre-static \
postgresql \
postgresql-devel \
qt \
qt-devel \
qt3 \
qt3-devel \
qt3-MySQL \
qt3-PostgreSQL \
qt-xll \
readline \
readline-devel \
readline-static \
sqlite \
sqlite-devel \
svg \
tbb \
tbb-devel \
zlib \
zlib-devel \
zlib-static \
bzip2 \
gzip \
lz4 \
lzo \
xz \
zip \
samba-client \
samba-winbind \
samba-winbind-clients \
iozone \
iperf3 

COPY . /home/MBB-Bio-Roll/RPMS/

RUN yum install -y /home/MBB-Bio-Roll/RPMS/opt-libcurl-7.61.1-1.x86_64.rpm && \
    yum install -y /home/MBB-Bio-Roll/RPMS/opt-curl-7.61.1-1.x86_64.rpm && \
    yum install -y /home/MBB-Bio-Roll/RPMS/opt-R-core-3.5.1-2.x86_64.rpm && \
    yum install -y /home/MBB-Bio-Roll/RPMS/opt-R-devel-3.5.1-2.x86_64.rpm    

#groff \
#stunnel \
#openssh-server

##add groff, stunnel, and openssh-server dependencies

## rpmbuild has to have fascist build policies turned of ###!!!!!!!!!!!!!
#
#
### Make opt-libcurl dependencies
#RUN cd /home/MBB-Bio-Roll/mbb-bio-deps/curl/ && \
#       make package && \
#       yum install -y RPMS/x86_64/*

### Make Bio-tools
#RUN cd /home/MBB-Bio-Roll/mbb-bio/R3/ && \
#       make package && \
#       yum install -y RPMS/x86_64/*


## shallow clone MBB-Bio-Roll from AAFC github
## build and install R3 RPMS 'devel' and 'core'
## then install listed packages from extend-compute.xml
## 
## at this point we match the R environment on the biocluster

## TODO
## from here we need to install dependencies specific to the R-package-management project
## this includes devtools

## ADD devtools_2.0.1.tar.gz /opt/packages
## WORKDIR /opt/packages

## RUN yum -y install epel-release && \
##     yum -y install R
## RUN R CMD INSTALL devtools_2.0.1.tar.gz

CMD /bin/bash
