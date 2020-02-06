---
title: Procedimientos recomendados para su infraestructura básica en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Es probable que ya haya tomado las medidas para diseñar la tolerancia a errores en el sistema, con prácticas tales como garantizar la redundancia de hardware, protegerse contra la pérdida de energía, instalar de forma rutinaria actualizaciones de seguridad y medidas antivirus, y supervisar la actividad del servidor. Estas prácticas no solo benefician su infraestructura de servidor de Skype empresarial, sino también de toda la red. Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Skype empresarial Server.
ms.openlocfilehash: 62200fc1ac45e1d647761af24d176a00d18693e4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815688"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="ae15c-105">Procedimientos recomendados para su infraestructura básica en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="ae15c-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="ae15c-106">Es probable que ya haya tomado las medidas para diseñar la tolerancia a errores en el sistema, con prácticas tales como garantizar la redundancia de hardware, protegerse contra la pérdida de energía, instalar de forma rutinaria actualizaciones de seguridad y medidas antivirus, y supervisar la actividad del servidor.</span><span class="sxs-lookup"><span data-stu-id="ae15c-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="ae15c-107">Estas prácticas no solo benefician su infraestructura de servidor de Skype empresarial, sino también de toda la red.</span><span class="sxs-lookup"><span data-stu-id="ae15c-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="ae15c-108">Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae15c-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="ae15c-109">Para ayudar a proteger los servidores de su implementación de Skype empresarial Server de daños accidentales o intencionados que puedan dar lugar a un tiempo de inactividad, tome las siguientes precauciones:</span><span class="sxs-lookup"><span data-stu-id="ae15c-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="ae15c-110">Mantenga sus servidores al día con las actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ae15c-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="ae15c-111">Suscribirse al servicio de notificaciones de seguridad de Microsoft le ayuda a recibir notificaciones inmediatas de versiones de boletines de seguridad para cualquier producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ae15c-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="ae15c-112">Para suscribirse, vaya al [sitio web de notificaciones de seguridad técnica de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span><span class="sxs-lookup"><span data-stu-id="ae15c-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="ae15c-113">Asegúrese de que los derechos de acceso están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae15c-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="ae15c-114">Mantenga los servidores en un entorno físico que evite el acceso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="ae15c-114">Keep your servers in a physical environment that prevents unauthorized access.</span></span> <span data-ttu-id="ae15c-115">Asegúrese de que el software antivirus adecuado esté instalado en todos los servidores.</span><span class="sxs-lookup"><span data-stu-id="ae15c-115">Ensure that adequate antivirus software is installed on all your servers.</span></span> <span data-ttu-id="ae15c-116">Mantenga el software actualizado con los últimos archivos de firma de virus.</span><span class="sxs-lookup"><span data-stu-id="ae15c-116">Keep the software up-to-date with the latest virus signature files.</span></span> <span data-ttu-id="ae15c-117">Use la característica de actualización automática de su aplicación antivirus para mantener actualizadas las firmas de virus.</span><span class="sxs-lookup"><span data-stu-id="ae15c-117">Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="ae15c-118">Le recomendamos que deshabilite los servicios del sistema operativo Windows Server que no son necesarios en los equipos en los que instala Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="ae15c-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="ae15c-119">Cifre los sistemas operativos y las unidades de disco en los que los datos se almacenan con un sistema de cifrado de volumen completo, a menos que pueda garantizar un control completo y constante de los servidores, el aislamiento físico total y la retirada correcta y segura de disco reemplazado o fallido discos.</span><span class="sxs-lookup"><span data-stu-id="ae15c-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="ae15c-120">Deshabilite todos los puertos de acceso directo a memoria (DMA) externos del servidor, a menos que pueda garantizar un control muy estricto sobre el acceso físico a los servidores.</span><span class="sxs-lookup"><span data-stu-id="ae15c-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="ae15c-121">Los ataques basados en DMA, que se pueden iniciar con bastante facilidad, pueden exponer información muy confidencial, como las claves de cifrado privadas.</span><span class="sxs-lookup"><span data-stu-id="ae15c-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

