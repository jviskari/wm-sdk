# You can add more sources here and libraries if needed
SRCS +=
INCLUDES +=
LIBS +=
LDFLAGS +=

# Example:
# SRCS += $(SRCS_PATH)my_driver.c
# LIBS += my_lib.a
# include math.h lib
# LDFLAGS += -lm

# Define default network settings
CFLAGS += -DNETWORK_ADDRESS=$(default_network_address)
CFLAGS += -DNETWORK_CHANNEL=$(default_network_channel)
CFLAGS += -DSTORAGE_TYPE=$(storage)

# Use App Scheduler and configure it
APP_SCHEDULER=yes
CFLAGS += -DAPP_SCHEDULER_MAX_TASKS=2
CFLAGS += -DAPP_SCHEDULER_MAX_EXEC_TIME_US=500

# Enable shared data library (needed by provisioning library)
SHARED_DATA=yes

# Enable CBOR library (needed by provisioning library)
TINY_CBOR=yes

# Enable software AES (needed by provisioning library)
SW_AES=yes

# Enable Provisioning library
PROVISIONING=yes

# HAL button functions
HAL_BUTTON=yes

# Uncomment to enable debug prints
# APP_PRINTING=yes

ifeq ($(storage),chipid)
	SRCS += $(SRCS_PATH)storage_chipid.c
else ifeq ($(storage),memarea)
	SRCS += $(SRCS_PATH)storage_memarea.c
else
    $(error Select one storage method.)
endif

# Generic util functions are needed (api.c)
include $(UTIL_PATH)makefile
