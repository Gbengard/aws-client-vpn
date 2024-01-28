## Project Stages:

- **Stage 1 - Create Directory Service (Authentication for VPN Users)**
- **Stage 2 - Certificates**
- **Stage 3 - Create VPN Endpoint**
- **Stage 4 - Configure VPN Endpoint & Associations**
- **Stage 5 - Download, Install, and Test VPN Client**
- **Stage 6 - Cleanup** <= `YOU ARE HERE`

## CLIENT VPN ENDPOINT

- Open the [Client VPN Connection console](https://console.aws.amazon.com/vpc/home?region=us-east-1#ClientVPNEndpoints).
- Select `A4L Client VPN`, Click `Associations`, Click `Disassociate`, Click `Yes, Dissociate`.
- Wait for the `Disassociate` to finish.
- Select `A4L Client VPN`, then click `Actions`, `Delete Client VPN Endpoint`, Click `Yes, Delete`.
- Wait for the Client VPN Endpoint to finish deleting.

## CERT

- Type `ACM` or `Certificate Manager` into the search box at the top of the screen, then right-click and open in a new tab.
- Select the server certificate, Click `Delete`.

## Directory Service

- Type `Directory Service` into the top search box and open the [Directory Services console](https://console.aws.amazon.com/directoryservicev2/identity?region=us-east-1#!/directories) in a new tab.
- Select the directory created in stage 1.
- Click `Actions` then `Delete directory`.
- Type the name of the directory and then click `Delete`.
- Wait for the directory to finish deleting before moving on.

## STACK

- Type `CloudFormation` into the top search box and open the [CloudFormation console](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks?filteringStatus=active&filteringText=&viewNested=true&hideStacks=false) in a new tab.
- Select the `A4L` Stack, Click `Delete`, click `Delete Stack`.

## LOCAL 

- Open Manage profiles.
- Delete the A4L profile.
- Optionally delete the AWS Client VPN Software.

Stages:

- [**Stage 1 - Create Directory Service (Authentication for VPN Users)**](https://github.com/Gbengard/aws-client-vpn/blob/main/stage1.md)
- [**Stage 2 - Certificates**](https://github.com/Gbengard/aws-client-vpn/blob/main/stage2.md)
- [**Stage 3 - Create VPN Endpoint**](https://github.com/Gbengard/aws-client-vpn/blob/main/stage3.md)
- [**Stage 4 - Configure VPN Endpoint & Associations**](https://github.com/Gbengard/aws-client-vpn/blob/main/stage4.md)
- [**Stage 5 - Download, Install, and Test VPN Client**](https://github.com/Gbengard/aws-client-vpn/blob/main/stage5.md)
- [**Stage 6 - Cleanup**](https://github.com/Gbengard/aws-client-vpn/blob/main/stage6.md) <= `YOU ARE HERE`
