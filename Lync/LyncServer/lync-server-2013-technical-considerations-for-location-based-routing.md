---
title: 'Lync Server 2013: Consideraciones técnicas para el enrutamiento basado en ubicación'
TOCTitle: Consideraciones técnicas para el enrutamiento basado en ubicación
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ994027(v=OCS.15)
ms:contentKeyID: 52061618
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Consideraciones técnicas para el enrutamiento basado en ubicación en Lync Server 2013

 

_**Última modificación del tema:** 2013-03-09_

Al planear el enrutamiento según ubicación, debe considerar el impacto de los siguientes escenarios.

## Recuperación ante desastres

Durante una conmutación por error del grupo principal a un grupo de reserva, así como al restaurar operaciones normales al grupo principal, el enrutamiento según ubicación permanece aplicado todas las veces durante un procedimiento de recuperación ante desastres.

## Aplicación de sucursal con funciones de supervivencia

La configuración del enrutamiento según ubicación afecta a la planeación de dónde se van a implementar las puertas de enlace asociadas a los Aplicaciones de sucursal con funciones de supervivencia. La puerta de enlace asociada a SBA debe estar situada en el mismo sitio de red que Aplicación de sucursal con funciones de supervivencia; de lo contrario, los usuarios hospedados en Aplicación de sucursal con funciones de supervivencia no podrán realizar llamadas salientes si el enrutamiento según ubicación está configurado. Cuando la conexión WAN entre Aplicación de sucursal con funciones de supervivencia y el sitio central está inactiva, las restricciones de enrutamiento según ubicación permanecen aplicadas.

## Vea también

#### Otros recursos

[Planificar el enrutamiento basado en ubicación en Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

