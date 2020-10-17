---
title: 'Lync Server 2013: configurar el Sign-In de cliente automático para usar el director'
description: 'Lync Server 2013: configurar el cliente Sign-In automático para usar el director.'
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
ms.openlocfilehash: b9c45a1a677d3a30704d8dca1771ef865cef29ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546656"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="b6f4f-103">Configurar el Sign-In de cliente automático para usar el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b6f4f-103">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6f4f-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b6f4f-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b6f4f-105">Al implementar un grupo de directores o un director de Lync Server 2013, se recomienda usar el Sign-In de cliente automático como procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="b6f4f-105">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="b6f4f-106">Para más información sobre cómo configurar los servidores DNS para el inicio de sesión automático de los clientes, consulte [requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="b6f4f-106">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="b6f4f-107">Si ya ha implementado el inicio de sesión automático de los clientes, consulte las siguientes secciones para configurarlo en sus directores.</span><span class="sxs-lookup"><span data-stu-id="b6f4f-107">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="b6f4f-108">Instancia de director único</span><span class="sxs-lookup"><span data-stu-id="b6f4f-108">Single Director Instance</span></span>

<span data-ttu-id="b6f4f-109">Si ya ha implementado el cliente Sign-In automático y apunta a un servidor front-end o a un grupo de servidores front-end, debe cambiar el registro SRV de DNS para que apunte al Director.</span><span class="sxs-lookup"><span data-stu-id="b6f4f-109">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="b6f4f-110">Grupo de servidores de director</span><span class="sxs-lookup"><span data-stu-id="b6f4f-110">Director Pool</span></span>

<span data-ttu-id="b6f4f-111">Si ya ha implementado el cliente Sign-In automático y está señalando a un servidor front-end o a un grupo de servidores front-end, debe cambiar el registro DNS SRV para que apunte al grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="b6f4f-111">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

