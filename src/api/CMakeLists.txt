# Copyright (c) Monetas AG, 2014

set(cxx-sources
  OpenTransactions.cpp
  ot_commands_ot.cpp
  ot_made_easy_ot.cpp
  OT_ME.cpp
  ot_opentxs_ot.cpp
  ot_otapi_ot.cpp
  ot_utility_ot.cpp
  OTAPI.cpp
  OTAPI_Exec.cpp
  OTClient.cpp
  OTMeChai.cpp
  OTMeCpp.cpp
  OTRecord.cpp
  OTRecordList.cpp
  OTServerConnection.cpp
)

set(dependency_include_dir
  ${CMAKE_CURRENT_SOURCE_DIR}/../../deps/
)

include_directories(SYSTEM
  ${dependency_include_dir}
  ${dependency_include_dir}/ChaiScript/include
)

include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}/../../include/
  ${CMAKE_CURRENT_SOURCE_DIR}/../../include/opentxs
  ${CMAKE_CURRENT_SOURCE_DIR}/../../include/opentxs/core
  ${CMAKE_CURRENT_SOURCE_DIR}/../../include/opentxs/ext
  ${CMAKE_CURRENT_SOURCE_DIR}/../../include/opentxs/api
)

link_directories(
  ${CMAKE_BINARY_DIR}/lib
)

add_library(opentxs-api
  ${cxx-sources}
)

target_link_libraries(opentxs-api opentxs-ext opentxs-core)