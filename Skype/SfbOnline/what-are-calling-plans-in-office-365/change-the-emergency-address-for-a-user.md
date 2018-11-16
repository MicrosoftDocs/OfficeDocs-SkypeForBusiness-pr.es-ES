---
title: Cambiar la dirección de emergencia de un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 5412636c-ad0e-48a5-b199-5925156abee4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Procedimiento para cambiar la dirección de emergencia de un usuario para que funcione con la pública teléfono red conmutada (RTC) en Estados Unidos y Europa. '
ROBOTS: NOINDEX
ms.openlocfilehash: 8dac43120fafa1a98e441b983b673e78d2a24d75
ms.sourcegitcommit: f0dec487e2893a171c7e701bfcf598076f5245b7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26538963"
---
# <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="8189a-103">Cambiar la dirección de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="8189a-103">Change the emergency address for a user</span></span>

<span data-ttu-id="8189a-104">Cuando configure un Plan de llamadas en Office 365, deberá asignar una dirección de emergencia a cada usuario o número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="8189a-104">When you are setting up Calling Plans in Office 365, you will need to assign an emergency address to each phone number or user.</span></span> <span data-ttu-id="8189a-105">En Europa, la dirección de emergencia se asocia con el número de teléfono cuando se obtiene desde Office 365 o cuando se transfiere a través de un número de teléfono para Office 365.</span><span class="sxs-lookup"><span data-stu-id="8189a-105">In European countries, the emergency address is associated with the phone number when you get it from Office 365 or when you transfer a phone number over to Office 365.</span></span> <span data-ttu-id="8189a-106">En los Estados Unidos, la dirección de emergencia se asocia con el número de teléfono cuando se asigna al usuario.</span><span class="sxs-lookup"><span data-stu-id="8189a-106">In the United States, the emergency address is associated with the phone number when it is assigned to the user.</span></span> <span data-ttu-id="8189a-107">La dirección de emergencia se puede cambiar si se mueve a una nueva ubicación el usuario al que está asignada.</span><span class="sxs-lookup"><span data-stu-id="8189a-107">The emergency address can be changed if the user it is assigned to moves to a new location.</span></span> <span data-ttu-id="8189a-108">Para obtener más información acerca de las direcciones de emergencias y ubicaciones, consulte [¿Cuáles son las ubicaciones de emergencia, direcciones y enrutamiento de llamadas?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="8189a-108">For more about emergency addresses and locations, see [What are emergency locations, addresses and call routing?](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)</span></span>
  
<span data-ttu-id="8189a-109">Para conseguir información sobre cómo obtener Planes de llamadas en Office 365 y su coste, consulte [Licencias de complementos de Skype Empresarial y Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="8189a-109">To learn how to get Calling Plans in Office 365 and how much they cost, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
  
## <a name="change-the-emergency-address-for-a-user"></a><span data-ttu-id="8189a-110">Cambiar la dirección de emergencia de un usuario</span><span class="sxs-lookup"><span data-stu-id="8189a-110">Change the emergency address for a user</span></span>

<span data-ttu-id="8189a-111">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="8189a-111">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="8189a-112">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="8189a-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="8189a-113">Vaya a **los equipos de Microsoft y Skype para el centro de administración de negocio** > **portal heredado**.</span><span class="sxs-lookup"><span data-stu-id="8189a-113">Go to the **Microsoft Teams and Skype for Business Admin Center** > **Legacy portal**.</span></span>
    
3. <span data-ttu-id="8189a-114">En el panel de navegación izquierdo, vaya a **voz** > **a los usuarios de voz**.</span><span class="sxs-lookup"><span data-stu-id="8189a-114">In the left navigation, go to **Voice** > **Voice users**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8189a-115">Para que pueda ver la opción de **voz** en la izquierda en la Skype para el centro de administración de negocio, primero debe comprar una licencia adicional para **Conferencias de Audio** , una licencia adicional para **El sistema de teléfono** o al menos una **licencia Enterprise E5**.</span><span class="sxs-lookup"><span data-stu-id="8189a-115">For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.</span></span>
    
4. <span data-ttu-id="8189a-116">En la página **Usuarios de voz**, busque y seleccione el usuario cuya dirección de emergencia quiere cambiar.</span><span class="sxs-lookup"><span data-stu-id="8189a-116">On the **Voice users** page, locate and select the user you want to change the emergency address for.</span></span>
    
5. <span data-ttu-id="8189a-117">En el panel de acciones, en **Ubicación de emergencia**, haga clic en **Cambiar**.</span><span class="sxs-lookup"><span data-stu-id="8189a-117">In the Action pane, under **Emergency location**, click **Change**.</span></span>
    
6. <span data-ttu-id="8189a-118">En la página **Asignar un número**, haga clic en **Cambiar ubicación**.</span><span class="sxs-lookup"><span data-stu-id="8189a-118">On the **Assign number** page, click **Change location**.</span></span> 
    
7. <span data-ttu-id="8189a-119">En **Cambiar dirección de emergencia a**, escriba el nombre de la ciudad en el cuadro y haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="8189a-119">Under **Change emergency address to**, enter the name of the city in the box and click **Search**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="8189a-120">Solo se puede cambiar una dirección de emergencia que ya esté validada.</span><span class="sxs-lookup"><span data-stu-id="8189a-120">You can only change an emergency address that has already been validated.</span></span> <span data-ttu-id="8189a-121">Para cambiar una dirección de emergencia que no se ha validado, eliminarla y crear otra dirección de emergencia.</span><span class="sxs-lookup"><span data-stu-id="8189a-121">To change an emergency address that hasn't been validated, delete it and create another emergency address.</span></span> 
  
8. <span data-ttu-id="8189a-122">Seleccione una nueva dirección de emergencia en la lista y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8189a-122">Select a new emergency address from the list, and then click **Save**.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="8189a-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8189a-123">Related topics</span></span>
[<span data-ttu-id="8189a-124">Agregar o quitar una dirección de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="8189a-124">Add or remove an emergency address for your organization</span></span>](add-or-remove-an-emergency-address-for-your-organization.md)

[<span data-ttu-id="8189a-125">Agregar, cambiar o quitar una ubicación de emergencia para su organización</span><span class="sxs-lookup"><span data-stu-id="8189a-125">Add, change, or remove an emergency location for your organization</span></span>](add-change-or-remove-an-emergency-location-for-your-organization.md)

[<span data-ttu-id="8189a-126">¿Qué es la validación de direcciones?</span><span class="sxs-lookup"><span data-stu-id="8189a-126">What is address validation?</span></span>](what-is-address-validation.md)

[<span data-ttu-id="8189a-127">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="8189a-127">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="8189a-128">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="8189a-128">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="8189a-129">[Skype for Business Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="8189a-129">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 