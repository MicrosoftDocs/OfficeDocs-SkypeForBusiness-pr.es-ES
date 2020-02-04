---
title: 'Lync Server 2013: Preparar Servicios de dominio de Active Directory bloqueados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing a locked-down Active Directory Domain Services
ms:assetid: 68bde963-3fa3-4102-88d6-ac931c1dd2d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398492(v=OCS.15)
ms:contentKeyID: 48184377
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d589fbc6b7d31b38bc788ba9851edf4386294ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>Preparar Servicios de dominio de Active Directory bloqueados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-14_

Las organizaciones suelen bloquear los servicios de dominio de Active Directory para ayudar a mitigar los riesgos de seguridad. Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que necesita Lync Server 2013. Preparar correctamente un entorno de Active Directory bloqueado para Lync Server 2013 implica algunas consideraciones y pasos adicionales.

Las siguientes son dos formas comunes en las que los permisos están limitados en un entorno de Active Directory bloqueado:

  - Las entradas de control de acceso (ACE) autenticadas se quitan de los contenedores.

  - La herencia de permisos está deshabilitada en los contenedores de objetos user, Contact, InetOrgPerson o Computer.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Se quitan los permisos de usuario autenticado en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [La herencia de permisos está deshabilitada en los contenedores Computer, Users o InetOrgPerson en Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

