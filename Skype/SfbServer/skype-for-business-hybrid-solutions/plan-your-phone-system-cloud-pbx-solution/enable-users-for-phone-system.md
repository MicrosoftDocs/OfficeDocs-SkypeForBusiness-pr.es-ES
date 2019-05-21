---
title: Habilitar usuarios para el sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente:.
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287464"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="8cacd-104">Habilitar usuarios para el sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="8cacd-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="8cacd-105">En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad RTC local.</span><span class="sxs-lookup"><span data-stu-id="8cacd-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="8cacd-106">Antes de seguir los pasos de este tema, debe leer lo siguiente:.</span><span class="sxs-lookup"><span data-stu-id="8cacd-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="8cacd-107">Para obtener información sobre cómo configurar la conectividad híbrida, consulte planear la conectividad [híbrida entre Skype empresarial Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e [implementar conectividad híbrida entre Skype empresarial Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8cacd-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="8cacd-108">Para obtener más información sobre cómo planear la implementación, consulte [planear el sistema telefónico en Office 365 con conectividad RTC local en Skype empresarial Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8cacd-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="8cacd-109">Para obtener más información sobre el sistema telefónico en Office 365, incluidas las licencias y los planes, consulte [planes de llamadas RTC para Skype empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="8cacd-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="8cacd-110">Mover usuarios a un sistema telefónico en Office 365 con conectividad RTC local</span><span class="sxs-lookup"><span data-stu-id="8cacd-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="8cacd-111">Antes de mover los usuarios a Skype empresarial online, se recomienda habilitar a los usuarios locales en Skype empresarial Server o Lync Server 2013 y, a continuación, moverlos a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="8cacd-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="8cacd-112">Para obtener más información, consulte [planear la conectividad híbrida entre Skype empresarial Server y Skype empresarial online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) , así como la sección de consideraciones especiales de [habilitar los usuarios de Enterprise Voice local](enable-the-users-for-enterprise-voice-on-premises.md) (se realizan mientras los usuarios están alojados). local).</span><span class="sxs-lookup"><span data-stu-id="8cacd-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="8cacd-113">Todos los usuarios deben crearse en Active Directory local y sincronizarse con Office 365 con la versión compatible del conector de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8cacd-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="8cacd-114">No puede habilitar usuarios para el sistema telefónico en Office 365 que se crearon directamente en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8cacd-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="8cacd-115">Si quiere habilitar el sistema telefónico en Office 365 con conectividad RTC local para un usuario que se creó en Azure AD, tendrá que crear una cuenta nueva para ese usuario en su AD local, configurar la cuenta local y, a continuación, sincronizar la cuenta con una versión compatible de la herramienta conector de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8cacd-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="8cacd-116">Habilitar un usuario para el sistema telefónico en Office 365 con conectividad RTC local y, a continuación, moverlos a Skype empresarial online requiere los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8cacd-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="8cacd-117">[Habilitar a los usuarios para Enterprise Voice local](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza mientras los usuarios están alojados en local).</span><span class="sxs-lookup"><span data-stu-id="8cacd-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="8cacd-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (realizado mientras los usuarios están hospedados de forma local).</span><span class="sxs-lookup"><span data-stu-id="8cacd-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="8cacd-119">[Sincronizar usuarios con la nube y asignar licencias](synchronize-users-to-the-cloud-and-assign-licenses.md) (realizada con Office 365).</span><span class="sxs-lookup"><span data-stu-id="8cacd-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="8cacd-120">[Mover usuarios locales a Skype empresarial online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (realizada con Windows PowerShell local, pero usando sus credenciales de administrador de Office 365).</span><span class="sxs-lookup"><span data-stu-id="8cacd-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="8cacd-121">[Habilitar usuarios para Enterprise Voice online y sistemas telefónicos en el buzón de voz de Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (realizada con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="8cacd-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

