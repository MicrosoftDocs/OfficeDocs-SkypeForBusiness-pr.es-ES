---
title: 'Lync Server 2013: Proceso de implementación para la integración de la mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6269efd85261c702c77568fac67c96034ba01a71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="a3bc0-102">Proceso de implementación para la integración de la mensajería unificada de Exchange hospedada con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3bc0-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3bc0-103">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="a3bc0-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="a3bc0-104">Una planeación eficaz para integrar Lync Server 2013 con mensajería unificada de Exchange hospedado (UM) requiere tener en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3bc0-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="a3bc0-105">Requisitos previos para integrar Lync Server 2013 con mensajería unificada de Exchange hospedado</span><span class="sxs-lookup"><span data-stu-id="a3bc0-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="a3bc0-106">Pasos necesarios durante el proceso de integración</span><span class="sxs-lookup"><span data-stu-id="a3bc0-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="a3bc0-107">Requisitos previos de implementación para la integración con mensajería unificada de Exchange hospedado</span><span class="sxs-lookup"><span data-stu-id="a3bc0-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="a3bc0-108">Antes de que pueda comenzar el proceso de integración, debe haber implementado ya Lync Server 2013 (como mínimo, un grupo de servidores front-end o un servidor Standard Edition), un servidor perimetral y clientes de Lync 2013 o Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="a3bc0-109">Proceso de integración</span><span class="sxs-lookup"><span data-stu-id="a3bc0-109">Integration Process</span></span>

<span data-ttu-id="a3bc0-110">En la tabla siguiente se ofrece información general sobre el proceso de integración de mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="a3bc0-111">Para obtener más información sobre los pasos de implementación, consulte [proporcionar a los usuarios de Lync Server 2013 correo de voz en la mensajería unificada de Exchange hospedada](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3bc0-112">Fase</span><span class="sxs-lookup"><span data-stu-id="a3bc0-112">Phase</span></span></th>
<th><span data-ttu-id="a3bc0-113">Pasos</span><span class="sxs-lookup"><span data-stu-id="a3bc0-113">Steps</span></span></th>
<th><span data-ttu-id="a3bc0-114">Derechos y permisos</span><span class="sxs-lookup"><span data-stu-id="a3bc0-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="a3bc0-115">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="a3bc0-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3bc0-116">Configurar el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a3bc0-117">Configure el servidor perimetral para la federación.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="a3bc0-118">Replicar manualmente los datos en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="a3bc0-119">Configure el proveedor de hospedaje en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a3bc0-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a3bc0-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a3bc0-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurar el servidor perimetral para la integración con la mensajería unificada de Exchange hospedada</a></span><span class="sxs-lookup"><span data-stu-id="a3bc0-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bc0-122">Configurar la Directiva de correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a3bc0-123">Modifique la Directiva de correo de voz hospedado global o cree una nueva Directiva de correo de voz hospedada con ámbito de sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="a3bc0-124">Para las directivas con ámbito por usuario, asigne la Directiva a los usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a3bc0-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="a3bc0-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="a3bc0-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Administrar directivas de correo de voz hospedado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3bc0-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bc0-127">Habilitar a los usuarios para el correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="a3bc0-128">Configure cuentas de usuario para los usuarios cuyos buzones estén en un servicio de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="a3bc0-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a3bc0-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a3bc0-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Habilitar a los usuarios para el correo de voz hospedado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3bc0-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bc0-131">Configurar objetos de contacto hospedados.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="a3bc0-132">Crear objetos de contacto de operador automático para mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="a3bc0-133">Crear objetos de contacto de acceso de suscriptores para mensajería unificada de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="a3bc0-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a3bc0-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="a3bc0-135">Para crear, modificar o quitar objetos de contacto, el usuario que ejecuta el cmdlet New-CsExUmContact, Set-CsExUmContact o Remove-CsExUmContact debe tener el permiso correcto para la unidad organizativa de Active Directory donde se almacenan los nuevos objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="a3bc0-136">Este permiso se puede conceder si se ejecuta el cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="a3bc0-137">Para obtener más información, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a3bc0-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="a3bc0-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Crear objetos de contacto para la mensajería unificada de Exchange hospedada en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="a3bc0-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

