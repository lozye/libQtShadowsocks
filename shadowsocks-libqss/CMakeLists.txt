set(TASK "shadowsocks-libqss")

set(SOURCE
    client.cpp
    main.cpp
    utils.cpp
    )

add_executable(${TASK} ${SOURCE})

target_link_libraries(${TASK} Qt5::Core Qt5::Network ${BOTAN_LIBRARIES} QtShadowsocks)
target_include_directories(${TASK}
    PUBLIC ${BOTAN_INCLUDE_DIRS}
    PUBLIC ${PROJECT_SOURCE_DIR}/lib)

install(TARGETS ${TASK} RUNTIME DESTINATION bin)
