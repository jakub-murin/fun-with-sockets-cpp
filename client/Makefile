CXX = g++
CFLAGS = -g -Wall
 
TARGET_EXEC ?= client

BUILD_DIR ?= ./build
SRC_DIRS ?= ./src

SRCS := $(shell find $(SRC_DIRS) -name '*.cpp' -or -name '*.c' -or -name '*.s')
OBJS := $(SRCS:%=$(BUILD_DIR)/%.o)
#DEPS := $(OBJS:.o=.d)
 
$(BUILD_DIR)/$(TARGET_EXEC): $(OBJS)
	$(CXX) $(OBJS) -o $@ $(LDFLAGS)

$(BUILD_DIR)/%.cpp.o: %.cpp
	$(MKDIR_P) $(dir $@)
	$(CXX) $(CFLAGS) -c $< -o $@

clean:
	$(RM) -r $(BUILD_DIR)

MKDIR_P ?= mkdir -p

.PHONY: clean
