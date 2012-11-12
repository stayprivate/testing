ROOT_DIR := $(notdir $(CURDIR))
ifndef QCONFIG
QCONFIG=qconfig.mk
endif
include $(QCONFIG)

HOST_MKIFS := $(QNX_HOST)/usr/bin/mkifs

SUFFIXES := .build .ifs .raw

.PHONY: all clean

all: ifs-NN.raw

clean: 
	$(RM_HOST) ifs-NN.raw

ifs-NN.raw: ../src/build
	$(HOST_MKIFS)  -v $(MKIFSFLAGS) $^ $@
