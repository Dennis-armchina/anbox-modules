ccflags-y += -I$(src) -Wno-error=implicit-int -Wno-int-conversion
obj-m := ashmem_linux.o
ashmem_linux-y := deps.o ashmem.o

KERNELRELEASE = 4.15.0-112-generic
KERNEL_SRC ?= /lib/modules/4.15.0-112-generic/build
VZ=	$(shell uname -r | grep vz)
ifneq ($(VZ),)
ccflags-y += -DVZKERNEL
endif

all:
	$(MAKE) -C $(KERNEL_SRC) V=0 M=$$PWD

install:
	cp ashmem_linux.ko $(DESTDIR)/

clean:
	rm -rf deps.h *.o *.ko *.mod.c *.symvers *.order .*.cmd .tmp_versions
