---
title: 'Lync Server 2013: Requisitos previos para habilitar la autenticación Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for enabling Kerberos authentication
ms:assetid: 3f276a21-7476-4bc0-9fd1-59e844d2e9c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425909(v=OCS.15)
ms:contentKeyID: 48183945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f405daa37007bffba1e02bd10d20d4de907e820e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-enabling-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="77f35-102">Requisitos previos para habilitar la autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77f35-102">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77f35-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="77f35-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="77f35-104">Antes de habilitar la autenticación Kerberos, asegúrese de completar todas las preparaciones de configuración y de infraestructura necesarias:</span><span class="sxs-lookup"><span data-stu-id="77f35-104">Before enabling Kerberos authentication, make sure that you complete all prerequisite configuration and infrastructure preparations:</span></span>

  - <span data-ttu-id="77f35-105">El esquema de Active Directory se extiende para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77f35-105">Active Directory schema is extended for Lync Server 2013.</span></span>

  - <span data-ttu-id="77f35-106">La preparación del bosque de Active Directory se completa para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77f35-106">Active Directory forest preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="77f35-107">La preparación del dominio de Active Directory se completa para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77f35-107">Active Directory domain preparation is completed for Lync Server 2013.</span></span>

  - <span data-ttu-id="77f35-108">El almacén de administración central se instaló correctamente y está disponible.</span><span class="sxs-lookup"><span data-stu-id="77f35-108">Central Management store is successfully installed and available.</span></span>

  - <span data-ttu-id="77f35-109">La topología se ha creado y publicado mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="77f35-109">The topology has been created and published by using Topology Builder.</span></span>

  - <span data-ttu-id="77f35-110">Servidores y roles que requieren servicios web definidos e implementados, incluidos los servidores front-end, los servidores Standard Edition y los directores.</span><span class="sxs-lookup"><span data-stu-id="77f35-110">Servers and roles that require Web Services have been defined and deployed, including Front End Servers, Standard Edition servers, and Directors.</span></span>

  - <span data-ttu-id="77f35-111">Los servicios de información de Internet (IIS) se configuran e implementan con los servicios de rol recomendados para admitir servicios web en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="77f35-111">Internet Information Services (IIS) is configured and deployed with the recommended role services to support Web Services in Lync Server 2013.</span></span>

<span data-ttu-id="77f35-112">Una vez cumplidos los requisitos previos, debe estar listo para crear una o varias cuentas para que los servicios web los usen para la autenticación Kerberos de la implementación.</span><span class="sxs-lookup"><span data-stu-id="77f35-112">After the prerequisites have been met, you should be ready to create one or more accounts for Web Services to use for Kerberos authentication for your deployment.</span></span> <span data-ttu-id="77f35-113">Como mínimo, debe crear una cuenta de autenticación Kerberos para cada implementación.</span><span class="sxs-lookup"><span data-stu-id="77f35-113">At a minimum, you need to create one Kerberos authentication account for each deployment.</span></span> <span data-ttu-id="77f35-114">Sin embargo, puede crear una cuenta para cada sitio para proporcionar autenticación Kerberos local en el sitio.</span><span class="sxs-lookup"><span data-stu-id="77f35-114">However, you can create an account for each site to provide local Kerberos authentication at the site.</span></span> <span data-ttu-id="77f35-115">Solo puede especificar una cuenta de autenticación de Kerberos por sitio.</span><span class="sxs-lookup"><span data-stu-id="77f35-115">You can only specify one Kerberos authentication account per site.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

