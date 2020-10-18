---
title: 'Lync Server 2013: requisitos previos para federar con un cliente de Lync Online'
description: 'Lync Server 2013: requisitos previos para federar con un cliente de Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99eabd4466385402d5e5983665e9349f1244348
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579866"
---
# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="99eb5-103">Requisitos previos para federar con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99eb5-103">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99eb5-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="99eb5-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="99eb5-105">Para federar con un cliente de Lync Online 2010, debe haber completado la implementación inicial y la configuración de Lync Server 2013 en su organización.</span><span class="sxs-lookup"><span data-stu-id="99eb5-105">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="99eb5-106">Esto incluye lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="99eb5-106">This includes the following:</span></span>

  - <span data-ttu-id="99eb5-107">Implementar al menos un servidor Standard Edition o un grupo de servidores front-end Enterprise Edition en la organización.</span><span class="sxs-lookup"><span data-stu-id="99eb5-107">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="99eb5-108">Para obtener más información sobre la implementación de servidores internos, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="99eb5-108">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="99eb5-109">Habilitación de cuentas de usuario internas para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99eb5-109">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="99eb5-110">Para obtener más información, vea [deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="99eb5-110">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="99eb5-111">Implementar al menos un servidor perimetral y los otros componentes necesarios para admitir el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="99eb5-111">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="99eb5-112">Para obtener más información, consulte [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="99eb5-112">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="99eb5-113">Habilitación de la compatibilidad de Federación dentro de la organización y configuración del método adecuado para controlar el acceso por parte de los dominios federados.</span><span class="sxs-lookup"><span data-stu-id="99eb5-113">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="99eb5-114">Para obtener más información, consulte [habilitar o deshabilitar el acceso de usuarios remotos en Lync server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) y [administrar los proveedores federados SIP para su organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="99eb5-114">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="99eb5-115">Habilitación del acceso de usuarios externos a los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="99eb5-115">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="99eb5-116">Para obtener más información, consulte [asignar una directiva de acceso de usuario externo a un usuario habilitado para Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) y en la documentación de implementación o de operaciones.</span><span class="sxs-lookup"><span data-stu-id="99eb5-116">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

