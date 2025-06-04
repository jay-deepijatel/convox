# ConVox 4.0 Installation Guide

## Step 1: Download the Tar File
Download the tar file from the following link:

[Download ConVox 4.0.2 Image](https://deepijatelepvtltd-my.sharepoint.com/:u:/g/personal/ahmed_deepijatel_com/EaInQcuiMVZAlIK2jht4BtYByA00gqFeK0R5hqZ5MfEfBw)

Once the download is complete, proceed to extract the tar file.

## Step 2: Extract the Tar File
Use the following command to untar the downloaded file:

```bash
tar -xvf convox4.0.2_image.tar
```

After extraction, you will see a folder named `convox4.0.2_image`. Navigate to this folder to proceed:

```bash
cd convox4.0.2_image
```

## Step 3: Execute the Restore Script
Navigate to the extracted folder and execute the restore script using the following command:

```bash
./restore.sh
```

The script will prompt you to enter the IP address that should be updated in all necessary configurations. After providing the IP address, it will ask for reboot confirmation. Press `y` to reboot the server.

## Step 4: Start Required Services
After the reboot, execute the second script to start all required services. Use the following command:

```bash
./start_services.sh
```

This will ensure that all necessary services are up and running.

## Step 5: Finalize Configuration
Execute the final script to adjust configuration parameter values based on your system's RAM and CPU cores. Run the following command:

```bash
./checklist.sh
```

Once this script completes, your setup is ready.
