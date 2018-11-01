---
title: "Conexión aplic. sucursal con supervivencia a servidores front-end de Lync Server 2013"
TOCTitle: Conexión de la aplicación de sucursal con funciones de supervivencia a un grupo de servidores front-end de Lync Server 2013
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49889050
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conexión de la aplicación de sucursal con funciones de supervivencia a un grupo de servidores front-end de Lync Server 2013

 

_**Última modificación del tema:** 2012-10-05_

Cada Aplicación de sucursal con funciones de supervivencia (SBA) está asociada con un Grupo de servidores front-end, que funciona como un registrador de reserva para la SBA. Cuando el Grupo de servidores front-end se actualiza a Lync Server 2013, la SBA debe desasociarse del Grupo de servidores front-end mientras que el Grupo de servidores front-end se actualiza. Una vez que el Grupo de servidores front-end se ha actualizado, la SBA puede reasociarse con el Grupo de servidores front-end. Esto implica eliminar la SBA de la topología en Topology Builder y luego agregar nuevamente la SBA a Topology Builder. Los usuarios hospedados en la SBA deben trasladarse a otro Grupo de servidores front-end antes de eliminar la SBA de la topología. Luego de que la SBA se agrega nuevamente a la topología, esos usuarios pueden trasladarse de vuelta a la SBA.

Estos pasos se sintetizan a continuación:

1.  Trasladar los usuarios de la sucursal hospedados en SBA a otro Grupo de servidores front-end.

2.  Eliminar SBA de su topología para desasociar el Grupo de servidores front-end existente como el registrador de reserva.

3.  Actualizar Grupo de servidores front-end a Microsoft Lync Server 2013.

4.  Agregar SBA de vuelta en su topología.

5.  Asociar el nuevo Grupo de servidores front-end a la SBA como un registrador de reserva.

6.  Mover los usuarios de la sucursal de vuelta a la SBA.

## En esta sección

  - [Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia de Lync Server 2013 a la topología](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia Lync Server 2010 a la topología](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

