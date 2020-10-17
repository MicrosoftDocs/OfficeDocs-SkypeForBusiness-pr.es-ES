---
title: 'Lync Server 2013: proceso de implementación para integrar la mensajería unificada de Exchange hospedada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68ae12ee384a78acd8c5c390715b05791b7a0df8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522597"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="0e106-102">Proceso de implementación para integrar la mensajería unificada de Exchange hospedada con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e106-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e106-103">_**Última modificación del tema:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="0e106-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="0e106-104">La planeación eficaz para la integración de Lync Server 2013 con mensajería unificada (UM) hospedada de Exchange requiere que tenga en cuenta lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e106-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="0e106-105">Requisitos previos para integrar Lync Server 2013 con mensajería unificada de Exchange hospedada</span><span class="sxs-lookup"><span data-stu-id="0e106-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="0e106-106">Los pasos necesarios durante el proceso de integración</span><span class="sxs-lookup"><span data-stu-id="0e106-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="0e106-107">Requisitos previos de implementación para la integración con la mensajería unificada hospedada de Exchange</span><span class="sxs-lookup"><span data-stu-id="0e106-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="0e106-108">Para poder iniciar el proceso de integración, debe haber implementado ya Lync Server 2013 (como mínimo, un grupo de servidores front-end o un servidor Standard Edition), un servidor perimetral y clientes de Lync 2013 o Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="0e106-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="0e106-109">Proceso de integración</span><span class="sxs-lookup"><span data-stu-id="0e106-109">Integration Process</span></span>

<span data-ttu-id="0e106-110">En la tabla siguiente se proporciona información general del proceso de integración de mensajería unificada hospedada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e106-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="0e106-111">Para obtener más información sobre los pasos de implementación, vea el documento sobre cómo [suministrar Lync Server 2013 usuarios de voz en la mensajería unificada de Exchange hospedada](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="0e106-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0e106-112">Fase</span><span class="sxs-lookup"><span data-stu-id="0e106-112">Phase</span></span></th>
<th><span data-ttu-id="0e106-113">Pasos</span><span class="sxs-lookup"><span data-stu-id="0e106-113">Steps</span></span></th>
<th><span data-ttu-id="0e106-114">Derechos y permisos</span><span class="sxs-lookup"><span data-stu-id="0e106-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="0e106-115">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="0e106-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0e106-116">Configurar el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0e106-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0e106-117">Configure el servidor perimetral para la federación.</span><span class="sxs-lookup"><span data-stu-id="0e106-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="0e106-118">Replique manualmente los datos al servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0e106-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="0e106-119">Configure el proveedor de hospedaje en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="0e106-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0e106-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0e106-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0e106-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configurar el servidor perimetral para la integración con mensajería unificada de Exchange hospedada</a></span><span class="sxs-lookup"><span data-stu-id="0e106-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e106-122">Configurar la directiva de correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="0e106-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0e106-123">Modifique la directiva global de correo de voz hospedado o cree una directiva de correo de voz hospedado con ámbito de sitio o por usuario.</span><span class="sxs-lookup"><span data-stu-id="0e106-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="0e106-124">Para las directivas con ámbito por usuario, asigne la directiva a usuarios o grupos.</span><span class="sxs-lookup"><span data-stu-id="0e106-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0e106-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0e106-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="0e106-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Administrar directivas de correo de voz hospedado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0e106-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0e106-127">Habilitar a los usuarios para correo de voz hospedado.</span><span class="sxs-lookup"><span data-stu-id="0e106-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0e106-128">Configure cuentas de usuario para los usuarios cuyos buzones de correo se encuentren en un servicio de Exchange hospedado.</span><span class="sxs-lookup"><span data-stu-id="0e106-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="0e106-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0e106-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="0e106-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Habilitar a los usuarios para el correo de voz hospedado en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0e106-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0e106-131">Configurar objetos de contacto hospedados.</span><span class="sxs-lookup"><span data-stu-id="0e106-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="0e106-132">Cree objetos de contacto de operador automático para la mensajería unificada hospedada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e106-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="0e106-133">Cree objetos de contacto de acceso de suscriptor para la mensajería unificada hospedada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0e106-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0e106-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0e106-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0e106-135">Para crear, modificar o quitar objetos de contacto, el usuario que ejecuta el cmdlet New-CsExUmContact, Set-CsExUmContact o Remove-CsExUmContact debe tener el permiso correcto para la unidad organizativa de Active Directory donde están almacenados los nuevos objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="0e106-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="0e106-136">Este permiso se obtiene si se ejecuta el cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="0e106-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="0e106-137">Para obtener más información, vea la documentación referente a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="0e106-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="0e106-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Crear objetos de contacto para la mensajería unificada de Exchange hospedada en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0e106-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

