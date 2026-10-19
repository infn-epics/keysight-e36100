TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

# e36100Support: the driver and the state programs, for any IOC to link (the generic
# INFN IOC does, through ibek-support-infn's install.yml)
LIBRARY_IOC += e36100Support
DBD += e36100Support.dbd
INC += e36100Driver.h
e36100Support_SRCS += e36100Driver.cpp
e36100Support_SRCS += e36100RampOn.st
e36100Support_SRCS += e36100SafeOff.st
e36100Support_LIBS += asyn
e36100Support_LIBS += seq pv
e36100Support_LIBS += $(EPICS_BASE_IOC_LIBS)

#=============================
# The example IOC (iocBoot/ioce36100)

PROD_IOC = e36100
DBD += e36100.dbd
e36100_DBD += base.dbd
e36100_DBD += asyn.dbd drvAsynIPPort.dbd drvAsynSerialPort.dbd
e36100_DBD += e36100Support.dbd

e36100_SRCS += e36100_registerRecordDeviceDriver.cpp
e36100_SRCS_DEFAULT += e36100Main.cpp
e36100_SRCS_vxWorks += -nil-

e36100_LIBS += e36100Support
e36100_LIBS += asyn
e36100_LIBS += seq pv
e36100_LIBS += $(EPICS_BASE_IOC_LIBS)

#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE
