---
title: 'Lync Server 2013: requisitos para publicar una topología'
description: 'Lync Server 2013: requisitos para publicar una topología.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5699657e680b78587b8ba354e9dc538f2e280c56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577866"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Requisitos para publicar una topología en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

En este tema se describen los requisitos de infraestructura y software específicos para la publicación de una topología, ya sea mediante el generador de topologías o la interfaz de línea de comandos del shell de administración de Lync Server 2013. Estos requisitos son adicionales a los requisitos de sistema operativo, software y permisos generales aplicables a todas las herramientas administrativas de Lync Server 2013. Asegúrese de que cumple con todos los requisitos de las herramientas administrativas antes de publicar una topología.

  - Debe ejecutar el generador de topologías en un equipo que se haya unido al mismo dominio o al bosque de la implementación de Lync Server 2013 que está creando para que los pasos de preparación de los servicios de dominio de Active Directory ya se hayan completado, lo que le permite usar las herramientas administrativas en ese equipo para publicar correctamente su topología.

  - Los equipos definidos en la topología deben estar unidos al dominio, excepto los servidores perimetrales y en AD DS. Sin embargo, los equipos no necesitan estar en línea cuando publica la topología.

  - El recurso compartido de archivos para el grupo de servidores debe estar creado y disponible para los usuarios remotos.

  - Para publicar un grupo de servidores front-end Enterprise Edition, el servidor back-end basado en SQL Server debe estar unido al dominio en el que va a implementar los servidores, en línea y configurados con las reglas de Firewall adecuadas para que estén disponibles para los usuarios remotos. Para obtener información detallada sobre cómo especificar las excepciones de firewall, consulte [Understanding Firewall Requirements for SQL Server with Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Para obtener más información acerca de la configuración de SQL Server, consulte [configurar SQL Server para Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > El servidor Standard Edition tiene una base de datos combinada que aceptará la configuración publicada. Primero debe ejecutar la tarea de configuración <STRONG>preparar el primer servidor Standard Edition</STRONG> en el Asistente para la implementación de Lync Server.

    
    </div>

<div>

## <a name="see-also"></a>Consulte también


[Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Delegación de permisos de instalación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Requisitos de software de herramientas administrativas en Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Compatibilidad del sistema operativo con el servidor y las herramientas en Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Permisos y derechos de administrador necesarios para la instalación y administración de Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

