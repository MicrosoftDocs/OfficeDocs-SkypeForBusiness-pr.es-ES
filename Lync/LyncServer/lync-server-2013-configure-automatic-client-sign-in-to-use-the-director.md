---
title: 'Lync Server 2013: configurar el inicio de sesión automático de los clientes para usar el director'
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
ms.openlocfilehash: 634bfad77e61846528b6013b82921dfdc366f372
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="ec420-102">Configurar el inicio de sesión automático de los clientes para usar el Director en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec420-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec420-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ec420-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ec420-104">Al implementar un servidor de Lync Server 2013, director o un grupo de directores, le recomendamos que use el inicio de sesión automático de los clientes como procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="ec420-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="ec420-105">Para más información sobre cómo configurar los servidores DNS para el inicio de sesión automático de los clientes, consulte [requisitos de DNS para el inicio de sesión automático de los clientes en Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="ec420-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="ec420-106">Si ya ha implementado el inicio de sesión automático de los clientes, consulte las siguientes secciones para configurarlo en sus directores.</span><span class="sxs-lookup"><span data-stu-id="ec420-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="ec420-107">Instancia de director único</span><span class="sxs-lookup"><span data-stu-id="ec420-107">Single Director Instance</span></span>

<span data-ttu-id="ec420-108">Si ya ha implementado el inicio de sesión automático de los clientes y está apuntando a un servidor front-end o a un grupo de servidores front-end, debe cambiar el registro DNS SRV para que apunte al Director.</span><span class="sxs-lookup"><span data-stu-id="ec420-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="ec420-109">Grupo de servidores de director</span><span class="sxs-lookup"><span data-stu-id="ec420-109">Director Pool</span></span>

<span data-ttu-id="ec420-110">Si ya ha implementado el inicio de sesión automático de los clientes y está apuntando a un servidor front-end o a un grupo de servidores front-end, debe cambiar el registro DNS SRV para que apunte al grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="ec420-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

