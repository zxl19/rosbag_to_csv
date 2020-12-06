# rosbag_to_csv

1. Change `line 30` and `line 42` in `/scripts/rosbag_to_csv.py`
    from:

    ```python
    stream.write("," + msg_str)             # line 30
    stream.write("," + parent_content_name) # line 42
    ```

    to:

    ```python
    stream.write(", " + msg_str)             # line 30
    stream.write(", " + parent_content_name) # line 42
    ```

2. Change `line 81` in `/scripts/rosbag_to_csv.py`
    from:

    ```python
    stream.write(datetime.fromtimestamp(time.to_time()).strftime('%Y/%m/%d/%H:%M:%S.%f'))
    ```

    to:

    ```python
    stream.write(str(time))
    ```

------

A GUI tool to convert topics from a rosbag file to csv files

# Install

clone this repository

> $ cd ~/catkin_ws/src
> $ git clone https://github.com/AtsushiSakai/rosbag_to_csv.git
> $ cd ~/catkin_ws && rosdep install -r --ignore-src --from-paths src

# How to use

## Start the node

> $ rosrun rosbag_to_csv rosbag_to_csv.py

## Select a bag file with the GUI

![1](https://github.com/AtsushiSakai/rosbag_to_csv/wiki/1.png)

## Select topics to convert csv

You can select topics to save in csv files.

![2](https://github.com/AtsushiSakai/rosbag_to_csv/blob/master/images/pic1.png)

## Wait seconds....

A Message "Converting..." is displayed in the terminal.

## Finish convert

When the finish convert message dialog is shown,

![3](https://github.com/AtsushiSakai/rosbag_filter_gui/wiki/4.png)

CSV files are generated successfly in `~/.ros`.

![4](https://github.com/AtsushiSakai/rosbag_to_csv/blob/master/images/pic2.png)


The CSV file name is same as (the bag file name)_(each selected topic name).csv.

If You open the csv file with office software, you can see:

![5](https://github.com/AtsushiSakai/rosbag_to_csv/wiki/3.png)


# License

MIT
