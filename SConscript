from building import *
import os

# Import environment variables
Import('env')

# Get the current working directory
cwd = GetCurrentDir()

# Initialize include paths and source files list
path = [os.path.join(cwd, 'device')]
src = [os.path.join(cwd, 'device', 'system_n32h49x.c')]

# Select chip's startup file
if rtconfig.PLATFORM in ['gcc', 'llvm-arm']:
    src = [os.path.join(cwd, 'device', 'startup', 'startup_n32h49x_gcc.s')]
elif rtconfig.PLATFORM in ['armcc', 'armclang']:
    src = [os.path.join(cwd, 'device', 'startup', 'startup_n32h49x.s')]
elif rtconfig.PLATFORM in ['iccarm']:
    src = [os.path.join(cwd, 'device', 'startup', 'startup_n32h49x_EWARM.s')]

# Define the build group
group = DefineGroup('Libraries-CMSIS', src, depend=['PKG_USING_N32H49X_CMSIS_DRIVER'], CPPPATH=path)

# Return the build group
Return('group')
