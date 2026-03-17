
## Paquetes del TurtleBot

Los paquetes del TurtleBot están organizados en diferentes ramas dentro del repositorio.  
A continuación, se presentan los principales paquetes incluidos en el proyecto:

- `kobuki_ros`
- `turtlebot2_bringup`
- `turtlebot2_commander`
- `turtlebot2_description`
- `turtlebot2_gazebo`
- `turtlebot2_nav`
- `turtlebot2_navigation`
- `turtlebot2_ros2`
- `turtlebot2_slam`
- `turtlebot_description`


## Instalación de Gazebo

Para ejecutar la simulación del TurtleBot es necesario instalar **Gazebo**.

### 1. Actualizar el sistema
```bash
sudo apt update
sudo apt upgrade
```
### 2. Instalar gazebo 
```bash
sudo apt install gazebo
```
### 3. Verificación de instalación
```bash
gazebo
```

## Instalar paquetes adicionales (recomendado para ROS / TurtleBot)
```bash
sudo apt install ros-humble-gazebo-ros-pkgs
```

## Visualización del robot en Gazebo

Para visualizar el robot en Gazebo, ejecuta el siguiente comando:

```bash
ros2 launch turtlebot2_gazebo turtlebot2_world.launch.py
