#################################################
############# MAKEFILE FOR L3 BINARY ############
#################################################
include make.inc

PWD=$(shell pwd)
ROOT_DIR=$(PWD)

export ROOT_DIR

OUTPUT       = $(PWD)/bin
LIBLINK      = -lz -lpthread -lm

TARGET       = $(OUTPUT)/output

# Libraries to be linked for creating final object 
L3_LIB_DIR +=  $(ROOT_DIR)/main/lib/libxxmain.a \
				$(ROOT_DIR)/com/lib/libcom.a \
			 


L3_SUBDIRS = \
				$(ROOT_DIR)/main \
				$(ROOT_DIR)/com \
				

#######################################################
############ Rules for building L3 binary #############
#######################################################

all: L3_SUB_MODULES
	$(CC) $(L3_LIB_DIR) -o $(TARGET)
	#cp $(TARGET) $(GNB_ROOT)/gNB_CU/bin
	#cp ./lib/libcucpinterface.so $(GNB_ROOT)/gNB_CU/lib


#######################################################
########## Rules for building L3 sub modules ##########
#######################################################

L3_SUB_MODULES:
	set -e;
	for i in $(L3_SUBDIRS); \
	do                      \
    echo "Compiling $$i";   \
	cd $$i;                 \
    if ! make;              \
    then exit 1;            \
	fi;                     \
    done

	
#######################################################
######### Rules for cleaning objects/libraries ########
#######################################################

clean:
	${RMD} $(TARGET)
	for i in $(L3_SUBDIRS);    \
    do                         \
    echo "Cleaning in $$i";    \
	cd $$i;                    \
	make clean;                \
	done

