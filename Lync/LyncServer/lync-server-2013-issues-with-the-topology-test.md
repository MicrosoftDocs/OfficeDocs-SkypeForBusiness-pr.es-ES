---
title: 'Lync Server 2013: problemas con la topología de la prueba'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Issues with the topology test
ms:assetid: 821e8916-7b5d-4f64-8fb0-e5cc392ec1bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205045(v=OCS.15)
ms:contentKeyID: 48184670
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d416aac6460870ab14d5296bcc6c7944ecf699e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-topology-test-in-lync-server-2013"></a>Problemas con la prueba de topología en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Al igual que el cmdlet **Test-CsTopology** , el analizador de procedimientos recomendados proporciona una forma de comprobar que Lync Server 2013 está funcionando correctamente en un nivel global. De forma predeterminada, el analizador de procedimientos recomendados, como el cmdlet, comprueba toda la infraestructura de Lync Server 2013, verifica que los servicios necesarios se estén ejecutando y que se hayan establecido los derechos y permisos de usuario apropiados para estos servicios y para la aplicación universal. grupos de seguridad creados al instalar Lync Server 2013.

Además de comprobar la validez de Lync Server como un todo, **Test-CsTopology** también comprueba la validez de un servicio específico. Para obtener detalles sobre el uso del cmdlet para probar servicios específicos, consulte [prueba-CsTopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) en la documentación del shell de administración de Lync Server. Use la siguiente información para ayudar a resolver problemas con su topología.

<div>


> [!NOTE]  
> En función de la configuración de los servidores perimetrales y de cualquier configuración de red perimetral relacionada, incluyendo la configuración y los permisos del firewall, es posible que el analizador de procedimientos recomendados no pueda tener acceso a los servidores perimetrales y explorarlos. Si incluye servidores perimetrales en el análisis y los informes indican que hay un problema de acceso a los servidores perimetrales, desactive la casilla <STRONG>servidores perimetrales</STRONG> y ejecute el examen de nuevo para evitar que se muestre el problema en los informes.



</div>

<div>

## <a name="resolving-issues-with-your-topology"></a>Solución de problemas con su topología

Si la prueba de topología encontró problemas con su topología, probablemente se deba a problemas que se produjeron al publicar o habilitar su topología.

Cuando realice cambios en su topología, los cambios solo se aplicarán cuando se hayan publicado y habilitado. Debe usar topología Builder para realizar cambios de topología. Después de realizar los cambios, puede publicar y habilitar esos cambios con el generador de topologías.

Al publicar los cambios, la nueva información (por ejemplo, un nuevo sitio o una nueva función de servidor) se escribe en el almacén de administración central. Sin embargo, estos nuevos objetos (o los recién modificados) no se unen inmediatamente a su topología. Los objetos se unen a su topología solo cuando habilita la topología actualizada. Si selecciona la opción de publicación en el generador de topología, se realizan ambos pasos: los cambios se publican (es decir, se escriben en el almacén de administración central) y, a continuación, se habilita la nueva topología.

De forma predeterminada, los miembros del grupo RTCUniversalServerAdmins tienen autorización para ejecutar el cmdlet **Publish-CsTopology** y el cmdlet enable **-CsTopology** . Sin embargo, si los permisos de configuración no se han delegado, debe haber iniciado sesión como administrador de dominio para poder ejecutar **Publish-CsTopology**. Para otorgar a RTCUniversalServerAdmins el derecho de usar el cmdlet **Publish-CsTopology** , debe ejecutar el cmdlet **Grant-CsSetupPermission** en todos los contenedores de Active Directory que contienen los equipos que ejecutan los servicios de Lync Server. Para otorgar a RTCUniversalServerAdmins el derecho de usar el cmdlet **enable-CsTopology** , debe ejecutar el cmdlet **set-CsSetupPermission** en todos los contenedores de los servicios de dominio de Active Directory que contengan equipos con los servicios de Lync Server. Tenga en cuenta que esto se aplica a habilitar y publicar una topología mediante el generador de topologías. Si no ha delegado permisos mediante **set-CsSetupPermission**, solo el administrador del dominio puede habilitar y publicar una topología a través de Topology Builder.

</div>

</div>

<span> </span>

</div>

</div>

</div>

