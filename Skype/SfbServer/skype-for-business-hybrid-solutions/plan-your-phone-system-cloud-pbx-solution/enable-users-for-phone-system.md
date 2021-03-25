---
title: Permitir que los usuarios usen el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'En este tema se describe cómo habilitar a los usuarios del sistema telefónico con conectividad RTC local. Antes de seguir los pasos de este tema, debe leer lo siguiente: .'
ms.openlocfilehash: 0a843b49546bfc5451197a3ef8ca48799c194731
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120872"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="10d07-104">Permitir que los usuarios usen el Sistema telefónico con una conectividad RTC local en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="10d07-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="10d07-105">En este tema se describe cómo habilitar a los usuarios del sistema telefónico con conectividad RTC local.</span><span class="sxs-lookup"><span data-stu-id="10d07-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="10d07-106">Antes de seguir los pasos de este tema, debe leer lo siguiente: .</span><span class="sxs-lookup"><span data-stu-id="10d07-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="10d07-107">Para obtener información sobre cómo configurar la conectividad híbrida, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Deploy hybrid connectivity between Skype for Business Server and Skype for Business [Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="10d07-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>
    
- <span data-ttu-id="10d07-108">Para obtener información sobre cómo planear la implementación, vea [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="10d07-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="10d07-109">Para obtener más información acerca del sistema telefónico, incluidas las licencias y los planes, vea Planes de llamadas [RTC para Skype Empresarial](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="10d07-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="10d07-110">Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual el servicio ya no será accesible.</span><span class="sxs-lookup"><span data-stu-id="10d07-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="10d07-111">Además, la conectividad RTC entre el entorno local ya no se admite a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="10d07-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="10d07-112">Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="10d07-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="10d07-113">Mover usuarios al sistema telefónico con conectividad RTC local</span><span class="sxs-lookup"><span data-stu-id="10d07-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="10d07-114">Antes de mover los usuarios a Skype Empresarial Online, se recomienda habilitar los usuarios locales en Skype Empresarial Server o Lync Server 2013 y, a continuación, moverlos en línea.</span><span class="sxs-lookup"><span data-stu-id="10d07-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="10d07-115">Para obtener más información, vea [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) y la sección de consideraciones especiales de Enable the users for Telefonía IP empresarial on [premises](enable-the-users-for-enterprise-voice-on-premises.md) (realizado mientras los usuarios se encuentran en el entorno local).</span><span class="sxs-lookup"><span data-stu-id="10d07-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="10d07-116">Todos los usuarios deben crearse en Active Directory localmente y sincronizarse con Microsoft 365 u Office 365 mediante la versión compatible de Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="10d07-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="10d07-117">No puede habilitar usuarios de Sistema telefónico en Office 365 que se crearon directamente en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="10d07-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="10d07-118">Si desea habilitar el sistema telefónico con conectividad RTC local para un usuario que se creó en Azure AD, deberá crear una nueva cuenta para ese usuario en su AD local, configurar la cuenta local y, a continuación, sincronizar la cuenta con una versión compatible de la herramienta Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="10d07-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="10d07-119">Habilitar un usuario para sistema telefónico con conectividad RTC local y, a continuación, moverlos a Skype Empresarial Online requiere los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="10d07-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="10d07-120">[Habilite los usuarios para Telefonía IP empresarial local](enable-the-users-for-enterprise-voice-on-premises.md) (se realiza mientras los usuarios se encuentran en el entorno local).</span><span class="sxs-lookup"><span data-stu-id="10d07-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="10d07-121">[Asignar una directiva de enrutamiento de](assign-a-voice-routing-policy.md) voz (realizada mientras los usuarios se encuentran en el entorno local).</span><span class="sxs-lookup"><span data-stu-id="10d07-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="10d07-122">[Sincronizar usuarios con la nube y asignar licencias (realizadas](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) con Office 365).</span><span class="sxs-lookup"><span data-stu-id="10d07-122">[Synchronize users to the cloud and assign licenses](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) (performed using Office 365).</span></span>
    
- <span data-ttu-id="10d07-123">[Mover usuarios locales a Skype Empresarial Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (realizado con Windows PowerShell local, pero con sus credenciales de administrador de Office 365).</span><span class="sxs-lookup"><span data-stu-id="10d07-123">[Move on-premises users to Skype for Business Online](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="10d07-124">[Habilite a los usuarios para Telefonía IP empresarial en](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) línea y el correo de voz del sistema telefónico (realizado con PowerShell remoto).</span><span class="sxs-lookup"><span data-stu-id="10d07-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
