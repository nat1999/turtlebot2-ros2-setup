# 🤖 Implementación de la pila de navegación de ROS 2 (Nav2) en TurtleBot2

Nav2 es un conjunto de nodos en ROS 2 que permiten la navegación autónoma de un robot en un entorno. Para ello, utiliza técnicas de mapeo, localización, planificación de rutas y detección de obstáculos en tiempo real.

👉 En otras palabras:
Es el “cerebro de navegación” que le dice al robot cómo ir de un punto A a un punto B sin chocar.

La pila de navegación permite que el robot:

- '📍 Sepa dónde está (localización)'
- '🗺️ Entienda el entorno (mapa)'
- '🚧 Detecte obstáculos'
- '🧠 Planifique rutas'
- '🚗 Se mueva solo hacia un objetivo'

Nav2 incluye paquetes como:

- `nav2_planner`: Planificador global de rutas. 
- `nav2_controller`: Controlador local del robot.
- `nav2_costmap_2d`: Detección de obstáculos.
- `nav2_bt_navigator`: Coordinación de navegación. 
- `nav2_bringup`: Inicia todos los nodos de Nav2.

# 🤖 Adaptación del TurtleBot2 para que usar ROS 2 Navigation (Nav2)

1. Ir al siguiente archivo
natalia@DESKTOP-PFND7RL:~/ros2_ws/src/turtlebot2_nav/launch$ ls
nav2.launch.py  rviz_nav2.launch.py  slam_nav2.launch.py  turtlebot_bringup.launch.py  turtlebot_bringup.launch.py.save
natalia@DESKTOP-PFND7RL:~/ros2_ws/src/turtlebot2_nav/launch$ nano turtlebot_bringup.launch.py
natalia@DESKTOP-PFND7RL:~/ros2_ws/src/turtlebot2_nav/launch$

turtlebot_bringup.launch.py

Se pone:
from launch import LaunchDescription
from launch_ros.actions import Node
from launch.actions import IncludeLaunchDescription
from launch.launch_description_sources import PythonLaunchDescriptionSource
from ament_index_python.packages import get_package_share_directory
import os

def generate_launch_description():

    # ---------------- LIDAR ----------------
    lidar = Node(
        package='urg_node',
        executable='urg_node_driver',
        name='lidar',
        output='screen',
        parameters=[{
            'serial_port': '/dev/ttyUSB0',  # cámbialo si aplica
            'frame_id': 'laser'
        }]
    )

    # ---------------- NAV2 (CORRECTO) ----------------
    nav2_dir = get_package_share_directory('nav2_bringup')

    nav2 = IncludeLaunchDescription(
        PythonLaunchDescriptionSource(
            os.path.join(nav2_dir, 'launch', 'bringup_launch.py')
        ),
        launch_arguments={
            'use_sim_time': 'false',
            'autostart': 'true'
        }.items()
    )

    # ---------------- RETURN ----------------
    return LaunchDescription([
        lidar,
        nav2
    ])

    luego en el espacio de trabajo, hacer compilación
    


3. Hay que instalar:
sudo apt update
sudo apt install ros-humble-urg-node 

