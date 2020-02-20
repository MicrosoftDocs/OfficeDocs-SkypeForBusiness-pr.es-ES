---
title: 'Lync Server 2013: pasos para preparar e implementar el entorno híbrido de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Steps to prepare and deploy Lync Server 2013 hybrid environment
ms:assetid: a50d4f7b-63f4-4663-af63-56ca87e4e3e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205157(v=OCS.15)
ms:contentKeyID: 48185060
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24a6d816f2f50c36694317f442cc79d06f077ef0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="steps-to-prepare-and-deploy-lync-server-2013-hybrid-environment"></a><span data-ttu-id="9e250-102">Pasos para preparar e implementar el entorno híbrido de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e250-102">Steps to prepare and deploy Lync Server 2013 hybrid environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e250-103">_**Última modificación del tema:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="9e250-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="9e250-104">En la siguiente tabla se enumeran los pasos necesarios para preparar el entorno para una implementación híbrida con Skype empresarial online y Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e250-104">The following table lists the steps required to prepare your environment for a hybrid deployment with Skype for Business Online and Microsoft Office 365.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e250-105">¿Completado?</span><span class="sxs-lookup"><span data-stu-id="9e250-105">Completed?</span></span></th>
<th><span data-ttu-id="9e250-106">Paso</span><span class="sxs-lookup"><span data-stu-id="9e250-106">Step</span></span></th>
<th><span data-ttu-id="9e250-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e250-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9e250-108">Crear una cuenta de inquilino para Office 365 y habilitar Lync Online</span><span class="sxs-lookup"><span data-stu-id="9e250-108">Create a tenant account for Office 365 and enable Lync Online</span></span></p></td>
<td><p><span data-ttu-id="9e250-109">Obtenga información sobre Office 365 y Lync Online en <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="9e250-109">Learn about Office 365 and Lync Online at <a href="https://go.microsoft.com/fwlink/p/?linkid=254980">Office 365</a>.</span></span></p>
<p><span data-ttu-id="9e250-110">Para asegurarse de que su entorno está listo para Office 365, consulte los <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">requisitos del sistema</a>.</span><span class="sxs-lookup"><span data-stu-id="9e250-110">To make sure that your environment is ready for Office 365, see the <a href="https://go.microsoft.com/fwlink/p/?linkid=401408">System Requirements</a>.</span></span></p>
<p><span data-ttu-id="9e250-111">Para obtener más información sobre cómo configurar Office 365, vea <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Introducción a office 365</a> y <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">configurar Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="9e250-111">For details about setting up Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254982">Getting Started with Office 365</a> and <a href="https://go.microsoft.com/fwlink/p/?linkid=254979">Set Up Office 365</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9e250-112">Agregar el dominio y comprobar la propiedad</span><span class="sxs-lookup"><span data-stu-id="9e250-112">Add your domain and verify ownership</span></span></p></td>
<td><p><span data-ttu-id="9e250-113">A veces, su dominio también se conoce como su <em>dominio</em>personal.</span><span class="sxs-lookup"><span data-stu-id="9e250-113">Your domain is sometimes also referred to as your <em>vanity domain</em>.</span></span> <span data-ttu-id="9e250-114">Debe agregar el dominio a su inquilino de Office 365 y, a continuación, seguir los pasos para validar el dominio con Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e250-114">You must add your domain to your Office 365 tenant, and then follow the steps to validate the domain with Office 365.</span></span> <span data-ttu-id="9e250-115">Esto es para confirmar que es el propietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="9e250-115">This is to confirm that you are the owner of the domain.</span></span></p>
<p><span data-ttu-id="9e250-116">Para agregar su dominio a su inquilino de Office 365, siga los pasos descritos en <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Agregar un dominio a office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="9e250-116">To add your domain to your Office 365 tenant, follow the steps described at <a href="https://go.microsoft.com/fwlink/p/?linkid=254983">Add your domain to Office 365</a>.</span></span></p>
<p><span data-ttu-id="9e250-117">Complete todos los pasos de cada sección del tema, incluida &quot;editar registros DNS para los servicios de Office 365.&quot;</span><span class="sxs-lookup"><span data-stu-id="9e250-117">Complete all of the steps in each section in the topic, including &quot;Edit DNS records for your Office 365 services.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9e250-118">Comprobar la preparación del entorno</span><span class="sxs-lookup"><span data-stu-id="9e250-118">Verify environment readiness</span></span></p></td>
<td><p><span data-ttu-id="9e250-119">Puede usar el Asistente para la instalación de Office 365 para ayudarle a implementar Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e250-119">You can use the Office 365 Setup Assistant to help you deploy Office 365.</span></span> <span data-ttu-id="9e250-120">Para obtener más información, vea <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">usar el Asistente para la instalación para determinar la preparación de Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="9e250-120">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=254985">Use Setup Assistant to determine Office 365 readiness</a>.</span></span></p>
<p><span data-ttu-id="9e250-121">Para más detalles sobre el uso de la herramienta y la implementación de Office 365, consulte la <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Guía de implementación de office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="9e250-121">For details about using the tool and deploying Office 365, see <a href="https://go.microsoft.com/fwlink/p/?linkid=257337">Office 365 deployment guide</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9e250-122">Preparar la sincronización de Active Directory</span><span class="sxs-lookup"><span data-stu-id="9e250-122">Prepare for Active Directory synchronization</span></span></p></td>
<td><p><span data-ttu-id="9e250-123">La sincronización de Active Directory mantiene su Active Directory local sincronizado permanentemente con Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e250-123">Active Directory synchronization keeps your on-premises Active Directory continuously synchronized with Office 365.</span></span> <span data-ttu-id="9e250-124">Esto le permite crear versiones sincronizadas de cada grupo y cuenta de usuario, además de habilitar la sincronización de la lista global de direcciones (GAL) de su entorno local de Microsoft Exchange Server a Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9e250-124">This lets you create synchronized versions of each user account and group, and also enables global address list (GAL) synchronization from your local Microsoft Exchange Server environment to Microsoft Exchange Online.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="9e250-125">Debe sincronizar las cuentas de AD para todos los usuarios de Lync de la organización entre las implementaciones locales y en línea de Lync, incluso si los usuarios no se mueven a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9e250-125">You need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="9e250-126">Si no sincroniza todos los usuarios, es posible que la comunicación entre los usuarios locales y en línea de su organización no funcione según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="9e250-126">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>


