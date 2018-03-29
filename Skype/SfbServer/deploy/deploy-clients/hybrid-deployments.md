---
title: Implementaciones híbridas del Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Lea este tema para aprender a implementar el sistema de sala de Skype en un entorno híbrido.
ms.openlocfilehash: e4ef63ec39106a2cb35201d43ca012b4ce173911
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="abc22-103">Implementaciones híbridas del Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="abc22-103">Skype Room System hybrid deployments</span></span>
 
<span data-ttu-id="abc22-104">Lea este tema para aprender a implementar el sistema de sala de Skype en un entorno híbrido.</span><span class="sxs-lookup"><span data-stu-id="abc22-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="abc22-105">Implementaciones híbridas</span><span class="sxs-lookup"><span data-stu-id="abc22-105">Hybrid deployments</span></span>

<span data-ttu-id="abc22-106">Si la topología tiene Skype para Business Server y Exchange Online y que desea alojar el buzón de recursos de sistema del sitio de Skype en Exchange Online, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="abc22-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="abc22-107">En esta sección también se tiene en cuenta un escenario híbrido donde tiene implementado tanto Exchange Online como Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="abc22-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="abc22-108">Con propósitos ilustrativos, utilizamos LyncSample.com para el dominio local y LyncSample.ccstp.net para el dominio en línea.</span><span class="sxs-lookup"><span data-stu-id="abc22-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="abc22-109">Conectando con el shell de administración de Exchange en línea, como se describe en la provisión en línea de Exchange, cree un buzón de recursos en el centro de administración de Exchange (LyncSample.ccsctp.net).</span><span class="sxs-lookup"><span data-stu-id="abc22-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    <span data-ttu-id="abc22-110">Puede comprobar la conectividad OWA usando lrstest5@LyncSample.ccsctp.net para iniciar la sesión.</span><span class="sxs-lookup"><span data-stu-id="abc22-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="abc22-111">En el centro de administración de Office 365 Exchange, agregue un correo electrónico dirección lrstest5@LyncSample.com (en prem dominio) y se establece como la dirección de respuesta.</span><span class="sxs-lookup"><span data-stu-id="abc22-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="abc22-112">Crear un sobre prem Active Directory usuario lrstest5@LyncSample.com, establezca la dirección de correo electrónico a lrstest5@LyncSample.com y establezca la dirección de destino a lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="abc22-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="abc22-113">Activar la sincronización de directorios y, una vez finalizada la sincronización, compruebe que los usuarios combinan en DAA y que no es posible cambiar las propiedades de los recursos del destinatario en el centro de administración de Exchange Office365.</span><span class="sxs-lookup"><span data-stu-id="abc22-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="abc22-114">Comprobar la conectividad OWA mediante lrstest5@LyncSample.com. (Anteriormente, usted comprobar conectividad OWA mediante el dominio en línea).</span><span class="sxs-lookup"><span data-stu-id="abc22-114">Verify OWA connectivity using lrstest5@LyncSample.com. (Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="abc22-p102">Después de crear el buzón, puede usar Set-CalendarProcessing en el Shell de administración de Exchange Online para configurarlo. Consulte los pasos 3 a 6 de Implementaciones locales de un solo bosque para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="abc22-p102">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="abc22-117">Si tiene un entorno híbrido con Exchange Server y Exchange Online, vaya a la Shell de administración de Exchange y habilitar RemoteMailbox lrstest5@LyncSample.com RemoteRoutingAddress - lrstest5@LyncSample.mail.ccsctp.net-sala.</span><span class="sxs-lookup"><span data-stu-id="abc22-117">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="abc22-118">A continuación, active la sincronización de directorios.</span><span class="sxs-lookup"><span data-stu-id="abc22-118">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="abc22-119">Si desea alojar el buzón del sistema de sala de Skype en Exchange Online, estos pasos de Shell de administración de Exchange no son necesarios y puede continuar con el paso 6.</span><span class="sxs-lookup"><span data-stu-id="abc22-119">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="abc22-120">Habilitar la cuenta de sistema del sitio de Skype de Skype para empresas ejecutando el siguiente cmdlet en Skype de Shell de administración de negocios:</span><span class="sxs-lookup"><span data-stu-id="abc22-120">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="abc22-121">Si tienes Skype para los negocios en línea en lugar de Skype para Business Server en el escenario anterior, después de crear el buzón de recursos de Exchange, aprovisionar un Skype para la cuenta de la empresa como se describe en Skype para el aprovisionamiento en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="abc22-121">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

