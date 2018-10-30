# KITTI Tracking Benchmark for Autoware Tracking Algorithm
## How to use


1. Setup Autoware
2. Download any of the KITTI dataset RAW rectified sets and its tracklets (http://www.cvlibs.net/datasets/kitti/raw_data.php).
You should have a directory structure that looks like this:
```
kitti_download_dir/2011_09_26/2011_09_26_drive_0001_sync
├── image_00
│   └── data
├── image_01
│   └── data
├── image_02
│   └── data
├── image_03
│   └── data
├── oxts
│   └── data
└── velodyne_points
    └── data
```
3. Download tracklets file for the RAW data.
```
kitti_download_dir/2011_09_26/2011_09_26_drive_0001_sync
|
~~~~~~~
└──tracklets_labels.xml
```

4. Make rosbag by using this [repo](https://github.com/tomas789/kitti2bag).

5. Set `kitti_data_dir` to your kitti data directrory path in launch/benchmark.launch#L104

6. Launch `benchmark.launch` in launch directory.

7. Play the rosbag made in step 4.

8. After finished recording results, you should get `benchmark_result.txt` file under the kitti data directory.
```
kitti_download_dir/2011_09_26/2011_09_26_drive_0001_sync
|
~~~~~~~
└──benchmark_result.txt
```

9. Run `python3 evaluate_tracking.py`

10. You will see benchmark directory under `kitti data directory`.
