A simple version of LVI-SAM  can be verified using a quadruped robot gazebo.

![dog](/home/skywoodsz/LVI_SAM_ws/git_up/pic/dog.png)

## 1. System 

We use **Aliengo** with **VLP-16**, **camera** and **IMU** to verify on the gazebo. The robot is controlled by **champ**, which is an open source quadruped controller.

The topics of sensors are

```
CloudTopic: "/velodyne_points" 
imuTopic: "/imu/data"   
image_topic: "/camera/image_raw"
```

You can check the details in the configuration file.

***Notes:  You shuold to close odom topic posting in champ to verify LVI-SAM.***

## 2. Install

- [champ](https://github.com/chvmp/champ)

- [LVI-SAM](https://github.com/epicjung/LVI_SAM_fixed)

***Notes: we verified on the ubuntu2004. You can choose different LVI-SAM versions according to your system version***

- Download our configuration files and robot description files.

### 3. Run

```
mon launch aliengo_config gazebo.launch 
```

```
mon launch champ_teleop teleop.launch joy:=true
```

```
mon launch lvi_sam run.launch
```

![2022-08-23_18-56](/home/skywoodsz/LVI_SAM_ws/git_up/pic/2022-08-23_18-56.png)