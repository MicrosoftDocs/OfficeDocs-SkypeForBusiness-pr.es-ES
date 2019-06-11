---
title: 'Lync Server 2013: configuración de la compatibilidad de Federación para un cliente de Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e3b1e7a325a078d4769116697f957815f02487
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="16e42-102">Configuración de la compatibilidad de Federación para un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16e42-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16e42-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="16e42-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="16e42-104">Puede proporcionar servicios de comunicaciones a los usuarios de su organización de cualquiera de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="16e42-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="16e42-105">Implementar Lync Server 2013 en su organización (conocidos como *servicios locales*) y configurar cuentas de usuario de Lync 2013 en su organización.</span><span class="sxs-lookup"><span data-stu-id="16e42-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="16e42-106">Configurar una cuenta de cliente de Microsoft Lync Online 2010 con un proveedor de hospedaje y configurar cuentas de usuario con el proveedor de hospedaje (conocido como *servicios en línea*).</span><span class="sxs-lookup"><span data-stu-id="16e42-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="16e42-107">Si implementa Lync 2013 en su organización, puede federar a los dominios de uno o varios clientes de Microsoft Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="16e42-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="16e42-108">Para habilitar la Federación entre los usuarios de la implementación local de Lync 2013 y los usuarios de un cliente de Lync Online 2010, debe configurar el soporte técnico para el dominio y los usuarios del cliente de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="16e42-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="16e42-109">Esta documentación describe solo los procedimientos para configurar su organización para que admitan la Federación con un cliente de Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="16e42-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="16e42-110">En esta documentación no se describen los procedimientos para configurar el cliente de Lync Online 2010 para que admita la Federación.</span><span class="sxs-lookup"><span data-stu-id="16e42-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="16e42-111">Para obtener más información sobre los servicios de Lync Online, <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>vea Lync Online en.</span><span class="sxs-lookup"><span data-stu-id="16e42-111">For details about Lync Online services, see Lync Online at <A href="http://go.microsoft.com/fwlink/p/?linkid=218941">http://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16e42-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="16e42-112">In This Section</span></span>

  - [<span data-ttu-id="16e42-113">Requisitos previos para la Federación con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16e42-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="16e42-114">Configurar la compatibilidad de Federación para un dominio de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16e42-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="16e42-115">Configurar el acceso de usuarios para la Federación con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16e42-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="16e42-116">Comprobar las comunicaciones con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16e42-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

