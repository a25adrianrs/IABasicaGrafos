# Nuevas localizaciones en TanksWayPoints
En este ejercicio añadir dos localizaciones con los nombres **Oil Camp** y **Palm Trees**
Para ello  creé 2 waypoints nuevos.
- El WayPoint10 que corresponde a **Palm Trees** el cual
esta situado entre los WayPoints del **Helipuerto** y **La Roca**.
- El WayPoint09 que corresponde a **Oil Camp** el cual se situa entre los WayPoints que corresponden
a **Factory** y los WayPoints02 y 04 este ultimo corresponde a **Ruin**.

- **ATENCION** automaticamente por algún motivo Unity cambio el nombre del **WayPoint009** que crée para la nueva ruta
por **001** y por consiguiente todos los números finales que hacen referencia al resto de WayPoints aumentaron en 1,
no se exactamente el mótivo pero es para que quede constancia que el **WayPoint001** es el **009** que yo creé para una de las nuevas localizaciones
***aún asi el ejercicio fue probado y los las rutas entre waypoints funcionan correctamente***.

Creé dos nuevos metodos dentro del script **TanksWayPoints** para usar en el menú e indicar a los tanques que se dirigan a las nuevas localizaciones:
- GotoPalmTrees
```csharp
    public void GotoPalmTrees()
    {
        graph.AStar(currentNode, waypoints[9]);
        currentWP = 0;
    }
```
- GotoOilCamp
```csharp
 public void GotoOilCamp()
    {
        graph.AStar(currentNode, waypoints[8]);
        currentWP = 0;
    }
```

Añadi los nuevos WayPoints a la lista de elementos de **WPManager** y creé 6 nuevos links 
- **OilCamp**
    - Link 11 :  Node 1: ***WP002***   Node2: ***WP001***
    - Link 12 :  Node 1: ***WP003***   Node2: ***WP001***
    - Link 13 :  Node 1: ***WP004***   Node2: ***WP001***
- **PalmTrees**
  - Link 14 :  Node 1: ***WP005***  Node2: ***WP010***
  - Link 15 :  Node 1: ***WP008***  Node2: ***WP010***
  - Link 16 :  Node 1: ***WP009***  Node2: ***WP010***
 
Por último tan solo tuve que crear dos nuevos botones en el **Canvas** y dentro del apartado ***OnClick()***
de ambos seleccionar los metodos para **PalmTrees** y **OilCamp**
  
