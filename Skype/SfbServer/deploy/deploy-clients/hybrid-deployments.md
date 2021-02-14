---
title: Implementaciones híbridas del Sistema de sala de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno híbrido.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805900"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="eb5b0-103">Implementaciones híbridas del Sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="eb5b0-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="eb5b0-104">Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno híbrido.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="eb5b0-105">Implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="eb5b0-105">Hybrid deployments</span></span>

<span data-ttu-id="eb5b0-106">Siga estos pasos si su topología tiene Skype Empresarial Server y Exchange Online, y desea hospedar el buzón de recursos del Sistema de sala de Skype en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="eb5b0-107">En esta sección también se describe un escenario híbrido en el que se han implementado Exchange Online Exchange Server implementación.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="eb5b0-108">Para fines ilustrativos, usamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="eb5b0-109">Cree un buzón de recursos en el Centro de administración de Exchange (LyncSample.ccsctp.net) conectándose al Shell de administración de Exchange Online, tal como se describe en Aprovisionamiento de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="eb5b0-110">Puede comprobar la conectividad de OWA mediante lrstest5@LyncSample.ccsctp.net para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="eb5b0-111">En el Centro de administración de Microsoft 365 u Office 365 Exchange, agregue una dirección de correo electrónico lrstest5@LyncSample.com (dominio local) y estacúla como la dirección de respuesta.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="eb5b0-112">Cree un usuario local de Active Directory lrstest5@LyncSample.com, establezca la dirección de correo electrónico en lrstest5@LyncSample.com y establezca la dirección de destino en lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="eb5b0-113">Desencadene la sincronización de directorios y, una vez completada la sincronización, compruebe que los usuarios se combinan en AAD y que no puede cambiar las propiedades de los recursos del destinatario en el Centro de administración de Microsoft 365 u Office 365 Exchange.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="eb5b0-114">Compruebe la conectividad de OWA mediante lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="eb5b0-115">(Anteriormente, ha comprobado la conectividad de OWA con el dominio en línea).</span><span class="sxs-lookup"><span data-stu-id="eb5b0-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="eb5b0-116">Después de crear el buzón, puede usar Set-CalendarProcessing en el Shell de administración de Exchange Online para configurar el buzón.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="eb5b0-117">Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="eb5b0-118">Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya al Shell de administración de Exchange y Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="eb5b0-119">A continuación, desencadene la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="eb5b0-120">Si desea hospedar el buzón del Sistema de sala de Skype en Exchange Online, estos pasos del Shell de administración de Exchange no son necesarios y puede continuar con el paso 6.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="eb5b0-121">Habilite la cuenta del Sistema de sala de Skype para Skype Empresarial ejecutando el siguiente cmdlet en el Shell de administración de Skype Empresarial:</span><span class="sxs-lookup"><span data-stu-id="eb5b0-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="eb5b0-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span><span class="sxs-lookup"><span data-stu-id="eb5b0-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

