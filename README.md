# sreproject for Ansible playbook on `httpd`

A simple Ansible role for installing and configuring the Apache web server for RHEL/CentOS 7.
- Install the necessary packages;
- Maintain the main configuration file;
- Maintain the configuration file for `mod_ssl`.
- This Configure http redirect to https
- This create an automated test verifying the web server is listening on port 443

HTTPS/TLS is enabled, by default using the standard self-signed certificate. You can provide your own certificate by setting the appropriate role variables.

## Requirements

- The firewall settings are included as a role.
- Please start iptables-service before testing web domain url

## Polaybook Variables

Applying this playbook role will result in a configuration equivalent to installing a secure host web server. 

| Variable                        | Default                                                                                 
| :---                            | :---                                                                                                                      
| `httpd_AccessLog_ssl`           | logs/ssl_access_log                                                                                                             
| `httpd_DocumentRoot`            | '/var/www/html'                                                                                                                   
| `httpd_ErrorLog_ssl`            | logs/ssl_error_log                                                                                                                
| `httpd_ErrorLog`                | logs/error_log                                                                                                                    
| `httpd_Listen_ssl`              | 443                                                                                                                               
| `httpd_Listen`                  | 80                                                                                                                                
| `httpd_LogLevel_ssl`            | warn                                                                                                                              
| `httpd_LogLevel`                | warn                                                                                                                              
| `httpd_SSLCACertificateFile`    | -                                                                                                                                 
| `httpd_SSLCertificateChainFile` | -                                                                                                                                 
| `httpd_SSLCertificateFile`      | /etc/pki/tls/certs/localhost.crt                                                                                                  
| `httpd_SSLCertificateKeyFile`   | /etc/pki/tls/private/localhost.key                                                                                              
| `httpd_SSLCipherSuite`          | See [default variables](defaults/main.yml)                                                                                       
| `httpd_SSLHonorCipherOrder`     | 'on'                                                                                                                             
| `httpd_SSLProtocol`             | 'all -SSLv3 -TLSv1'                                                                                                               
| `httpd_ServerAdmin`             | ansadm@localhost                                                                                                                  
| 'httpd_ServerRoot'              | '/etc/httpd'                                                                                                                      
| 'httpd_ServerTokens'            | web                                        
| 'httpd_DirectoryIndex'          | homepage.html                      

## Dependencies

No dependencies.

## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section.

Pull requests are also very welcome. 
