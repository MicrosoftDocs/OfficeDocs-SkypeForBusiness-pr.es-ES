---
title: 'Lync Server 2013: realización y supervisión de copias de seguridad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing and monitoring backups
ms:assetid: 2df415d4-0f37-460e-99ff-4035a9a2f445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720912(v=OCS.15)
ms:contentKeyID: 63969595
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3181a266e5792d190186e9f09b2cab5852156cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Realizar y supervisar copias de seguridad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-15_

Las prioridades empresariales deben impulsar la especificación de los requisitos de copia de seguridad y restauración de su organización. La realización de copias de seguridad de los datos y los servidores es la primera línea de defensa en el planeamiento de un desastre.

Los equipos que ejecutan los servicios de Lync Server 2013 o los roles de servidor deben tener una copia de la topología actual, de las opciones de configuración actuales y de las directivas actuales antes de que puedan funcionar con su función designada. Lync Server es responsable de asegurarse de que esta información se transmita a todos los equipos que la necesiten.

Los cmdlets **Export-CsConfiguration** y **Import-CsConfiguration** se usan para realizar copias de seguridad y restaurar la topología, las opciones de configuración y las directivas de Lync Server durante una actualización de almacén de administración central. Los cmdlets **Export-CsConfiguration** permiten exportar datos a un. Archivo ZIP. Puede usar el cmdlet **Import-CsConfiguration** para leerlo. Archivo ZIP y restaurar la topología, los parámetros de configuración y las directivas en el almacén de administración central. Después, los servicios de replicación de Lync Server replicarán la información restaurada en otros equipos que ejecuten servicios de Lync Server.

La capacidad de exportar e importar datos de configuración también se usa durante la configuración inicial de los equipos que se encuentran en la red perimetral (por ejemplo, los servidores perimetrales). Al configurar un equipo en la red perimetral, primero debe realizar una replicación manual con los cmdlets de CsConfiguration: debe exportar los datos de configuración con **Export-CsConfiguration** y, a continuación, copie el archivo. Archivo ZIP en el equipo de la red perimetral. Después de ese, puede usar **Import-CsConfiguration** y el parámetro LocalStore para importar los datos. Solo tienes que hacerlo una vez. Después de eso, la replicación se realizará de forma automática.

¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet **Export-CsConfiguration** de forma local: RTCUniversalServerAdmins. Para devolver una lista de todos los roles de RBAC, este cmdlet se asigna a (incluidos los roles de RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

Se debe realizar una copia de seguridad de todas las bases de datos back-end de SQL 2012 según las recomendaciones de [SQL](http://go.microsoft.com/fwlink/p/?linkid=290716).

Las pruebas periódicas del plan de recuperación ante desastres para su infraestructura de Lync Server 2013 deberían realizarse en un entorno de laboratorio que imite el entorno de producción de la mejor manera posible. Para obtener más información sobre las pruebas de recuperación ante desastres, consulte las tareas mensuales.

Tenga en cuenta que la frecuencia de la copia de seguridad se puede ajustar en función de su punto de restauración y sus objetivos de punto de recuperación. Como práctica recomendada, realice instantáneas periódicas y periódicas durante todo el día. Por lo general, deberías realizar copias de seguridad completas cada 24 horas.

<div>

## <a name="see-also"></a>Vea también


[Importar-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Exportar-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Procedimientos recomendados de SQL](http://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

