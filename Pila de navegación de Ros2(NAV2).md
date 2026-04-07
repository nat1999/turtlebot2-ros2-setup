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

