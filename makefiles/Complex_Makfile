# Compiler and Flags
CC = gcc
CFLAGS = -Wall -Wextra -std=c11
LDFLAGS =

# Project directories
APP = my_program
SRCDIR = src
OBJDIR = obj
BINDIR = bin
INC = include

# Find all .c files in the source directory and list corresponding .o files in obj directory
SOURCES := $(wildcard $(SRCDIR)/*.c)
OBJECTS := $(patsubst $(SRCDIR)/%.c, $(OBJDIR)/%.o, $(SOURCES))

# Add include directory to CFLAGS
CFLAGS += -I$(INC)

# Default APP
all: $(BINDIR)/$(APP)

# Link object files into the final executable
$(BINDIR)/$(APP): $(OBJECTS)
	@mkdir -p $(BINDIR)
	$(CC) $(OBJECTS) -o $@ $(LDFLAGS)
	@echo "Build complete: $@"

# Compile source files into object files
$(OBJDIR)/%.o: $(SRCDIR)/%.c
	@mkdir -p $(OBJDIR)
	$(CC) $(CFLAGS) -c $< -o $@

# Clean up build files
clean:
	rm -rf $(OBJDIR) $(BINDIR)

# Run the executable
run: all
	./$(BINDIR)/$(APP)

# Phony APPs
.PHONY: all clean run
