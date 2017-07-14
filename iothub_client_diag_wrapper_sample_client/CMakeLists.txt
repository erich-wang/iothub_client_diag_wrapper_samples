#Copyright (c) Microsoft. All rights reserved.
#Licensed under the MIT license. See LICENSE file in the project root for full license information.

#this is CMakeLists.txt for iothub_client_diag_wrapper_sample_client

cmake_minimum_required(VERSION 2.8.11)

if (CMAKE_C_COMPILER_ID STREQUAL "GNU")
  set (CMAKE_C_FLAGS "--std=c99 -g ${CMAKE_C_FLAGS}")
endif()

include_directories("/usr/include/azureiot"
                    "/usr/include/azureiot/inc/")

set(iothub_client_diag_wrapper_sample_client_c_files
    iothub_client_diag_wrapper_sample_client.c
)

set(iothub_client_diag_wrapper_sample_client_h_files
    iothub_client_diag_wrapper_sample_client.h
)


add_executable(iothub_client_diag_wrapper_sample_client ${iothub_client_diag_wrapper_sample_client_c_files} ${iothub_client_diag_wrapper_sample_client_h_files})

target_link_libraries(iothub_client_diag_wrapper_sample_client  
                          serializer
                          iothub_client
                          iothub_client_mqtt_transport
			  iothub_client_diag_wrapper
                          umqtt
                          aziotsharedutil
                          ssl
                          crypto
                          curl
                          pthread
                          m
                          ssl
			  uuid
                          crypto)

