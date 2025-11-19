# Setup

## BIOS

- ensure "secure boot" is off for TrueNAS Scale

## Load TrueNAS Scale

- ensure you remember the PASSWORD!
- login: "truenas_admin"
- load OS on the small drive
  - keep the 2 large drives for mirrored storage 

## Startup

Once you can login headless from another computer on network:

- change the port from 80 & 443, so that these can be used by a local web server:
  - "System, General Settings, GUI: Settings"
  - change to 81 & 444
      - you will need to re-login again after saving changes 
- wipe drives:
  - Storage, Disks
  - select the 2 storage HDs (do not select the boot drive!)
  - select the "down arrow" on each
  - select "wipe", to clear everything of (quick is OK)
  - now "test" the drives, just to make sure everything is working before starting to use them
  - select a disk, "Manual Test", "Long Test 

- create a storage pool, to run everything off of
  - select "Storage, Create Pool (call it storage or something else)
  - Data -> Mirror, since you have 2", then select the drives with "width" of 2, since we have 2 drives and 1 VDEV
 
- create Data Sets
  - "Datasets"
  - under the "storage" pool just created, add "datasets" 

- latter on you "might" want to change to a static IP address, so it does not chnage on you!
  - "Networking", select your NIC, the pencil, unselect "DHCP"
  - select "Aliases, Add" and enter static IP address you know is free and you want to use
    - xxx.xxx.xxx.xxx / 24
  - enter gate for your network (or maybe you can skip!)
  - test changes and then reopen TrueNAS from new static IP address
  - you might want to enter in your local network DNS and gateway
