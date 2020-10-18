---
title: 'Lync Server 2013: requisitos previos para habilitar la autenticación Kerberos'
description: 'Lync Server 2013: requisitos previos para habilitar la autenticación Kerberos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65a45bad0eb249fdbc717fe05f080ce737c87c6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579926"
---
# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="5cf48-103">Requisitos previos para habilitar la autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5cf48-103">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cf48-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5cf48-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5cf48-105">Antes de habilitar la autenticación Kerberos, asegúrese de completar todos los preparativos de configuración y la infraestructura de requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="5cf48-105">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="5cf48-106">El esquema de Active Directory se ha ampliado para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5cf48-106">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="5cf48-107">La preparación del bosque de Active Directory se ha completado para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5cf48-107">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="5cf48-108">La preparación del dominio de Active Directory se ha completado para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5cf48-108">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="5cf48-109">El almacén de administración central se ha instalado correctamente y está disponible.</span><span class="sxs-lookup"><span data-stu-id="5cf48-109">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="5cf48-110">La topología se ha creado y publicado mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="5cf48-110">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="5cf48-111">Se han definido e implementado los servidores y roles que requieren servicios Web, incluidos los servidores front-end, los servidores Standard Edition y los directores.</span><span class="sxs-lookup"><span data-stu-id="5cf48-111">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="5cf48-112">Internet Information Services (IIS) está configurado e implementado con los servicios de rol recomendados para admitir servicios web en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5cf48-112">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="5cf48-113">Una vez cumplidos los requisitos previos, debe estar preparado para crear una o más cuentas para los servicios web que se usarán para la autenticación Kerberos en su implementación.</span><span class="sxs-lookup"><span data-stu-id="5cf48-113">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="5cf48-114">Como mínimo, es necesario crear una cuenta de autenticación Kerberos para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="5cf48-114">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="5cf48-115">Sin embargo, puede crearse una cuenta en cada sitio para proporcionar autenticación local Kerberos en el sitio.</span><span class="sxs-lookup"><span data-stu-id="5cf48-115">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="5cf48-116">Únicamente se puede especificar una sola cuenta de autenticación Kerberos por sitio.</span><span class="sxs-lookup"><span data-stu-id="5cf48-116">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

