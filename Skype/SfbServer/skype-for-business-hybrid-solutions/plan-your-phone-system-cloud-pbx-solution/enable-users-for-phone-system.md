---
title: Permitir a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Este tema describe cómo habilitar a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local. Antes de seguir los pasos de este tema, lea lo siguiente:.
ms.openlocfilehash: e4b76074f26cbfafc248bfe9787f5886f4a70063
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="facdc-104">Permitir a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="facdc-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="facdc-105">Este tema describe cómo habilitar a los usuarios para el sistema de teléfono en Office 365 con conectividad de RTC local.</span><span class="sxs-lookup"><span data-stu-id="facdc-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="facdc-106">Antes de seguir los pasos de este tema, lea lo siguiente:.</span><span class="sxs-lookup"><span data-stu-id="facdc-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="facdc-107">Para aprender a configurar la conectividad híbrida, consulte [Plan de conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) y [conectividad de implementación híbrida entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="facdc-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="facdc-108">Para obtener información acerca de cómo planear la implementación, vea [Planear el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="facdc-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="facdc-109">Para obtener más información sobre el sistema de teléfono en Office 365, incluyendo licencias y planes, consulte [PSTN llamando a planes de Skype para el negocio](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="facdc-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="facdc-110">Mover los usuarios al sistema de teléfono en Office 365 con conectividad de RTC local</span><span class="sxs-lookup"><span data-stu-id="facdc-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="facdc-111">Antes de mover los usuarios a Skype para los negocios en línea, se recomienda permitir a los usuarios en las instalaciones de Skype para Business Server o Lync Server 2013 y moverlos en línea.</span><span class="sxs-lookup"><span data-stu-id="facdc-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="facdc-112">Para obtener más información, consulte la sección Consideraciones especiales de [Permitir que los usuarios de Telefonía IP empresarial en instalaciones](enable-the-users-for-enterprise-voice-on-premises.md)y [Plan de conectividad híbrida entre Skype para Business Server y Skype para los negocios en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) .</span><span class="sxs-lookup"><span data-stu-id="facdc-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md).</span></span> 
  
<span data-ttu-id="facdc-113">Todos los usuarios deben ser creados en Active Directory en locales y sincronizados a Office 365 con la versión compatible de conector de AD de Azure.</span><span class="sxs-lookup"><span data-stu-id="facdc-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="facdc-114">No puede habilitar a los usuarios para el sistema de teléfono en Office 365 creados directamente en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="facdc-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="facdc-115">Si desea habilitar el sistema de teléfono en Office 365 con conectividad de RTC local para un usuario que se creó en Azure AD, necesitará crear una nueva cuenta para ese usuario en sus instalaciones AD, configurar la cuenta local y, a continuación, sincronizar la cuenta mediante una versión compatible de la herramienta Conector de AD de Azure.</span><span class="sxs-lookup"><span data-stu-id="facdc-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="facdc-116">Habilitar a un usuario para el sistema telefónico en Office 365 con conectividad de RTC local y, a continuación, moverlos a Skype para los negocios en línea requieren los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="facdc-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="facdc-117">[Permitir que los usuarios de Telefonía IP empresarial en instalaciones](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza cuando los usuarios están alojados en locales).</span><span class="sxs-lookup"><span data-stu-id="facdc-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="facdc-118">[Asignar una directiva de enrutamiento de voz](assign-a-voice-routing-policy.md) (se realiza cuando los usuarios están alojados en locales).</span><span class="sxs-lookup"><span data-stu-id="facdc-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="facdc-119">[Sincronizar usuarios a la nube y asignar licencias](synchronize-users-to-the-cloud-and-assign-licenses.md) (realiza mediante Office 365).</span><span class="sxs-lookup"><span data-stu-id="facdc-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="facdc-120">[Mover usuarios locales a Skype para los negocios en línea](move-on-premises-users-to-skype-for-business-online.md) (se realiza mediante Windows PowerShell local, sino mediante sus credenciales de administrador de Office 365).</span><span class="sxs-lookup"><span data-stu-id="facdc-120">[Move on-premises users to Skype for Business Online](move-on-premises-users-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="facdc-121">[Permitir que los usuarios de Telefonía IP empresarial en línea y sistema de teléfono en el correo de voz de Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (lo realiza el uso de PowerShell remoto).</span><span class="sxs-lookup"><span data-stu-id="facdc-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell).</span></span>
    

