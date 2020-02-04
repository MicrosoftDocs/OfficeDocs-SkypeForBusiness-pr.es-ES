---
title: 'Lync Server 2013: Conceder permisos'
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
ms.openlocfilehash: ccfdf804fc9052ac69b383d0f8cd3321222e79a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-permissions-in-lync-server-2013"></a>Conceder permisos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-15_

Para la configuración, puede conceder permisos al grupo universal RTCUniversalServerAdmins de una unidad organizativa de Active Directory específica, lo que permite a los miembros del grupo RTCUniversalServerAdmins de esa OU instalar Lync Server 2013 en el dominio especificado. Al conceder permisos para una unidad organizativa, se conceden los permisos siguientes:

  - Consulte

  - Graba

  - ReadSPN

  - WriteSPN

Para la administración, puede Agregar permisos a unidades organizativas específicas para que los miembros de los grupos RTC universales creados por la preparación del bosque puedan tener acceso a las unidades organizativas sin necesidad de ser miembros del grupo administradores del dominio. Los permisos agregados a la unidad organizativa especificada son los mismos permisos que el cmdlet **enable-CsAdDomain** agrega a los contenedores de ou de equipos y usuarios.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Concesión de permisos de instalación en Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Conceder permisos de unidad organizativa en Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

