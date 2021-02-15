---
title: Procedimientos recomendados para su infraestructura principal en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor. Estas prácticas benefician no solo la infraestructura de Skype Empresarial Server, sino también toda la red. Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Skype Empresarial Server.
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832250"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="6d13a-105">Procedimientos recomendados para su infraestructura principal en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6d13a-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="6d13a-106">Es probable que ya haya tomado las medidas necesarias para diseñar la tolerancia a errores en el sistema, mediante el uso de prácticas como garantizar la redundancia de hardware, la protección frente a interrupciones del suministro eléctrico, realizar instalaciones rutinarias de las actualizaciones de seguridad y las medidas contra virus, además de la supervisión de la actividad del servidor.</span><span class="sxs-lookup"><span data-stu-id="6d13a-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="6d13a-107">Estas prácticas benefician no solo la infraestructura de Skype Empresarial Server, sino también toda la red.</span><span class="sxs-lookup"><span data-stu-id="6d13a-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="6d13a-108">Si no ha implementado estos procedimientos, le recomendamos que lo haga antes de implementar Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6d13a-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="6d13a-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span><span class="sxs-lookup"><span data-stu-id="6d13a-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="6d13a-110">Mantenga los servidores actualizados con las actualizaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6d13a-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="6d13a-111">Al suscribirse al Servicio de notificación de seguridad de Microsoft (Microsoft Security Notification Service), se garantiza que recibirá notificación inmediata de las nuevas versiones de los boletines de seguridad de los productos de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d13a-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="6d13a-112">Para suscribirse, vaya al sitio web de notificaciones [de seguridad técnica de Microsoft.](https://go.microsoft.com/fwlink/p/?LinkId=145202)</span><span class="sxs-lookup"><span data-stu-id="6d13a-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="6d13a-113">Asegúrese de que los derechos de acceso estén correctamente configurados.</span><span class="sxs-lookup"><span data-stu-id="6d13a-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="6d13a-p104">Mantenga los servidores en un entorno físico que evite el acceso no autorizado. Asegúrese de que haya un software antivirus adecuado instalado en todos los servidores. Mantenga el software actualizado con los archivos de firma de virus más recientes. Utilice la función de actualización automática de la aplicación de antivirus para mantener las firmas de virus actualizadas.</span><span class="sxs-lookup"><span data-stu-id="6d13a-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="6d13a-118">Le recomendamos que deshabilite los servicios del sistema operativo Windows Server que no son necesarios en los equipos donde instale Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="6d13a-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="6d13a-119">Cifre los sistemas operativos y las unidades de disco en los que se encuentren almacenados los datos mediante un sistema de cifrado de todo el volumen, a menos que pueda garantizar un control constante y completo de los servidores, aislamiento físico total y la retirada correcta y segura de las unidades de disco que se sustituyan o fallen.</span><span class="sxs-lookup"><span data-stu-id="6d13a-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="6d13a-120">Deshabilite todos los puertos de Acceso directo a memoria (DMA) del servidor, a menos que pueda garantizar un control muy estricto del acceso físico a los servidores.</span><span class="sxs-lookup"><span data-stu-id="6d13a-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="6d13a-121">Los ataques basados en DMA, que pueden iniciarse de una forma muy sencilla, pueden exponer información muy confidencial, como es el caso de las claves de cifrado privadas.</span><span class="sxs-lookup"><span data-stu-id="6d13a-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

