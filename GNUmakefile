include $(GNUSTEP_MAKEFILES)/common.make

SUBPROJECTS = ToolSource

ifneq (,$(filter clean distclean,$(MAKECMDGOALS)))
  testsource ?= yes
endif

ifeq ($(test), yes)
  testsource ?= yes
endif

ifeq ($(testsource), yes)
  SUBPROJECTS += \
	TestSource/TestFramework \
	TestSource/TestBundle \
	TestSource/TestUnitKit
endif

FRAMEWORK_NAME = UnitKit

UnitKit_VERSION = 1.3

UnitKit_OBJCFLAGS = -std=c99 
UnitKit_LIBRARIES_DEPEND_UPON = $(FND_LIBS) $(OBJC_LIBS) $(SYSTEM_LIBS)

OTHER_HEADER_DIRS = FrameworkSource

UnitKit_HEADER_FILES_DIR = UnitKit
UnitKit_HEADER_FILES = $(notdir $(wildcard UnitKit/*.h))

UnitKit_OBJC_FILES = $(wildcard FrameworkSource/*.m)

UnitKit_LOCALIZED_RESOURCE_FILES = UKTestHandler.strings
UnitKit_LANGUAGES = FrameworkSource/English

# Documentation

UnitKitDoc_DOC_FILES = \
	FrameworkSource/UKTest.h \
	FrameworkSource/UKTestHandler.h \
	FrameworkSource/UKRunner.h

UnitKitDoc_MENU_TEMPLATE_FILE = Documentation/Templates/menu.html

UnitKitDoc_README_FILE = README.md
UnitKitDoc_INSTALL_FILES = INSTALL.Cocoa.md INSTALL.GNUstep.md
UnitKitDoc_NEWS_FILE = NEWS.md

include $(GNUSTEP_MAKEFILES)/framework.make
-include ../../etoile.make
-include ../../documentation.make
include $(GNUSTEP_MAKEFILES)/aggregate.make
