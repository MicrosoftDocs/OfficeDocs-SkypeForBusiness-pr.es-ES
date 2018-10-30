---
title: 'Lync Server 2013: Componentes requeridos para el director'
TOCTitle: Componentes requeridos para el director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48274540
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes requeridos para el director en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

El único componente necesario para crear y configurar un Director es implementar el rol de servidor de Director. Haga esto mediante el uso de Generador de topologíasy defina un grupo de equipos único o un grupo de equipos múltiples en el nodo de Grupo de directores. Cuando haya definido el Director o el Grupo de directores, se ejecuta la Asistente para la implementación de Lync Serveren el equipo que va a ser un Director. En el caso de un Grupo de directores, ejecute el Asistente para la implementación de Lync Server en cada servidor que será miembro del grupo de servidores.

## Topologías

Es posible implementar tanto un solo servidor de Director como un Grupo de directores. El Director es siempre un servidor o grupo independiente que no se instala con ningún otro rol de servidor en el Lync Server 2013.


> [!NOTE]
> Si no implementa Directores, el Servidor front-end o el Grupo de servidores front-end asumirá rol Director.



Un grupo de Directores debe tener equilibrio de carga. Puede realizar una de las acciones siguientes:

  - Cree una topología que usa un equilibrador de carga de hardware para servicios web y equilibrio de carga de sistema de nombres de dominio (DNS) para los demás tipos de tráfico.
    
    [Grupo de director escalado - Equilibrio de carga DNS y equilibradores de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - Cree una topología que usa un equilibrador de carga de hardware para el equilibrio de carga necesario para el Grupo de directores.
    
    [Grupo de servidores de director escalado - Equilibrador de carga de hardware en Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

