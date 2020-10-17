---
title: 'Lync Server 2013: problemas con la prueba de topología'
description: 'Lync Server 2013: problemas con la prueba de topología.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a0f24942844bcf371eff94ee04c8faafcf513d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554446"
---
# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Problemas con la prueba de topología en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Al igual que el cmdlet **Test-CsTopology** , el analizador de procedimientos recomendados proporciona una manera de comprobar que Lync Server 2013 funciona correctamente a nivel global. De forma predeterminada, el analizador de procedimientos recomendados, al igual que el cmdlet, comprueba toda la infraestructura 2013 de Lync Server, comprobando que los servicios necesarios se están ejecutando y que se han establecido los derechos y permisos de usuario adecuados para estos servicios y para los grupos de seguridad universal creados al instalar Lync Server 2013.

Además de comprobar la validez de Lync Server como un todo, **Test-CsTopology** también comprueba la validez de un servicio específico. Para obtener información detallada sobre cómo usar el cmdlet para probar servicios específicos, consulte [Test-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) en la documentación del shell de administración de Lync Server. Use la siguiente información para ayudar a resolver los problemas con su topología.

<div>


> [!NOTE]  
> Dependiendo de la configuración de sus Servidores perimetrales y las configuraciones de red perimetrales relacionadas, incluso los permisos y configuraciones de firewall, el Analizador de mejores prácticas puede no acceder y registrar sus Servidores perimetrales. Si incluye los Servidores perimetrales en su registro y los informes indican que existe un problema al acceder a los Servidores perimetrales, desmarque la casilla <STRONG>Servidores perimetrales</STRONG> y ejecute nuevamente para evitar que el problema aparezca en los informes.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Resolver problemas con su topología

Si la prueba de topología encuentra problemas con su topología, estos problemas son probablemente causados por problemas que se produjeron cuando publicó o habilitó su topología.

Cuando realiza cambios en su topología, los cambios surten efecto solo después de haberse publicado y habilitado. Debe usar el generador de topologías para realizar cambios en la topología. Después de realizar los cambios, puede publicar y habilitar dichos cambios mediante el generador de topologías.

Al publicar los cambios, la nueva información (por ejemplo, un nuevo sitio o un nuevo rol de servidor) se escribe en el almacén de administración central. Sin embargo, estos nuevos objetos (o los que se modificaron recientemente) no se unen inmediatamente a su topología. los objetos se unen a su topología solo cuando habilita la topología actualizada. Si selecciona la opción publicar en el generador de topologías, se producen estos dos pasos: los cambios se publican (es decir, se escriben en el almacén de administración central) y, a continuación, se habilita la nueva topología.

De forma predeterminada, los miembros del grupo RTCUniversalServerAdmins tienen la autorización de ejecutar el cmdlet **Publish-CsTopology** y el cmdlet **Enable-CsTopology**. Sin embargo, si no se delegaron los permisos de configuración, debe haber iniciado sesión como un administrador de dominio para ejecutar **Publish-CsTopology**. Para conceder a RTCUniversalServerAdmins el derecho de usar el cmdlet **Publish-CsTopology** , debe ejecutar el cmdlet **Grant-CsSetupPermission** en cada contenedor de Active Directory que contenga equipos que ejecutan servicios de Lync Server. Para conceder a RTCUniversalServerAdmins el derecho a usar el cmdlet **enable-CsTopology** , debe ejecutar el cmdlet **set-CsSetupPermission** en cada contenedor de servicios de dominio de Active Directory que contiene equipos que ejecutan servicios de Lync Server. Tenga en cuenta que esto se aplica a la habilitación y publicación de una topología mediante el generador de topologías. Si no ha delegado permisos mediante **set-CsSetupPermission**, solo un administrador de dominio puede habilitar y publicar una topología a través del generador de topologías.

</div>

</div>

<span> </span>

</div>

</div>

</div>

