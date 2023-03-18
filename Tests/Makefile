CXX = g++
CXX_FLAGS = -pedantic -Wall -Wextra -std=c++20
LD_FLAGS = -llfds

OPT_FLAGS = -Ofast -march=native
DBG_FLAGS = -g3 -Og -ggdb

SRC = $(wildcard ./src/*.cpp)
INCLPATH = ./../LFDS/headers
LDPATH = ./../LFDS
TARGETS = $(patsubst ./src/%.cpp,./bin/%,$(SRC))

.PHONY: release
release: CXX_FLAGS += $(OPT_FLAGS)
release: $(TARGETS)

.PHONY: debug
debug: CXX_FLAGS += $(DBG_FLAGS)
debug: $(TARGETS)

./bin/%: ./src/%.cpp
	$(CXX) -I$(INCLPATH) -L$(LDPATH) $(CXX_FLAGS) $^ -o $@ $(LD_FLAGS)

.PHONY: clean
clean:
	rm $(TARGETS)
