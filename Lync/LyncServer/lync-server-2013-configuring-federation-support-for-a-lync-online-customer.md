---
title: 'Lync Server 2013: configuración de la compatibilidad de Federación para un cliente de Lync Online'
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
ms.openlocfilehash: f25a2ba7735c8ccf135d2030e7853940ef545ac2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="bf1ca-102">Configuración de la compatibilidad de Federación para un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf1ca-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf1ca-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bf1ca-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bf1ca-104">Puede proporcionar servicios de comunicaciones a usuarios de la organización de cualquiera de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="bf1ca-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="bf1ca-105">Implemente Lync Server 2013 en su organización (conocido como *servicios locales*) y configure las cuentas de usuario de Lync 2013 en su organización.</span><span class="sxs-lookup"><span data-stu-id="bf1ca-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="bf1ca-106">Configuración de una cuenta de cliente de Microsoft Lync Online 2010 con un proveedor de hospedaje y configuración de cuentas de usuario con el proveedor de hospedaje (conocido como *servicios en línea*).</span><span class="sxs-lookup"><span data-stu-id="bf1ca-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="bf1ca-107">Si implementa Lync 2013 en su organización, puede federar a los dominios de uno o más clientes de Microsoft Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="bf1ca-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="bf1ca-108">Para habilitar la Federación entre los usuarios de la implementación local de Lync 2013 y los usuarios de un cliente de Lync Online 2010, debe configurar la compatibilidad con el dominio y los usuarios del cliente de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="bf1ca-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bf1ca-109">En esta documentación solo se describen los procedimientos para configurar su organización para que admitan la Federación con un cliente de Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="bf1ca-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="bf1ca-110">En esta documentación no se describen los procedimientos para configurar el cliente de Lync Online 2010 para que admita la Federación.</span><span class="sxs-lookup"><span data-stu-id="bf1ca-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="bf1ca-111">Para obtener más información sobre los servicios de Lync Online, <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>consulte Lync Online en.</span><span class="sxs-lookup"><span data-stu-id="bf1ca-111">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bf1ca-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bf1ca-112">In This Section</span></span>

  - [<span data-ttu-id="bf1ca-113">Requisitos previos para federar con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf1ca-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="bf1ca-114">Configurar la compatibilidad de Federación para un dominio de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf1ca-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="bf1ca-115">Configurar el acceso de usuario para la Federación con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf1ca-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="bf1ca-116">Comprobar las comunicaciones con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf1ca-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

