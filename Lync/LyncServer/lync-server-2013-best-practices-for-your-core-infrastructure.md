---
title: 'Lync Server 2013: procedimientos recomendados para su infraestructura básica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb6e12f6f2c6d66a0d4f5fed17bc01dc250db5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="3d610-102">Procedimientos recomendados para su infraestructura básica en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d610-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d610-103">_**Última modificación del tema:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="3d610-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="3d610-104">Es probable que ya haya tomado las medidas para diseñar la tolerancia a errores en el sistema, con prácticas tales como garantizar la redundancia de hardware, protegerse contra la pérdida de energía, instalar de forma rutinaria actualizaciones de seguridad y medidas antivirus, y supervisar la actividad del servidor.</span><span class="sxs-lookup"><span data-stu-id="3d610-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="3d610-105">Estas prácticas no solo benefician la infraestructura de Microsoft Lync Server 2013, sino también de toda la red.</span><span class="sxs-lookup"><span data-stu-id="3d610-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="3d610-106">Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d610-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="3d610-107">Para ayudar a proteger los servidores de su implementación de Lync Server 2013 de daños accidentales o intencionados que pueden dar lugar a un tiempo de inactividad, tome las siguientes precauciones:</span><span class="sxs-lookup"><span data-stu-id="3d610-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="3d610-108">Mantenga sus servidores al día con las actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="3d610-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="3d610-109">Suscribirse al servicio de notificaciones de seguridad de Microsoft le ayuda a recibir notificaciones inmediatas de versiones de boletines de seguridad para cualquier producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3d610-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="3d610-110">Para suscribirse, vaya al sitio web de notificaciones de seguridad [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)técnica de Microsoft en.</span><span class="sxs-lookup"><span data-stu-id="3d610-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="3d610-111">Asegúrese de que los derechos de acceso están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="3d610-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="3d610-112">Mantenga los servidores en un entorno físico que evite el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="3d610-112">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="3d610-113">Asegúrese de que el software antivirus adecuado esté instalado en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="3d610-113">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="3d610-114">Mantenga el software actualizado con los últimos archivos de firma de virus.</span><span class="sxs-lookup"><span data-stu-id="3d610-114">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="3d610-115">Use la característica de actualización automática de su aplicación antivirus para mantener actualizadas las firmas de virus.</span><span class="sxs-lookup"><span data-stu-id="3d610-115">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="3d610-116">Le recomendamos que deshabilite los servicios del sistema operativo Windows Server que no son necesarios en los equipos en los que instala Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3d610-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="3d610-117">Cifre los sistemas operativos y las unidades de disco en los que los datos se almacenan con un sistema de cifrado de volumen completo, a menos que pueda garantizar un control completo y constante de los servidores, el aislamiento físico total y la retirada correcta y segura de disco reemplazado o fallido discos.</span><span class="sxs-lookup"><span data-stu-id="3d610-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="3d610-118">Deshabilite todos los puertos de acceso directo a memoria (DMA) externos del servidor, a menos que pueda garantizar un control muy estricto sobre el acceso físico a los servidores.</span><span class="sxs-lookup"><span data-stu-id="3d610-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="3d610-119">Los ataques basados en DMA, que se pueden iniciar con bastante facilidad, pueden exponer información muy confidencial, como las claves de cifrado privadas.</span><span class="sxs-lookup"><span data-stu-id="3d610-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

