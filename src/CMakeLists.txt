# zectl Source ------------------------------------------------------------------

set(SOURCE_FILES
        zectl.c zectl.h
        zectl_list.c
        zectl_create.c
        zectl_activate.c
        zectl_destroy.c
        zectl_mount.c
        zectl_unmount.c
        zectl_rename.c
        zectl_set.c
        zectl_snapshot.c
        zectl_get.c
        zectl_util.h zectl_util.c)

list(APPEND ZE_LINK_LIBRARIES libze)
#list(APPEND ZE_LINK_LIBRARIES libze libze_plugin_systemdboot)

add_executable(zectl ${SOURCE_FILES})

target_link_libraries(zectl ${ZE_LINK_LIBRARIES})

install(TARGETS zectl DESTINATION ${CMAKE_INSTALL_PREFIX}/bin)
