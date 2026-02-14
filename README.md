# Racerbot Workspace

The official SFU Racerbot Workspace with solutions to the RoboRacer labs and all other learning projects.

## How to Run
1. Build the image
    ```
    `docker build -f .devcontainer/Dockerfile -t racerbot .`
    ```
2. Run the image
    ```
    docker run -it \
        --name racerbot \
        -v $(pwd)/src:/racerbot_ws/src \
        --net=host \
        racerbot
    ```
3. Build the workspace and source the overlay:
    ```bash
    colcon build
    source install/setup.bash
    ```
    - If `colcon build` doesn't work try `sudo chown -R rosdev:rosdev /racerbot_ws`

## VSCode
If you want a smooth VSCode workflow and intellisense for ROS 2 follow these instructions:
1. Install these extensions in VSCode:
    - Dev containers
    - C/C++, C/C++ Extension Pack
    - Robotics Developer Environment
    - CMake, CMake Tools
    - Container Tools
    - Python
2. In VSCode, open your ROS 2 container using the Dev Containers command: `cmd+shift+p`: 'Open folder in container'.
3. Redownload your extensions (if they didn't follow) in your VSCode container enviornment.
4. Make sure you have your ROS 2 packages downloaded (using `rosdep`) whenever you use a new package. This will ensure the intellisense works for it.
