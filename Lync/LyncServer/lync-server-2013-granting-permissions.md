---
title: 'Lync Server 2013: concesión de permisos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting permissions
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48185446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc725122005793790344544575fa4456d742c88d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146123"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Concesión de permisos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-15_

Para el programa de instalación, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa (OU) de Active Directory específica, habilitando a los miembros del grupo RTCUniversalServerAdmins en dicha unidad organizativa que instalen Lync Server 2013 en el dominio especificado. Cuando se conceden permisos para una unidad organizativa, se conceden los siguientes permisos:

  - Leer

  - Escritura

  - ReadSPN

  - WriteSPN

Para la administración, puede agregar permisos a las OU especificadas, de modo que los miembros de los grupos universales RTC que se han creado durante la preparación del bosque pueden obtener acceso a las OU sin ser miembros del grupo de administradores de dominio. Los permisos agregados a la OU especificada son los mismos permisos que los que el cmdlet **Enable-CsAdDomain** agrega a los equipos y los contenedores de OU de los usuarios.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Concesión de permisos de instalación en Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Concesión de permisos de unidad organizativa en Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

