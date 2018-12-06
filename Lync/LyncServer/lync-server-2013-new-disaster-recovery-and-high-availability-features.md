---
title: "Lync Server 2013: Nuevas funciones alta disponibilidad y recuperación ante desastres"
TOCTitle: Nuevas funciones de alta disponibilidad y recuperación ante desastres
ms:assetid: 4fa7cd0f-784b-4d3f-b839-432c2ecaf7c1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204892(v=OCS.15)
ms:contentKeyID: 48275208
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Nuevas funciones de alta disponibilidad y recuperación ante desastres en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-20_

Como en Lync Server 2010, el esquema de alta disponibilidad principal de Lync Server 2013 se basa en la redundancia de servidor a través de grupos. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor. Esto se aplica a los servidores front-end, los servidores perimetrales, los servidores de mediación y los directores.

Lync Server 2013 agrega nuevas medidas de recuperación ante desastres al permitir emparejar grupos front-end ubicados en dos centros de datos. Si uno de los grupos emparejadas se desactiva, un administrador puede conmutar por error los usuarios de un grupo a otro grupo de la pareja, para proporcionar continuidad del servicio. Estas funciones no necesitan una red o soluciones de hardware caras como redes de almacenamiento o discos compartidos.

Lync Server 2013 también agrega alta disponibilidad del servidor back-end. Se trata de una topología opcional en la que implementa dos servidores back-end para un grupo front-end y configura una creación de reflejo de SQL sincrónica para todas las bases de datos de Lync que se ejecutan en los servidores back-end. Puede elegir si desea implementar un testigo para el reflejo.

## Vea también

#### Conceptos

[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)

