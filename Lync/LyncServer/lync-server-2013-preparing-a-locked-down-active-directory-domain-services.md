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
ms.openlocfilehash: 1b3e1eb33568bbc0e1742e31638a20879e4fffdd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513367"
---
# <a name="preparing-a-locked-down-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="8da02-102">Preparar servicios de dominio de Active Directory bloqueados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da02-102">Preparing a locked-down Active Directory Domain Services in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8da02-103">_**Última modificación del tema:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="8da02-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="8da02-104">Las organizaciones suelen bloquear los servicios de dominio de Active Directory para ayudar a mitigar los riesgos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8da02-104">Organizations often lock down Active Directory Domain Services to help mitigate security risks.</span></span> <span data-ttu-id="8da02-105">Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que necesita Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8da02-105">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="8da02-106">Preparar correctamente un entorno de Active Directory bloqueado para Lync Server 2013 implica algunas consideraciones y pasos adicionales.</span><span class="sxs-lookup"><span data-stu-id="8da02-106">Properly preparing a locked-down Active Directory environment for Lync Server 2013 involves some additional considerations and steps.</span></span>

<span data-ttu-id="8da02-107">A continuación se indican dos formas comunes de limitar los permisos en un entorno de Active Directory bloqueado:</span><span class="sxs-lookup"><span data-stu-id="8da02-107">Two common ways in which permissions are limited in a locked-down Active Directory environment are as follows:</span></span>

  - <span data-ttu-id="8da02-108">Las entradas de control de acceso (ACE) de los usuarios autenticados se quitan de los contenedores.</span><span class="sxs-lookup"><span data-stu-id="8da02-108">Authenticated user access control entries (ACEs) are removed from containers.</span></span>

  - <span data-ttu-id="8da02-109">Se deshabilita la herencia de permisos en los contenedores de los objetos User, Contact, InetOrgPerson o Computer.</span><span class="sxs-lookup"><span data-stu-id="8da02-109">Permissions inheritance is disabled on containers of User, Contact, InetOrgPerson, or Computer objects.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8da02-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8da02-110">In This Section</span></span>

  - [<span data-ttu-id="8da02-111">Los permisos de usuarios autenticados se quitan en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da02-111">Authenticated user permissions are removed in Lync Server 2013</span></span>](lync-server-2013-authenticated-user-permissions-are-removed.md)

  - [<span data-ttu-id="8da02-112">La herencia de permisos está deshabilitada en los contenedores Computers, users o InetOrgPerson en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da02-112">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

