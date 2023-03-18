CXX = g++
CXX_FLAGS = -pedantic -Wall -Wextra -std=c++20
TARGET_FLAGS = $(CXX_FLAGS) -shared -fPIC

OPT_FLAGS = -Ofast -march=native
DBG_FLAGS = -g3 -Og -ggdb

SRC = $(wildcard ./src/*/impl.cpp)
INCLPATH = ./headers
OBJECTS = $(patsubst ./src/%/impl.cpp,./build/%.o,$(SRC))
TARGET = liblfds.so

.PHONY: release
release: FLAGS = $(OPT_FLAGS)
release: $(TARGET)

.PHONY: debug
debug: FLAGS=$(DBG_FLAGS)
debug: $(TARGET)

$(TARGET): $(OBJECTS)
	$(CXX) -I$(INCLPATH) $(TARGET_FLAGS) $(FLAGS) $^ -o $@
./build/%.o: ./src/%/impl.cpp
	$(CXX) -I$(INCLPATH) $(CXX_FLAGS) $(FLAGS) -c $< -o $@

.PHONY: clean
clean:
	rm -rf $(OBJECTS)
	rm $(TARGET)
