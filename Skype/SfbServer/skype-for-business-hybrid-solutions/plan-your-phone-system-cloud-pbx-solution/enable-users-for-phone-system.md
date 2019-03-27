---
title: Habilitar a usuarios para el sistema telefónico en Office 365 con conectividad de RTC local en Skype para Business Server
ms.reviewer: ''
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad de RTC local. Antes de seguir los pasos descritos en este tema, debe leer los siguientes:.
ms.openlocfilehash: a3eec7adbd4897889cbc2ef8c7e985231c53bc99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889220"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="ff3c0-104">Habilitar a usuarios para el sistema telefónico en Office 365 con conectividad de RTC local en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="ff3c0-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="ff3c0-105">En este tema se describe cómo habilitar a los usuarios para el sistema telefónico en Office 365 con conectividad de RTC local.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="ff3c0-106">Antes de seguir los pasos descritos en este tema, debe leer los siguientes:.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="ff3c0-107">Para obtener información sobre cómo configurar la conectividad híbrida, vea [Planear la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) y la [conectividad de híbrido de implementar entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="ff3c0-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="ff3c0-108">Para obtener información acerca de cómo planear la implementación, vea [Planear el sistema de teléfono en Office 365 con conectividad de RTC local en Skype para Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="ff3c0-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="ff3c0-109">Para obtener más información acerca del sistema de teléfono en Office 365, incluida la concesión de licencias y planes, consulte [planes de RTC de llamada de Skype para la empresa](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="ff3c0-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="ff3c0-110">Mover a los usuarios al sistema de teléfono en Office 365 con conectividad de RTC local</span><span class="sxs-lookup"><span data-stu-id="ff3c0-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="ff3c0-111">Antes de mover los usuarios a Skype para profesionales en línea, se recomienda que permiten a los usuarios en local en Skype para Business Server o Lync Server 2013 y, a continuación, muévalos en línea.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="ff3c0-112">Para obtener más información, vea la sección Consideraciones especiales de [Habilitar a los usuarios para Enterprise Voice en local](enable-the-users-for-enterprise-voice-on-premises.md) (realizado mientras los usuarios están hospedados y [planeación de la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) local).</span><span class="sxs-lookup"><span data-stu-id="ff3c0-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="ff3c0-113">Todos los usuarios deben crearse en Active Directory local y sincronizan en Office 365 con la versión admitida del conector de AD de Azure.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="ff3c0-114">No se puede habilitar a los usuarios para el sistema telefónico en Office 365 que se crearon directamente en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="ff3c0-115">Si desea habilitar el sistema telefónico en Office 365 con conectividad de RTC local para un usuario que se creó en Azure AD, que necesitará para crear una nueva cuenta para ese usuario en sus instalaciones AD, configuración de la cuenta local y, a continuación, sincronizar el uso de la cuenta una versión compatible de la herramienta de conector de AD de Azure.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="ff3c0-116">Habilitar a un usuario para el sistema telefónico en Office 365 con conectividad de RTC local y, a continuación, moverlos a Skype para profesionales Online requieren los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="ff3c0-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="ff3c0-117">[Habilitar a los usuarios para Enterprise Voice local](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza cuando los usuarios están hospedados en implementaciones locales).</span><span class="sxs-lookup"><span data-stu-id="ff3c0-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="ff3c0-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (realizado mientras los usuarios están hospedados de forma local).</span><span class="sxs-lookup"><span data-stu-id="ff3c0-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="ff3c0-119">[Sincronizar a los usuarios a la nube y asignar licencias](synchronize-users-to-the-cloud-and-assign-licenses.md) (realiza mediante Office 365).</span><span class="sxs-lookup"><span data-stu-id="ff3c0-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="ff3c0-120">[Mover a los usuarios de local Skype para profesionales en línea](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (lo realiza el uso de Windows PowerShell local, pero con sus credenciales de administrador de Office 365).</span><span class="sxs-lookup"><span data-stu-id="ff3c0-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="ff3c0-121">[Habilitar a los usuarios para Enterprise Voice en línea y el sistema de teléfono en el correo de voz de Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (realiza mediante PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="ff3c0-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

