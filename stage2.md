# Advanced AWS Client VPN Demo - Certificate Creation

## Project Overview

This GitHub project provides a step-by-step guide for setting up an advanced AWS Client VPN, focusing on certificate creation in Stage 2. The stages include:

1. Stage 1 - Create Directory Service (authentication for VPN users)
2. Stage 2 - Certificates <= **YOU ARE HERE**
3. Stage 3 - Create VPN Endpoint
4. Stage 4 - Configure VPN Endpoint & Associations
5. Stage 5 - Download, install, and test VPN Client
6. Stage 6 - Cleanup

**Note: Ensure that the Directory Service created in the previous step is in an `Active` state before proceeding.**

## Creating Certificates

### Server Certificate

This section of the demo involves downloading EasyRSA and using it to create certificates, which will be imported into ACM. For simplicity (focusing on ClientVPN), only the server certificate will be used.

### Linux/macOS

```bash
# open a terminal
cd /tmp 
git clone https://github.com/OpenVPN/easy-rsa.git
cd easy-rsa/easyrsa3
./easyrsa init-pki
./easyrsa build-ca nopass
# Set Common Name: ANIMALS4LIFEVPN
./easyrsa build-server-full server nopass
aws acm import-certificate --certificate fileb://pki/issued/server.crt --private-key fileb://pki/private/server.key --certificate-chain fileb://pki/ca.crt --profile iamadmin-general
```

### Windows

1. Open the OpenVPN Community Downloads page, download the Windows installer, and run it.
2. Open the EasyRSA releases page, download the ZIP file, extract it, and copy the EasyRSA folder to \Program Files\OpenVPN.
3. Open the command prompt as an Administrator, navigate to \Program Files\OpenVPN\EasyRSA, and run the following commands:
   ```bash
   EasyRSA-Start
   ./easyrsa init-pki
   ./easyrsa build-ca nopass
   ./easyrsa build-server-full server nopass
   ./easyrsa build-client-full client1.domain.tld nopass
   exit
   ```
4. Import the server certificate into ACM:
   ```bash
   aws acm import-certificate --certificate fileb://pki/issued/server.crt --private-key fileb://pki/private/server.key --certificate-chain fileb://pki/ca.crt --profile iamadmin-general
   ```

### Verify Certificate in ACM

1. Type `ACM` or `Certificate Manager` into the search box, then right-click and open in a new tab.
2. Verify that your certificate exists in the `us-east-1` region.

**END OF STAGE 2**