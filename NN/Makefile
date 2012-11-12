ROOT_DIR := $(notdir $(CURDIR))
ifndef QCONFIG
QCONFIG=qconfig.mk
endif
include $(QCONFIG)
unexport ROOT_DIR

.PHONY: all clean images

# Expands to a single newline character
define NEWLINE


endef

SUFFIXES := .mk

all: $(if $(wildcard images/*),images)
	@echo done

subdirs:=$(subst /Makefile,,$(wildcard */[Mm]akefile))

clean:
	$(foreach dir,$(subdirs), $(MAKE) -C$(dir) clean $(NEWLINE))

images:
	$(MAKE) -Cimages
