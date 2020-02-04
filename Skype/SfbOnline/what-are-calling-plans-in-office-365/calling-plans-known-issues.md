---
title: Problemas conocidos de Planes de llamadas
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 3441969133c8f67b63b620aff25545b89085858f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692315"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="dd2fa-103">Problemas conocidos de Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="dd2fa-103">Calling Plans known issues</span></span>

<span data-ttu-id="dd2fa-p101">Los planes de llamadas en Office 365 son una nueva característica que se encuentra en Skype empresarial online. A continuación se indican los problemas actuales de los que se realiza un seguimiento y se investigan activamente. Se resolverán potencialmente cuando la característica se actualice en las compilaciones futuras de Office 365 y Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="dd2fa-p101">Calling Plans in Office 365 are a new feature found in Skype for Business Online. The following are current issues that are being tracked and actively investigated. They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="dd2fa-107">Problemas conocidos de Planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="dd2fa-107">Calling Plans known issues</span></span>

|<span data-ttu-id="dd2fa-108">**Problema conocido**</span><span class="sxs-lookup"><span data-stu-id="dd2fa-108">**Known issue**</span></span>|<span data-ttu-id="dd2fa-109">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="dd2fa-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd2fa-110">La transición desde las licencias Technical Preview a las licencias de producción para planes de llamadas no actualiza automáticamente la licencia.</span><span class="sxs-lookup"><span data-stu-id="dd2fa-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="dd2fa-111">Compre primero sus licencias nuevas para que estén listas para su asignación a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="dd2fa-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="dd2fa-112">Elimine la licencia de la promoción (Technical Preview) de un usuario y, a continuación, asigne **inmediatamente** el nuevo **plan de llamadas nacionales** y las licencias del **plan de llamadas nacionales e internacionales** al usuario.</span><span class="sxs-lookup"><span data-stu-id="dd2fa-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="dd2fa-113">Si va a quitar y agregar licencias para varios usuarios, es muy importante que quite las licencias de todos los usuarios que usen Windows PowerShell y que después asigne **INMEDIATAMENTE** las licencias de todos los usuarios que usen Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd2fa-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="dd2fa-114">De esta manera, se asegurará de que no se interrumpa el servicio al manejar grandes volúmenes de asignaciones de licencias de usuario.</span><span class="sxs-lookup"><span data-stu-id="dd2fa-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="dd2fa-115">Para obtener ejemplos de scripts de PowerShell, consulte [asignar licencias de Skype empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="dd2fa-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="dd2fa-116">**Nota:** Si está usando la conectividad RTC local para usuarios híbridos, *solo* tiene que asignar una licencia de **sistema telefónico** .</span><span class="sxs-lookup"><span data-stu-id="dd2fa-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="dd2fa-117">Además, **no** deberías asignar un plan de llamadas de voz.</span><span class="sxs-lookup"><span data-stu-id="dd2fa-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="dd2fa-118">Sin embargo, si habilita planes de llamadas en Office 365 para usuarios que están en Office 365, debe asignar un **plan de llamadas nacionales** o una licencia de **plan de llamadas nacionales e internacionales** para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="dd2fa-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="dd2fa-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="dd2fa-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dd2fa-120">Si necesita obtener más números de teléfono, [póngase en contacto con el soporte técnico para productos para empresas: ayuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="dd2fa-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="dd2fa-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="dd2fa-121">Related topics</span></span>
[<span data-ttu-id="dd2fa-122">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="dd2fa-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="dd2fa-123">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="dd2fa-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="dd2fa-124">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="dd2fa-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="dd2fa-125">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="dd2fa-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="dd2fa-126">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="dd2fa-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 