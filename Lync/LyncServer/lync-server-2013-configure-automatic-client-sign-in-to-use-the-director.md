---
title: 'Lync Server 2013: configurar el Sign-In de cliente automático para usar el director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e174e55a2564dcf60b0405819e2996e4bf3d8f95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522967"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="89e1c-102">Configurar el Sign-In de cliente automático para usar el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89e1c-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89e1c-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="89e1c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="89e1c-104">Al implementar un grupo de directores o un director de Lync Server 2013, se recomienda usar el Sign-In de cliente automático como procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="89e1c-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="89e1c-105">Para más información sobre cómo configurar los servidores DNS para el inicio de sesión automático de los clientes, consulte [requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="89e1c-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="89e1c-106">Si ya ha implementado el inicio de sesión automático de los clientes, consulte las siguientes secciones para configurarlo en sus directores.</span><span class="sxs-lookup"><span data-stu-id="89e1c-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="89e1c-107">Instancia de director único</span><span class="sxs-lookup"><span data-stu-id="89e1c-107">Single Director Instance</span></span>

<span data-ttu-id="89e1c-108">Si ya ha implementado el cliente Sign-In automático y apunta a un servidor front-end o a un grupo de servidores front-end, debe cambiar el registro SRV de DNS para que apunte al Director.</span><span class="sxs-lookup"><span data-stu-id="89e1c-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="89e1c-109">Grupo de servidores de director</span><span class="sxs-lookup"><span data-stu-id="89e1c-109">Director Pool</span></span>

<span data-ttu-id="89e1c-110">Si ya ha implementado el cliente Sign-In automático y está señalando a un servidor front-end o a un grupo de servidores front-end, debe cambiar el registro DNS SRV para que apunte al grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="89e1c-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

