# Certificate Authentication

!!! Attention
    The official support end-of-life (EOL) date for Gluu Server 2.4.4 is December 31, 2018. Starting January 1, 2019, no further security updates or bug-fixes will be provided for Gluu Server 2.X. We strongly recommend [upgrading](https://gluu.org/docs/ce/upgrade/) to the newest version.

The image below contains the design diagram for this module.

![cert-design](../img/admin-guide/multi-factor/cert-design.jpg)

The script has a few properties:

|       Property        |Description|   Allowed Values                  |example|
|-------|--------------|------------|-----------------|
|chain_cert_file_path   |mandatory property pointing to certificate chains in [pem][pem] format |file path| /etc/certs/chain_cert.pem   |
|map_user_cert          |specifies if the script should map new user to local account           |true/false| true|
|use_generic_validator  |enable/disable specific certificate validation                         |true/false| false|
|use_path_validator     |enable/disable specific certificate validation                         |true/false| true|
|use_oscp_validator|enable/disable specific certificate validation                              |true/false| false|
|use_crl_validator|enable/disable specific certificate validation                               |true/false| false|
|crl_max_response_size  |specifies the maximum allowed size of [CRL][crl] response              | Integer > 0| 2|

**Configure oxTrust**
Follow the steps below to configure the certificate authentication in the oxTrust Admin GUI.

1. Navigate to `Configuration` > `Manage Custom Scripts`.
2. Click on the `Person Authentication` tab.
3. Click on the `Add Custom Scritp` button.
![add-script-button](../img/admin-guide/multi-factor/add-script-button.png)
4. Fill up the from and add the [Certificate Authentication Script](./UserCertExternalAuthenticator.py)
5. Enable the script by ticking the check box
![enable](../img/admin-guide/enable.png)
6. Change the `Default Authentication Method` to `Cert`
![cert](../img/admin-guide/multi-factor/cert.png)