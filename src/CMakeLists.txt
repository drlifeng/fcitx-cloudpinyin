include_directories(
  ${PROJECT_BINARY_DIR}
  ${CMAKE_CURRENT_SOURCE_DIR}
  ${CURL_INCLUDE_DIRS}
  ${PTHREAD_INCLUDE_DIR}
  ${FCITX4_FCITX_INCLUDE_DIRS}
  ${FCITX4_FCITX_CONFIG_INCLUDE_DIRS}
  ${FCITX4_FCITX_UTILS_INCLUDE_DIRS}
  ${LIBINTL_INCLUDE_DIR}
  )

link_directories(
  ${CURL_LIBRARY_DIRS}
  )

set(FCITX_CLOUDPINYIN_SRCS
  cloudpinyin.c
  cloudpinyinconifg.c
  fetch.c
  parse.c
  )

fcitx_add_addon_full(cloudpinyin DESC
  SOURCES ${FCITX_CLOUDPINYIN_SRCS}
  LINK_LIBS ${CURL_LIBRARIES}
  ${LIBINTL_LIBRARIES}
  ${PTHREAD_LIBRARIES})
