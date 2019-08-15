.PHONY: all pack

VERSION=5.4.0
RELEASE=casa-release-${VERSION}-70.el7

all: pack

${RELEASE}.tar.gz:
	wget https://casa.nrao.edu/download/distro/casa/release/el7/${RELEASE}.tar.gz

${RELEASE}/: ${RELEASE}.tar.gz
	tar zxmvf ${RELEASE}.tar.gz

casa-alma-pipeline-${VERSION}/: ${RELEASE}/
	cp -a ${RELEASE}/ casa-alma-pipeline-${VERSION}/

casa-alma-pipeline-${VERSION}.tar.xz: casa-alma-pipeline-${VERSION}/
	tar Jcvf casa-alma-pipeline-${VERSION}.tar.xz casa-alma-pipeline-${VERSION}/

pack: casa-alma-pipeline-${VERSION}.tar.xz
	echo "done"
