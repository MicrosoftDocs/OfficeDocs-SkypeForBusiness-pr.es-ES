---
title: Implementaciones híbridas del Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lea este tema para obtener información sobre cómo implementar el sistema de salas de Skype en un entorno híbrido.
ms.openlocfilehash: 37ed625ca97ba34a30ec6f4acbabce272ef6ac50
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293623"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="720a1-103">Implementaciones híbridas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="720a1-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="720a1-104">Lea este tema para obtener información sobre cómo implementar el sistema de salas de Skype en un entorno híbrido.</span><span class="sxs-lookup"><span data-stu-id="720a1-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="720a1-105">Implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="720a1-105">Hybrid deployments</span></span>

<span data-ttu-id="720a1-106">Siga estos pasos si su topología tiene Skype empresarial Server y Exchange Online, y quiere hospedar el buzón de recursos del sistema de salas de Skype en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="720a1-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="720a1-107">En esta sección también se tiene en cuenta un escenario híbrido donde tiene implementado tanto Exchange Online como Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="720a1-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="720a1-108">Por motivos ilustrativos, usamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.</span><span class="sxs-lookup"><span data-stu-id="720a1-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="720a1-109">Para crear un buzón de recursos en el centro de administración de Exchange (LyncSample.ccsctp.net), conéctese al shell de administración de Exchange online como se describe en aprovisionamiento de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="720a1-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="720a1-110">Puede comprobar la conectividad de OWA con lrstest5@LyncSample.ccsctp.net para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="720a1-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="720a1-111">En el centro de administración de Office 365 de Exchange, agregue una dirección de correo electrónico lrstest5@LyncSample.com (dominio local) y establézcalo como la dirección de respuesta.</span><span class="sxs-lookup"><span data-stu-id="720a1-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="720a1-112">Cree una lrstest5@LyncSample.com de usuario de Active Directory local, establezca la dirección de correo electrónico en lrstest5@LyncSample.com y establezca la dirección de destino en lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="720a1-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="720a1-113">Desencadene la sincronización de directorios y, una vez completada la sincronización, compruebe que los usuarios se fusionan en AAD y que no puede cambiar las propiedades de los recursos del destinatario en el centro de administración de Exchange de Office365.</span><span class="sxs-lookup"><span data-stu-id="720a1-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="720a1-114">Comprobar la conectividad de OWA con lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="720a1-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="720a1-115">(Anteriormente, comprobó la conectividad de OWA con el dominio en línea).</span><span class="sxs-lookup"><span data-stu-id="720a1-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="720a1-p103">Después de crear el buzón, puede usar Set-CalendarProcessing en el Shell de administración de Exchange Online para configurarlo. Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="720a1-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="720a1-118">Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya al shell de administración de Exchange y habilite-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room.</span><span class="sxs-lookup"><span data-stu-id="720a1-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="720a1-119">A continuación, active la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="720a1-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="720a1-120">Si desea hospedar el buzón del sistema de Skype Room en Exchange Online, estos pasos del shell de administración de Exchange no son necesarios y puede continuar con el paso 6.</span><span class="sxs-lookup"><span data-stu-id="720a1-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="720a1-121">Habilite la cuenta del sistema de Skype Room para Skype empresarial ejecutando el siguiente cmdlet en el shell de administración de Skype empresarial:</span><span class="sxs-lookup"><span data-stu-id="720a1-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="720a1-122">Si tiene Skype empresarial online en lugar de Skype empresarial Server en el escenario anterior, después de aprovisionar el buzón de recursos de Exchange, aprovisione una cuenta de Skype empresarial, tal y como se describe en Skype empresarial online aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="720a1-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

