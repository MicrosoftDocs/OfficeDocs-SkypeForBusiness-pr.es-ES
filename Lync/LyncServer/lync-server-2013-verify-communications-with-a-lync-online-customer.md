---
title: 'Lync Server 2013: comprobar las comunicaciones con un cliente de Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6707139535ab30909f74b1a3fa51cce24374d09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="b92b7-102">Comprobar las comunicaciones con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b92b7-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b92b7-103">_**Última modificación del tema:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="b92b7-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="b92b7-104">Para permitir que los usuarios de la organización de Lync se comuniquen con los usuarios de un cliente de Microsoft Lync Online 2010, debe haber completado los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="b92b7-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="b92b7-105">Cumple con todos los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="b92b7-105">Met all prerequisites.</span></span> <span data-ttu-id="b92b7-106">Esto incluye implementar los servidores internos y perimetrales, habilitar la compatibilidad con la Federación de su organización y configurar cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="b92b7-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="b92b7-107">Para obtener más información, consulte [requisitos previos para federar con un cliente de Lync Online en Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="b92b7-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="b92b7-108">Compatibilidad con el acceso a dominios configurado en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b92b7-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="b92b7-109">Esto incluye la creación de una entrada de proveedor de host y la configuración de la implementación para permitir el acceso desde el dominio del cliente de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b92b7-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="b92b7-110">Para obtener más información, vea [configurar la compatibilidad de Federación para un dominio de Lync Online en Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span><span class="sxs-lookup"><span data-stu-id="b92b7-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="b92b7-111">Configuró las cuentas de usuario para admitir la Federación.</span><span class="sxs-lookup"><span data-stu-id="b92b7-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="b92b7-112">Para obtener más información, vea [configurar el acceso de usuarios para la Federación con un cliente de Lync Online en Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="b92b7-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="b92b7-113">Después de completar todos estos pasos y el administrador del cliente de Lync Online 2010 completa toda la configuración de sus servicios en línea para admitir la Federación con su organización, comprobar las comunicaciones entre una usuario de la organización y un usuario del cliente de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="b92b7-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="b92b7-114">Si la comunicación no se realiza correctamente, use la herramienta de registro de su servidor perimetral para capturar archivos de registro y de seguimiento a fin de solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="b92b7-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="b92b7-115">Para obtener información detallada sobre el uso de la herramienta registro, consulte [abrir las herramientas administrativas de Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="b92b7-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="b92b7-116">Para obtener más información sobre la herramienta de registro, consulte la documentación de la herramienta de registro de Lync [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)Server 2010 en la biblioteca de TechNet en.</span><span class="sxs-lookup"><span data-stu-id="b92b7-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

