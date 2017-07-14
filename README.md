# E2E Diagnostics Layered Azure IoT SDK Samples On Raspberry Pi
Beside the steps at [Use apt-get to create a C device client project on Ubuntu](https://github.com/erich-wang/azure-iot-sdk-c/blob/master/doc/ubuntu_apt-get_sample_setup.md), you need to:
1. Copy package/inc/iothub_client_diag_wrapper.h to /usr/include/azureiot/
2. Copy package/lib/armhf/libiothub_client_diag_wrapper.a to /usr/lib/
3. Include "iothub_client_diag_wrapper.h" in your project, and add link library to iothub_client_diag_wrapper
4. Build the sample code
```
mkdir cmake
cd cmake
cmake ..
make
```
5. Run samples
- [iothub_client_diag_wrapper_sample_server](./iothub_client_diag_wrapper_sample_server) Diagnostics sampling switch and percentage are controlled by device twin configuration at server end. The binary is located at cmake/iothub_client_diag_wrapper_sample_server/.

```  
  Usage:
  ./iothub_client_diag_wrapper_sample_server <Device Connection String> ["yes"|"no"]
  The first parameter is device connection string
  The second parameter means whether simulating invalid messages, this parameter is optional and has default value "no" 
  ```

- [iothub_client_diag_wrapper_sample_client](./iothub_client_diag_wrapper_sample_client) Diagnostics sampling percentage is using parameter value when calling **IoTHubClient_LL_CreateFromConnectionString_WithDiagnostics**. The binary is located at cmake/iothub_client_diag_wrapper_sample_client/.
```
Usage: ./iothub_client_diag_wrapper_sample_client <Device Connection String> ["yes"|"no"]
```
