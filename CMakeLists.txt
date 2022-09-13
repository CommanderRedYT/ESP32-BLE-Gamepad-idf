set(headers
    src/BleConnectionStatus.h
    src/BleGamepad.h
    src/BleGamepadConfiguration.h
    src/utils.h
)

set(sources
    src/BleConnectionStatus.cpp
    src/BleGamepad.cpp
    src/BleGamepadConfiguration.cpp
)

set(dependencies
    esp-nimble-cpp expected
)

idf_component_register(
    INCLUDE_DIRS
        src
    SRCS
        ${headers}
        ${sources}
    REQUIRES
        ${dependencies}
)

target_compile_options(${COMPONENT_TARGET}
    PRIVATE
        -fstack-reuse=all
        -fstack-protector-all
)
