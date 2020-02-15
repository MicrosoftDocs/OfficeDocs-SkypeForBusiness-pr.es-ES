---
title: 'Lync Server 2013: procedimientos recomendados para la infraestructura básica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd53ac85ec544af58c1f94f7397a030f6b10fdb2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="f5574-102">Procedimientos recomendados para la infraestructura básica en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5574-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5574-103">_**Última modificación del tema:** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="f5574-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="f5574-104">Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor.</span><span class="sxs-lookup"><span data-stu-id="f5574-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="f5574-105">Estas prácticas no solo benefician la infraestructura de Microsoft Lync Server 2013, sino también de toda la red.</span><span class="sxs-lookup"><span data-stu-id="f5574-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="f5574-106">Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5574-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="f5574-107">Para ayudar a proteger los servidores de la implementación de Lync Server 2013 de daños accidentales o intencionados que puedan provocar un tiempo de inactividad, adopte las siguientes precauciones:</span><span class="sxs-lookup"><span data-stu-id="f5574-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="f5574-108">Mantenga los servidores actualizados con las actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="f5574-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="f5574-109">Al suscribirse al Servicio de notificación de seguridad de Microsoft (Microsoft Security Notification Service), se garantiza que recibirá notificación inmediata de las nuevas versiones de los boletines de seguridad de los productos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f5574-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="f5574-110">Para suscribirse, vaya al sitio web de notificaciones de seguridad [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202)técnica de Microsoft en.</span><span class="sxs-lookup"><span data-stu-id="f5574-110">To subscribe, go to the Microsoft Technical Security Notifications website at [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="f5574-111">Asegúrese de que los derechos de acceso estén correctamente configurados.</span><span class="sxs-lookup"><span data-stu-id="f5574-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="f5574-p103">Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que haya un software antivirus adecuado instalado en todos los servidores. Mantenga el software actualizado con los archivos de firma de virus más recientes. Utilice la función de actualización automática de la aplicación de antivirus para mantener las firmas de virus actualizadas.</span><span class="sxs-lookup"><span data-stu-id="f5574-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="f5574-116">Le recomendamos que deshabilite los servicios del sistema operativo Windows Server que no son necesarios en los equipos en los que se instala Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f5574-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="f5574-117">Cifre los sistemas operativos y las unidades de disco en los que se encuentren almacenados los datos mediante un sistema de cifrado de todo el volumen, a menos que pueda garantizar un control constante y completo de los servidores, aislamiento físico total y la retirada correcta y segura de las unidades de disco que se sustituyan o fallen.</span><span class="sxs-lookup"><span data-stu-id="f5574-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="f5574-118">Deshabilite todos los puertos de Acceso directo a memoria (DMA) del servidor, a menos que pueda garantizar un control muy estricto del acceso físico a los servidores.</span><span class="sxs-lookup"><span data-stu-id="f5574-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="f5574-119">Los ataques basados en DMA, que pueden iniciarse de una forma muy sencilla, pueden exponer información muy confidencial, como es el caso de las claves de cifrado privadas.</span><span class="sxs-lookup"><span data-stu-id="f5574-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

