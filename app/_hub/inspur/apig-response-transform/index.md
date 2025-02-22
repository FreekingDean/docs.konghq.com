---
name: Inspur Response Transform
publisher: Inspur
categories:
  - transformations
type: plugin
desc: kong plugin to transform http response from json to xml
description: |
    This plugin transform the response sent by the upstream server on the fly on Kong from json to xml,before returning the response to the client.Because of Nginx's internals, the `Content-Length` header will not be set when transforming a response body.
support_url: https://github.com/kakascx/apig-response-transform/issues
source_url: https://github.com/kakascx/apig-response-transform
license_type: Apache-2.0
license_url: https://github.com/kakascx/apig-response-transform/blob/master/LICENSE 

kong_version_compatibility:
  community_edition:
    compatible:
     - 1.2.x
     - 1.1.x


params:
  name: apig-response-transform 
  api_id: False
  service_id: True
  consumer_id: False
  route_id: True
  protocols: ["http","https"]
  dbless_compatible: 'yes'
  dbless_explanation: It is recommended to use in dbless mode.
  config:
    - name: format
      required: true
      default: xml
      value_in_examples: xml 
      description: |
        Describe the format of the response format.
---
### Installation 
Recommended: 
 
```bash 
$ git clone https://github.com/kakascx/apig-response-transform /opt/kong/plugins 
$ cd /opt/kong/plugins/apig-response-transform 
$ luarocks make 
``` 
