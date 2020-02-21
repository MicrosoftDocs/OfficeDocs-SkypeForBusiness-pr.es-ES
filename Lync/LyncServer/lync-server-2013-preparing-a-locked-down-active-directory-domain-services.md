---
title: 'Lync Server 2013: preparar servicios de dominio de Active Directory bloqueados'
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
ms.openlocfilehash: 6e57d982983bdd5ca0f85235cd44bc2fba5b1bf7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a>Preparar servicios de dominio de Active Directory bloqueados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-05-14_

Las organizaciones suelen bloquear los servicios de dominio de Active Directory para ayudar a mitigar los riesgos de seguridad. Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que necesita Lync Server 2013. Preparar correctamente un entorno de Active Directory bloqueado para Lync Server 2013 implica algunas consideraciones y pasos adicionales.

A continuación se indican dos formas comunes de limitar los permisos en un entorno de Active Directory bloqueado:

  - Las entradas de control de acceso (ACE) de los usuarios autenticados se quitan de los contenedores.

  - Se deshabilita la herencia de permisos en los contenedores de los objetos User, Contact, InetOrgPerson o Computer.

<div>

## <a name="in-this-section"></a>En esta sección

  - [Los permisos de usuarios autenticados se quitan en Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [La herencia de permisos está deshabilitada en los contenedores Computers, users o InetOrgPerson en Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

