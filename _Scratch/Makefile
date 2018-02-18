# vim: set ts=4 sw=4 ft=sh:
## Module 3 Chapter 5 Program
## Ashton S. Hellwig
## Feb 09 2018
## CSC160
##

# --- Variables ---
# Directories
SRC = src
TGT = obj
INCLUDES = -Iinclude
DBGOUT = target/debug
UDOCDIR = DOC/assigned
# Compiler
CXX = g++
CXXFLAGSDBG = -Wall -std=c++17 -g -ggdb $(INCLUDES)
SOURCES = $(wildcard $(SRC)/*.cpp)
DBGOBJS = $(addprefix $(TGT)/debug/, $(notdir $(SOURCES:.cpp=.o)))


# --- Rules ---

# All
## Build
all: debug
## Removes object files
clean: clean-dbg

# Debug
## Run
run-debug: debug
	$(DBGOUT)/Chapter5-Debug.bin
## Build
debug: $(TGT)/debug/Chapter5-DBG
$(TGT)/debug/%.o: $(SRC)/%.cpp
	$(CXX) $(CXXFLAGSDBG) -c $< -o $@
$(TGT)/debug/Chapter5-DBG: $(DBGOBJS)
	$(CXX) $(LDFLAGS) $(DBGOBJS) -o $(DBGOUT)/Chapter5-Debug.bin
## Removes Object Files
clean-dbg:
	rm -rf $(TGT)/debug/*.o $(DBGOUT)/*.bin
