# Minimum version CMake
cmake_minimum_required(VERSION 3.10)

# Pro name & set std language
project(42 LANGUAGES C CXX)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_C_STANDARD 99)
# Path for exec file generation
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/../)

# Include path for headers
include_directories(
    Include
    Kit/Include
)

# Src file list
set(SOURCES
    Source/42main.c
    Kit/Source/dcmkit.c
    Kit/Source/envkit.c
    Kit/Source/fswkit.c
    Kit/Source/meshkit.c
    Kit/Source/iokit.c
    Kit/Source/mathkit.c
    Kit/Source/msis86kit.c
    Kit/Source/nrlmsise00kit.c
    Kit/Source/orbkit.c
    Kit/Source/sigkit.c
    Kit/Source/sphkit.c
    Kit/Source/timekit.c
    Kit/Source/iokit.c
    Source/42actuators.c
    Source/42environs.c
    Source/42ephem.c
    Source/42ipc.c
    Source/42perturb.c
    Source/42sensors.c
    Source/42jitter.c
    Source/42joints.c
    Source/42optics.c
    Source/AcApp.c
    Source/42dynamics.c
    Source/42fsw.c
    Source/42cmd.c
    Source/AutoCode/TxRxIPC.c
    Source/AutoCode/WriteAcToCsv.c
    Source/AutoCode/WriteScToCsv.c
    Source/42init.c
    Source/42actuators.c
    Source/42fsw.c
    Source/42exec.c
    Source/42report.c
)

# Exec file create
add_executable(${PROJECT_NAME} ${SOURCES})

find_package(MPI)
find_library(WINPTHREADS_LIB
    NAMES pthread
    REQUIRED
)
target_link_libraries(${PROJECT_NAME} PRIVATE MPI::MPI_C ${WINPTHREADS_LIB})

# Setting for Windows
if(WIN32)
    target_link_libraries(${PROJECT_NAME} PRIVATE ws2_32)
endif()

if(UNIX)
    target_link_libraries(${PROJECT_NAME} m dl rt pthread)
endif()
