FILE(GLOB_RECURSE sqlite_SOURCES "*.c")
                                                                                
ADD_LIBRARY(sqlite_static STATIC ${sqlite_SOURCES})
SET_TARGET_PROPERTIES(sqlite_static PROPERTIES OUTPUT_NAME sqlite)
TARGET_LINK_LIBRARIES(sqlite_static)
INSTALL(TARGETS sqlite_static DESTINATION lib)

IF(ENABLE_SHARED_LIBS)
  ADD_LIBRARY(sqlite_shared SHARED ${sqlite_SOURCES})
  SET_TARGET_PROPERTIES(sqlite_shared PROPERTIES OUTPUT_NAME sqlite)
  TARGET_LINK_LIBRARIES(sqlite_shared)
  INSTALL(TARGETS sqlite_shared DESTINATION lib)
ENDIF()
