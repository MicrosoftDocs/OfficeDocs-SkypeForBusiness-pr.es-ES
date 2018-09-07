---
title: Problemas conocidos de Planes de llamada
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: e43aecea6bd19c6b346de68577f471214818d43f
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854161"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="a47eb-103">Problemas conocidos de Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="a47eb-103">Calling Plans known issues</span></span>

<span data-ttu-id="a47eb-104">Planes de llamada en Office 365 son una característica nueva que se encuentran en Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="a47eb-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="a47eb-105">Los siguientes son problemas actuales que se va a realizar un seguimiento y activamente investigarse.</span><span class="sxs-lookup"><span data-stu-id="a47eb-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="a47eb-106">Se resolverán potencialmente cuando la característica se ha actualizado en futuras versiones de Office 365 y Skype para profesionales en línea.</span><span class="sxs-lookup"><span data-stu-id="a47eb-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="a47eb-107">Problemas conocidos de Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="a47eb-107">Calling Plans known issues</span></span>

|<span data-ttu-id="a47eb-108">**Problema conocido**</span><span class="sxs-lookup"><span data-stu-id="a47eb-108">**Known issue**</span></span>|<span data-ttu-id="a47eb-109">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="a47eb-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a47eb-110">Transición de Tech Preview licencias para las licencias de producción para llamar a los planes no actualizan automáticamente la licencia.</span><span class="sxs-lookup"><span data-stu-id="a47eb-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="a47eb-111">En primer lugar a adquirir las licencias nuevo para que estén preparados ser asignado a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a47eb-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="a47eb-112">Quitar la licencia de promoción (Tech Preview) de un usuario y, a continuación, asignar **inmediatamente** las licencias de **Llamar a planear nacional** o **nacionales y llamar a planear internacional de** nuevo al usuario.</span><span class="sxs-lookup"><span data-stu-id="a47eb-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="a47eb-113">Si va a quitar y agregar licencias para varios usuarios, es muy importante que quite las licencias de todos los usuarios que usen Windows PowerShell y que después asigne **INMEDIATAMENTE** las licencias de todos los usuarios que usen Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a47eb-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="a47eb-114">De esta forma se asegurará de que no hay ninguna interrupción del servicio al manejar grandes volúmenes de las asignaciones de licencia de usuario.</span><span class="sxs-lookup"><span data-stu-id="a47eb-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="a47eb-115">Para los scripts de PowerShell de ejemplo, vea [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a47eb-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="a47eb-116">**Nota:** Si está utilizando la conectividad de RTC local para los usuarios de híbrida, *sólo* tiene que asignar una licencia de **Sistema telefónico** .</span><span class="sxs-lookup"><span data-stu-id="a47eb-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="a47eb-117">**No** debe asignar también una planeación de la llamada de voz.</span><span class="sxs-lookup"><span data-stu-id="a47eb-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="a47eb-118">Sin embargo, si va a habilitar una llamada a los planes en Office 365 para los usuarios que se encuentran en Office 365, debe asignar aún un **Nacionales llamar a planear** o una licencia **nacionales y llamar a planear internacional** para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="a47eb-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="a47eb-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="a47eb-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a47eb-120">Si necesita obtener más números de teléfono que este, por favor, [póngase en contacto con soporte técnico para productos de negocio: Ayuda de administración](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="a47eb-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="a47eb-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a47eb-121">Related topics</span></span>
[<span data-ttu-id="a47eb-122">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="a47eb-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="a47eb-123">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="a47eb-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="a47eb-124">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="a47eb-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="a47eb-125">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="a47eb-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a47eb-126">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a47eb-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 