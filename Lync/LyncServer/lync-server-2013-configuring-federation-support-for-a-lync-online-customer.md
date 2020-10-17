---
title: 'Lync Server 2013: configuración de la compatibilidad de Federación para un cliente de Lync Online'
description: 'Lync Server 2013: configuración de la compatibilidad de Federación para un cliente de Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b5e7995e686a9492b3a4be98a92b848716cacf9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548426"
---
# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="6d842-103">Configuración de la compatibilidad de Federación para un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d842-103">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d842-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6d842-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6d842-105">Puede proporcionar servicios de comunicaciones a usuarios de la organización de cualquiera de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="6d842-105">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="6d842-106">Implemente Lync Server 2013 en su organización (conocido como *servicios locales*) y configure las cuentas de usuario de Lync 2013 en su organización.</span><span class="sxs-lookup"><span data-stu-id="6d842-106">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="6d842-107">Configuración de una cuenta de cliente de Microsoft Lync Online 2010 con un proveedor de hospedaje y configuración de cuentas de usuario con el proveedor de hospedaje (conocido como *servicios en línea*).</span><span class="sxs-lookup"><span data-stu-id="6d842-107">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="6d842-108">Si implementa Lync 2013 en su organización, puede federar a los dominios de uno o más clientes de Microsoft Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="6d842-108">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="6d842-109">Para habilitar la Federación entre los usuarios de la implementación local de Lync 2013 y los usuarios de un cliente de Lync Online 2010, debe configurar la compatibilidad con el dominio y los usuarios del cliente de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="6d842-109">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d842-110">En esta documentación solo se describen los procedimientos para configurar su organización para que admitan la Federación con un cliente de Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="6d842-110">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="6d842-111">En esta documentación no se describen los procedimientos para configurar el cliente de Lync Online 2010 para que admita la Federación.</span><span class="sxs-lookup"><span data-stu-id="6d842-111">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="6d842-112">Para obtener más información sobre los servicios de Lync Online, consulte Lync Online en <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A> .</span><span class="sxs-lookup"><span data-stu-id="6d842-112">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6d842-113">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6d842-113">In This Section</span></span>

  - [<span data-ttu-id="6d842-114">Requisitos previos para federar con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d842-114">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="6d842-115">Configurar la compatibilidad de Federación para un dominio de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d842-115">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="6d842-116">Configurar el acceso de usuario para la Federación con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d842-116">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="6d842-117">Comprobar las comunicaciones con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d842-117">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

