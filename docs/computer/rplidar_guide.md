# Guide to RPLidar-A1

This is a simple guide to set-up the Lidar and run few demo applications on a Windows Machine. This is in now way a comprehensive guide to set-up RP Lidar for programming needs. It's scope is only limited to running Demo.

For setting it up and utilizing it's ROS compatibility follow their official [GitHub Repo][slamtec-public-repo]

---

## About RPLidar-A1

RPLidar-A1 is 360* omnidirectional laser range scanner used to generate an outline map for the environment and ideal for applying SLAM algorithms. It works on laser triangulation ranging principle and uses high-speed vision acquisition and processing hardware developed by Slamtec. [Link to Official Website](https://www.slamtec.com/en/Lidar/A1)

It uses UART to communicate with the host device. However, Slamtec has been generous enough to provide a chipset to communicate via USB COM Ports using USB to UART Bridge Virtual COM Port(VCP) Drivers.

**General Applications:**

1. Robot simultaneous localization and mapping (SLAM)
2. Environment scanning and 3D rebuilding
3. Obstacle detecting and avoiding
4. Multi-point touching and man-machine interaction

**Some general Specifications:**
|Detection Range|Sample Rate|Angular Resolution|Distance Resolution|Typical Scan frequency|
| :--: | :--: | :--: | :--: | :--:|
|30cm to 12m|8000 Samples/s|1 Degree|0.2cm|5.5 Hz|

For more detailed specification, check the [official website](https://www.slamtec.com/en/Lidar/A1Spec).

---

## Set-up on Windows

1. Install [cp2102 Driver](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers) to connect it using USB. (_preferable_)
2. Install RoboStudio to connect using WiFi.

---

## Run Demo

The company provides the following 3 simple demos for fast evaluations:

1. Ultra_Simple:
2. Simple_Grabber:
3. Frame_Grabber:

Checkout their [GitHub Repo][slamtec-public-repo] for details on how to run each of them on different machines.

### Run `frame_grabber`

1. Download `rp_lidar_sdk_v1.4.2.7z` from [here](./assets/rp_lidar_sdk_v1.4.2.7z).
2. Extract the all the files to a folder.
3. Navigate to `rp_lidar_sdk_v1.4.2/tools/win32/`
4. Run `frame_grabber.exe`

[slamtec-public-repo]: <https://github.com/Slamtec/rplidar_sdk>
