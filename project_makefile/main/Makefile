#######################################################
############# MAKEFILE FOR L3 F1AP MODULE #############
#######################################################
include ${ROOT_DIR}/make.inc

SRC_DIR    = $(PWD)/src
OUTPUT       = $(PWD)/lib

TARGET       = $(OUTPUT)/libxxmain.a

SRCS         = $(wildcard $(SRC_DIR)/*.c)

OBJECTS      = $(patsubst %.c,$(OUTPUT)/%.o,$(notdir $(SRCS)))

INC        = -I$(PWD)/inc  \
			-I$(ROOT_DIR)/com/inc
			 
#######################################################
################# Rules for building ##################
#######################################################

all: create_dir $(TARGET)

create_dir: 
		${MKD} $(OUTPUT)
		${MKD} $(ROOT_DIR)/bin/
		${MKD} $(ROOT_DIR)/lib/

$(TARGET): $(OBJECTS) 
	       $(AR) $(RVS) $(TARGET) $(OBJECTS)
		   cp -f $(TARGET) $(ROOT_DIR)/lib/

$(OUTPUT)/%.o : $(SRC_DIR)/%.c 
				$(CC) $(CFLAGS) $(SCTPFLAGS) -c $< -o $@ $(INC) 


#######################################################
################# Rules for cleanup ###################
#######################################################

clean:
	rm -f $(OBJECTS)
	rm -f $(TARGET)
