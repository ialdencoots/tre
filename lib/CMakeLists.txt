file(GLOB PRIVATE_HEADERS CONFIGURE_DEPENDS "${PROJECT_SOURCE_DIR}/lib/*.h")
file(GLOB PUBLIC_HEADERS CONFIGURE_DEPENDS "${PROJECT_SOURCE_DIR}/local_includes/*.h")
file(GLOB SOURCE_FILES ${PROJECT_SOURCE_DIR}/lib/*.c)

# Make an automatic library - will be static or dynamic based on user setting
add_library(tre ${SOURCE_FILES} ${PUBLIC_HEADERS} ${PRIVATE_HEADERS})

# We need this directory, and users of our library will need it too
target_include_directories(tre PUBLIC ../local_includes)

# All users of this library will need at least C11
target_compile_features(tre PUBLIC c_std_11)

# IDEs should put the headers in a nice place
source_group(
    TREE "${PROJECT_SOURCE_DIR}/local_includes"
    PREFIX "Header Files"
    FILES ${PUBLIC_HEADERS})

source_group(
    TREE "${PROJECT_SOURCE_DIR}/lib"
    PREFIX "Header Files"
    FILES ${PRIVATE_HEADERS})
