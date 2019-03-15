## Multihost Hyperledger Fabric Network
This is a multihost Hyperledger Fabric setup that can be used to setup across various VMs.

1. Edit template files for Org1 and Org2
    - Edit the IP address only of the machines of the peers in 'extra_hosts'

2. Run command to generate certificates
    - `./network.sh generate`

3. Copy the files to the second VM
    - `scp -r ../test-network-multihost <username@second-vm-ip>`

4. Bring up Orderer and Org1 (Peers, CouchDBs and CliOrg1)
    - `./network.sh up -org1`

5. Bring up Org2 (Peers, CouchDBs and CliOrg2) in Second VM
    - `./network.sh up -org2`

6. Connect to CliOrg1 and run the script
    - `docker exec -it cliOrg1 bash`
    - `./scripts/script.sh`

7. DONE !

#### Extras

1. Stop containers
    - `./network.sh stop`

2. Start containers
    - `./network.sh start`
