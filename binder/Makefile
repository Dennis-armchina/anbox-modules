ccflags-y += -I$(src) -Wno-int-conversion -DCONFIG_ANDROID_BINDER_DEVICES="\"binder\""
obj-m := binder_linux.o
binder_linux-y := deps.o binder.o

KERNELRELEASE = 4.15.0-112-generic
KERNEL_SRC ?= /lib/modules/4.15.0-112-generic/build

all:
	$(MAKE) -C $(KERNEL_SRC) V=0 M=$$PWD

install:
	cp binder_linux.ko $(DESTDIR)/

clean:
	rm -rf deps.h *.o *.ko *.mod.c *.symvers *.order .*.cmd .tmp_versions
