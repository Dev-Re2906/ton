set(COMMON_SOURCE
  checksum.h
  errorcode.h 
  status.h
  io.hpp

  errorlog.h
  errorlog.cpp

  global-version.h)


add_library(common STATIC ${COMMON_SOURCE})

target_include_directories(common PUBLIC 
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}> 
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>/.. 
  ${OPENSSL_INCLUDE_DIR}
)
target_link_libraries(common PRIVATE tdutils ton_crypto )
