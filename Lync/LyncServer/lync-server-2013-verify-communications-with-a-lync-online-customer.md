---
title: 'Lync Server 2013: comprobar las comunicaciones con un cliente de Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0269c66ad88f7be7f34874a8e4370fb65b954ccf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518667"
---
# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="89e2f-102">Comprobar las comunicaciones con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89e2f-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89e2f-103">_**Última modificación del tema:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="89e2f-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="89e2f-104">Para permitir que los usuarios de Lync de su organización se comuniquen con los usuarios de un cliente de Microsoft Lync Online 2010, debe haber completado los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="89e2f-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="89e2f-105">Reunir todos los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="89e2f-105">Met all prerequisites.</span></span> <span data-ttu-id="89e2f-106">Este paso incluye implementar los servidores internos y perimetrales, habilitar la compatibilidad con federación para la organización, y configurar cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="89e2f-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="89e2f-107">Para obtener más información, consulte [requisitos previos para federar con un cliente de Lync Online en Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="89e2f-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="89e2f-108">Configurar compatibilidad con acceso a dominio en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="89e2f-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="89e2f-109">Esto incluye la creación de una entrada de proveedor de host y la configuración de la implementación para permitir el acceso desde el dominio del cliente de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="89e2f-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="89e2f-110">Para obtener más información, consulte [configurar la compatibilidad con la Federación para un dominio de Lync Online en Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span><span class="sxs-lookup"><span data-stu-id="89e2f-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="89e2f-111">Configurar sus cuentas de usuario para admitir federación.</span><span class="sxs-lookup"><span data-stu-id="89e2f-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="89e2f-112">Para obtener más información, consulte [configurar el acceso de usuario para la Federación con un cliente de Lync Online en Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="89e2f-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="89e2f-113">Después de completar todos estos pasos y el administrador del cliente de Lync Online 2010 completa toda la configuración de sus servicios en línea para admitir la Federación con su organización, compruebe las comunicaciones probando las comunicaciones entre un usuario interno de la organización y un usuario del cliente de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="89e2f-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="89e2f-114">Si la comunicación no se realiza correctamente, use la herramienta de registro del servidor perimetral para capturar los archivos de registro y de seguimiento con el fin de solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="89e2f-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="89e2f-115">Para obtener más información sobre el uso de la herramienta de registro, consulte [Open Lync Server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="89e2f-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="89e2f-116">Para obtener más información sobre la herramienta de registro, vea la documentación de la herramienta de registro de Lync Server 2010 en la biblioteca de TechNet en [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) .</span><span class="sxs-lookup"><span data-stu-id="89e2f-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