</div>
<p><span data-ttu-id="9e250-127">Para preparar el entorno para la sincronización de Active Directory, siga los pasos que se describen en <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Guía básica de sincronización de directorios</a>, incluida la configuración del inicio de sesión único.</span><span class="sxs-lookup"><span data-stu-id="9e250-127">To prepare your environment for Active Directory synchronization, follow the steps described in <a href="https://go.microsoft.com/fwlink/p/?linkid=254988">Directory synchronization Roadmap</a>, including setting up single sign-on.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9e250-128">Crear certificados para los servicios de Federación de Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="9e250-128">Create certificates for Active Directory Federation Services (AD FS)</span></span></p></td>
<td><p><span data-ttu-id="9e250-129">Tendrá que crear los certificados que se usan para la Federación de identidades con Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e250-129">You will need to create the certificates that are used for identity federation with Office 365.</span></span> <span data-ttu-id="9e250-130">Para obtener más información, consulte la sección "certificados de servidor de Federación" del tema Plan for and Deploy AD FS for use with Single Sign-on en la <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">lista de comprobación: Use AD FS para implementar y administrar el inicio de sesión único</a>.</span><span class="sxs-lookup"><span data-stu-id="9e250-130">For more information, see the “Federation server certificates” section of the Plan for and deploy AD FS for use with single sign-on topic at <a href="https://go.microsoft.com/fwlink/p/?linkid=285376">Checklist: Use AD FS to implement and manage single sign-on</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9e250-131">Asignar certificados para AD FS</span><span class="sxs-lookup"><span data-stu-id="9e250-131">Assign certificates for AD FS</span></span></p></td>
<td><p><span data-ttu-id="9e250-132">Después de crear los certificados que se usan para la Federación de identidades con Office 365, debe instalarlos y asignarlos.</span><span class="sxs-lookup"><span data-stu-id="9e250-132">After you create the certificates that are used for identity federation with Office 365, you must install and assign them.</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="9e250-133">Mover los usuarios piloto a Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="9e250-133">Move pilot users to Skype for Business Online</span></span></p></td>
<td><p><span data-ttu-id="9e250-134">Una vez que haya completado los pasos para preparar y configurar el entorno para Skype empresarial online, puede empezar a mover los usuarios piloto a Lync Online.</span><span class="sxs-lookup"><span data-stu-id="9e250-134">After you have completed the steps to prepare and configure your environment for Skype for Business Online, you can start moving pilot users to Lync Online.</span></span></p>
<p><span data-ttu-id="9e250-135">Consulte <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="9e250-135">See <a href="lync-server-2013-move-users-to-lync-online.md">Move users to Lync Online in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td></td>
<td><p><span data-ttu-id="9e250-136">Administración de usuarios en una implementación híbrida</span><span class="sxs-lookup"><span data-stu-id="9e250-136">Administering users in a hybrid deployment</span></span></p></td>
<td><p><span data-ttu-id="9e250-137">Para obtener más información sobre cómo administrar usuarios en una implementación híbrida, vea <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a Hybrid Lync Server 2013 Deployment</a>.</span><span class="sxs-lookup"><span data-stu-id="9e250-137">For details about how to administer users in a hybrid deployment, see <a href="lync-server-2013-administering-users-in-a-hybrid-deployment.md">Administering users in a hybrid Lync Server 2013 deployment</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

