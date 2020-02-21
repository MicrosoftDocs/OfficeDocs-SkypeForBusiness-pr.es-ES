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
ms.openlocfilehash: d44fe94ab8e02551f8d33d95248c6cede63a6974
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="performing-and-monitoring-backups-in-lync-server-2013"></a>Realización y supervisión de copias de seguridad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-15_

Las prioridades empresariales deben impulsar la especificación de los requisitos de copia de seguridad y restauración de su organización. La realización de copias de seguridad de los servidores y los datos es la primera línea de defensa en la planeación de un desastre.

Los equipos que ejecutan los servicios o roles de servidor de Lync Server 2013 deben tener una copia de la topología actual, las opciones de configuración actuales y las directivas actuales para que puedan funcionar en su rol designado. Lync Server es responsable de garantizar que esta información se pase a todos los equipos que la necesiten.

Los cmdlets **Export-CsConfiguration** y **Import-CsConfiguration** se usan para realizar copias de seguridad y restaurar la topología, las opciones de configuración y las directivas de Lync Server durante una actualización del almacén de administración central. Los cmdlets **Export-CsConfiguration** permiten exportar datos a un. Archivo ZIP. A continuación, puede usar el cmdlet **Import-CsConfiguration** para leerlo. Archivo ZIP y restaurar la topología, las opciones de configuración y las directivas en el almacén de administración central. A continuación, los servicios de replicación de Lync Server replicarán la información restaurada en otros equipos que ejecutan servicios de Lync Server.

La capacidad de exportar e importar datos de configuración también se usa durante la configuración inicial de los equipos que se encuentran en la red perimetral (por ejemplo, servidores perimetrales). Al configurar un equipo en la red perimetral, primero debe realizar una replicación manual con los cmdlets CsConfiguration: debe exportar los datos de configuración mediante **Export-CsConfiguration** y, a continuación, copiar el. Archivo ZIP en el equipo en la red perimetral. Luego, puede usar **Import-CsConfiguration** y el parámetro LocalStore para importar los datos. Solo tiene que hacerlo una vez. A continuación, la replicación se producirá automáticamente.

Quién puede iniciar este cmdlet: de forma predeterminada, los miembros de los grupos siguientes están autorizados a ejecutar el cmdlet **Export-CsConfiguration** localmente: RTCUniversalServerAdmins. Para devolver una lista de todos los roles RBAC a los que se asigna este cmdlet (incluidos los roles RBAC personalizados que haya creado), ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:

`Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Export-CsConfiguration"}`

Se debe realizar una copia de seguridad de todas las bases de datos back-end de SQL 2012 según los [procedimientos recomendados de SQL](https://go.microsoft.com/fwlink/p/?linkid=290716).

Las pruebas periódicas del plan de recuperación ante desastres para la infraestructura de Lync Server 2013 deben realizarse en un entorno de laboratorio que imite el entorno de producción lo más fielmente posible. Consulte las tareas mensuales para obtener más información acerca de las pruebas de recuperación ante desastres.

Tenga en cuenta que la frecuencia de copia de seguridad se puede ajustar, en función de los objetivos de punto de restauración y punto de recuperación. Como procedimiento recomendado, realice instantáneas regulares y periódicas durante todo el día. Por lo general, debe realizar copias de seguridad completas cada 24 horas.

<div>

## <a name="see-also"></a>Consulta también


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Export-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Export-CsConfiguration)  
[Procedimientos recomendados de SQL](https://go.microsoft.com/fwlink/p/?linkid=290716)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

