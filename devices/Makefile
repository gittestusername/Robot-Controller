PREFIX_XENO := /usr/xenomai
EXECUTABLE := dev-task
LIBDIR := ${PREFIX_XENO}/lib
LIBS := native xenomai pthread_rt ethercat
INCLUDES := ../include ${PREFIX_XENO}/include /include
SRCDIR :=

CC = g++
CXX = g++
CFLAGS := -std=c++11
CPPFLAGS += $(CFALGS) $(addprefix -I,$(INCLUDES))

RM-F := rm -f

SRCS := $(wildcard *.cc) $(wildcard $(addsuffix /*.cc, $(SRCDIR)))
OBJS := $(patsubst %.cc,%.o,$(SRCS))

.PHONY : all clean rebuild


all: $(EXECUTABLE)

clean: 
	@$(RM-F) $(OBJS)

rebuild:
	clean all

$(EXECUTABLE) : $(OBJS)
	$(CXX) -o $(EXECUTABLE) $(OBJS) $(addprefix -L,$(LIBDIR)) $(addprefix -l,$(LIBS))