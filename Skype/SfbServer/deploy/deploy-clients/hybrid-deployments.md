---
title: Implementaciones híbridas del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lea este tema para obtener información sobre cómo implementar el sistema de sala de Skype en un entorno híbrido.
ms.openlocfilehash: ce57178a03a466b76edfbafdcc467d9458028845
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997296"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="22e5f-103">Implementaciones híbridas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="22e5f-103">Skype Room System hybrid deployments</span></span>
 
<span data-ttu-id="22e5f-104">Lea este tema para obtener información sobre cómo implementar el sistema de sala de Skype en un entorno híbrido.</span><span class="sxs-lookup"><span data-stu-id="22e5f-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="22e5f-105">Implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="22e5f-105">Hybrid deployments</span></span>

<span data-ttu-id="22e5f-106">Siga estos pasos si la topología tiene Skype para Business Server y Exchange Online y desea hospedar el buzón de recursos del sistema de salas de Skype en Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="22e5f-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="22e5f-107">En esta sección también se tiene en cuenta un escenario híbrido donde tiene implementado tanto Exchange Online como Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="22e5f-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="22e5f-108">Con fines ilustrativos, usamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.</span><span class="sxs-lookup"><span data-stu-id="22e5f-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="22e5f-109">Crear un buzón de recursos en el centro de administración de Exchange (LyncSample.ccsctp.net) mediante la conexión a la consola de administración de Exchange Online tal como se describe en el aprovisionamiento en línea de Exchange.</span><span class="sxs-lookup"><span data-stu-id="22e5f-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    <span data-ttu-id="22e5f-110">Puede comprobar la conectividad OWA mediante lrstest5@LyncSample.ccsctp.net para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="22e5f-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="22e5f-111">En el centro de administración de Office 365 Exchange, agregue un correo electrónico dirección lrstest5@LyncSample.com (dominio en prem) y establézcala como la dirección de respuesta.</span><span class="sxs-lookup"><span data-stu-id="22e5f-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="22e5f-112">Crear un en prem Active Directory usuario lrstest5@LyncSample.com, establezca la dirección de correo electrónico a lrstest5@LyncSample.com y establece la dirección de destino en lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="22e5f-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="22e5f-113">Desencadenar la sincronización de directorios y, una vez finalizada la sincronización, compruebe que los usuarios combinar en AAD y que no es capaz de cambiar las propiedades de los recursos del destinatario en el centro de administración de Exchange Office365.</span><span class="sxs-lookup"><span data-stu-id="22e5f-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="22e5f-114">Compruebe la conectividad OWA mediante lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="22e5f-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="22e5f-115">(Anteriormente, comprobó la conectividad de OWA con el dominio en línea).</span><span class="sxs-lookup"><span data-stu-id="22e5f-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="22e5f-p103">Después de crear el buzón, puede usar Set-CalendarProcessing en el Shell de administración de Exchange Online para configurarlo. Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="22e5f-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="22e5f-118">Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya a la consola de administración de Exchange y Enable-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-salón.</span><span class="sxs-lookup"><span data-stu-id="22e5f-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="22e5f-119">A continuación, active la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="22e5f-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="22e5f-120">Si desea alojar el buzón del sistema de salas de Skype en Exchange Online, estos pasos de Shell de administración de Exchange no son necesarios y puede continuar con el paso 6.</span><span class="sxs-lookup"><span data-stu-id="22e5f-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="22e5f-121">Habilitar la cuenta del sistema de salas de Skype para Skype para la empresa, ejecute el siguiente cmdlet en Skype para Shell de administración de negocio:</span><span class="sxs-lookup"><span data-stu-id="22e5f-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="22e5f-122">Si tiene Skype para profesionales en línea en lugar de Skype para Business Server en el escenario anterior, a continuación, después de aprovisionar el buzón de recursos de Exchange, aprovisionar un Skype para cuenta de la empresa tal como se describe en Skype para aprovisionamiento en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="22e5f-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

