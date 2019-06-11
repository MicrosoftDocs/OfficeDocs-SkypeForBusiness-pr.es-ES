---
title: 'Lync Server 2013: requisitos previos para la Federación con un cliente de Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af3db1918e2d347084f1bbdcdf5ea4eb92ae8d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="fd467-102">Requisitos previos para la Federación con un cliente de Lync Online en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd467-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd467-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="fd467-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="fd467-104">Para federarse a un cliente de Lync Online 2010, ya debe haber completado la implementación inicial y la configuración de Lync Server 2013 en su organización.</span><span class="sxs-lookup"><span data-stu-id="fd467-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="fd467-105">Entre estas directivas se incluyen:</span><span class="sxs-lookup"><span data-stu-id="fd467-105">This includes the following:</span></span>

  - <span data-ttu-id="fd467-106">Implementar al menos un servidor Standard Edition o un grupo de servidores front-end Enterprise Edition en la organización.</span><span class="sxs-lookup"><span data-stu-id="fd467-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="fd467-107">Para obtener detalles sobre la implementación de servidores internos, consulte [implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="fd467-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="fd467-108">Habilitar cuentas de usuario internas para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fd467-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="fd467-109">Para obtener más información, vea [deshabilitar o volver a habilitar la cuenta de usuario para Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="fd467-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="fd467-110">Implementar al menos un servidor perimetral y los otros componentes necesarios para admitir el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="fd467-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="fd467-111">Para obtener más información, vea [administrar la Federación y el acceso externo a Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="fd467-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="fd467-112">Habilitar la compatibilidad de Federación dentro de su organización y configurar el método adecuado para controlar el acceso por parte de los dominios federados.</span><span class="sxs-lookup"><span data-stu-id="fd467-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="fd467-113">Para obtener más información, vea [habilitar o deshabilitar el acceso de usuarios remotos en Lync server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) y [administrar proveedores federados SIP para su organización en Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="fd467-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="fd467-114">Habilitar el acceso de usuarios externos a los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="fd467-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="fd467-115">Para obtener más información, consulte [asignar una directiva de acceso de usuarios externos a un usuario habilitado de Lync en Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) y en la documentación de implementación o de operaciones.</span><span class="sxs-lookup"><span data-stu-id="fd467-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

