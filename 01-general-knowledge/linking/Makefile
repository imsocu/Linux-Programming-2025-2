
CUR_DIR := .
BIN_DIR := $(CUR_DIR)/bin
INC_DIR := $(CUR_DIR)/inc
OBJ_DIR := $(CUR_DIR)/obj
SRC_DIR := $(CUR_DIR)/src
LIB_DIR := $(CUR_DIR)/lib
LIB_STATIC_DIR := $(LIB_DIR)/static
LIB_SHARED_DIR := $(LIB_DIR)/shared

C_FLAGS = -I $(INC_DIR)

# Create the object files for the static library (without -fPIC)
#
create_objs_static:
	gcc -c	$(SRC_DIR)/helloHieu.c   -o $(OBJ_DIR)/helloHieu.o -I $(INC_DIR)
	gcc -c	$(SRC_DIR)/helloWorld.c   -o $(OBJ_DIR)/helloWorld.o -I $(INC_DIR)
	gcc -c	$(SRC_DIR)/main.c   -o $(OBJ_DIR)/main.o -I $(INC_DIR)

# object files for shared libraries need to be compiled as position independent
# code (-fPIC) because they are mapped to any position in the address space.
#
create_objs_shared:
	gcc -c -fPIC $(SRC_DIR)/helloHieu.c   -o $(OBJ_DIR)/helloHieu.o -I $(INC_DIR)
	gcc -c -fPIC $(SRC_DIR)/helloWorld.c   -o $(OBJ_DIR)/helloWorld.o -I $(INC_DIR)
	gcc -c -fPIC $(SRC_DIR)/main.c   -o $(OBJ_DIR)/main.o -I $(INC_DIR)

create_lib_static:
	ar rcs $(LIB_STATIC_DIR)/libhello.a $(OBJ_DIR)/helloHieu.o $(OBJ_DIR)/helloWorld.o
	
create_lib_shared:
	gcc -shared $(OBJ_DIR)/helloHieu.o $(OBJ_DIR)/helloWorld.o -o $(LIB_SHARED_DIR)/libhello.so

# library shared (.so) and obj shard (.0) >> make all
all: create_objs_shared create_lib_shared
	gcc  $(OBJ_DIR)/main.o -L$(LIB_SHARED_DIR) -lhello -o $(BIN_DIR)/use-shared-library

# library static (.a) and obj static (.0) >> make all2
all2: create_objs_static create_lib_static
	gcc  $(OBJ_DIR)/main.o -L$(LIB_STATIC_DIR) -lhello -o $(BIN_DIR)/use-static-library

#clean cua shared
clean:
	rm -rf $(OBJ_DIR)/*.o
	rm -rf $(LIB_SHARED_DIR)/*.so
	rm -rf $(BIN_DIR)/use-shared-library

#clean cua static
clean2:
	rm -rf $(OBJ_DIR)/*.o
	rm -rf $(LIB_STATIC_DIR)/*.a
	rm -rf $(BIN_DIR)/use-static-library
