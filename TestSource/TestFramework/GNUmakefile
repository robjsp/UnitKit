include $(GNUSTEP_MAKEFILES)/common.make

# We reset PROJECT_DIR provided by etoile.make to match the subproject since 
# etoile.make doesn't detect and handle such embedded project (this ensures 
# the headers and framework get exported in the Build directory and can be 
# found by TestBundle)
PROJECT_DIR = $(CURDIR)
PRINT_PROJECT_NAME = NO

FRAMEWORK_NAME = TestFramework
# We declare PROJECT_NAME to export the dependencies (see etoile.make)
PROJECT_NAME = $(FRAMEWORK_NAME)

$(FRAMEWORK_NAME)_LIBRARIES_DEPEND_UPON = -lUnitKit $(FND_LIBS)

$(FRAMEWORK_NAME)_HEADER_FILES = TestClass.h

$(FRAMEWORK_NAME)_OBJC_FILES = TestClass.m

include ../../compilerflags.preamble

include $(GNUSTEP_MAKEFILES)/framework.make
-include ../../../../etoile.make
-include ../../etoile.make
