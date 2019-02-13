---
title: Cómo se puede usar la identificación de llamadas en su organización
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
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
description: Identificador de autor de la llamada se puede controlar mediante el uso de una directiva denominada CallingLineIdentity para las llamadas entrantes y salientes para los usuarios del sistema telefónico.
ms.openlocfilehash: 4ae5c54d68410096104f61bf8cdbd71fa0628003
ms.sourcegitcommit: 99bc2db8cb857b6fd2ddf9b837198be849dafb9b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "29981918"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="91591-103">Cómo se puede usar la identificación de llamadas en su organización</span><span class="sxs-lookup"><span data-stu-id="91591-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="91591-104">Identificador de autor de la llamada se puede controlar mediante el uso de una directiva denominada CallingLineIdentity para las llamadas entrantes y salientes para los usuarios del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="91591-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="91591-105">La funcionalidad de identificador de autor de la llamada está disponible para todos los usuarios del sistema telefónico independientemente de la conectividad de RTC:</span><span class="sxs-lookup"><span data-stu-id="91591-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="91591-106">Conectividad con RTC en línea</span><span class="sxs-lookup"><span data-stu-id="91591-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="91591-107">Conectividad con RTC local con Skype Empresarial Cloud Connector Edition (requiere Cloud Connector Edition 1.4.2 y posterior)</span><span class="sxs-lookup"><span data-stu-id="91591-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="91591-108">Conectividad con RTC local con Skype Empresarial Server (requiere Skype Empresarial Server 2015 CU5 y posterior)</span><span class="sxs-lookup"><span data-stu-id="91591-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="91591-109">Esta directiva no está disponible en Skype Empresarial 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="91591-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="91591-110">Identificación de llamadas de salida</span><span class="sxs-lookup"><span data-stu-id="91591-110">Outbound caller ID</span></span>

<span data-ttu-id="91591-111">Hay tres opciones disponibles para la identificación de llamadas RTC de salida:</span><span class="sxs-lookup"><span data-stu-id="91591-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="91591-112">El número de teléfono asignado al usuario, que es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="91591-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="91591-113">Un número de teléfono que está clasificado como un *servicio* y un número *gratuito* en el inventario de números de teléfono de Planes de llamadas de Office 365.</span><span class="sxs-lookup"><span data-stu-id="91591-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="91591-114">Normalmente, se asigna a una cola de llamadas o de operador automático organizativos.</span><span class="sxs-lookup"><span data-stu-id="91591-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="91591-115">Configurado como anónimo.</span><span class="sxs-lookup"><span data-stu-id="91591-115">Set to anonymous.</span></span>
    
<span data-ttu-id="91591-116">Sin embargo, no es posible asignar estos tipos de números de teléfono al identificador de llamadas de salida:</span><span class="sxs-lookup"><span data-stu-id="91591-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="91591-117">Los números de teléfono que se clasifican como un *usuario* en su teléfono de planes de llamar al número de inventario</span><span class="sxs-lookup"><span data-stu-id="91591-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="91591-118">Un número de teléfono de Skype Empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="91591-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="91591-119">Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="91591-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="91591-120">Control de usuario final para la identificación de llamadas de salida</span><span class="sxs-lookup"><span data-stu-id="91591-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="91591-121">El atributo EnableUserOverride permite a uno o varios usuarios cambiar su configuración de identificación de llamadas a **Anónimo**.</span><span class="sxs-lookup"><span data-stu-id="91591-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="91591-122">Esto solo se aplica cuando una directiva de CallingLineIdentity se configura con un parámetro CallingIDSubstitute de LineURI o Substitute.</span><span class="sxs-lookup"><span data-stu-id="91591-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="91591-123">El valor predeterminado de EnableUserOverride es False.</span><span class="sxs-lookup"><span data-stu-id="91591-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="91591-124">Los usuarios finales pueden establecer su identificador de autor de la llamada a **anónimo** mediante la ficha **configuración** en el Skype para el cliente de escritorio empresarial, seleccione **llamadas a un usuario final** (si se habilita por admin), seleccione información del perfil y el número de \*\*Ocultar Mi teléfono para todas las llamadas \*\*.</span><span class="sxs-lookup"><span data-stu-id="91591-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="91591-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="91591-125">**Windows**</span></span> <br/> |<span data-ttu-id="91591-126">**Versión**</span><span class="sxs-lookup"><span data-stu-id="91591-126">**Version**</span></span> <br/> |<span data-ttu-id="91591-127">**Compatible**</span><span class="sxs-lookup"><span data-stu-id="91591-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="91591-128">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="91591-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="91591-129">Canal actual publicado el 6 de diciembre de 2016 - Versión 1611 (Compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="91591-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="91591-130">Sí</span><span class="sxs-lookup"><span data-stu-id="91591-130">Yes</span></span>  <br/> |
|<span data-ttu-id="91591-131">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="91591-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="91591-132">Primera versión para el Canal diferido publicada el 22 de febrero de 2017 - Versión 1701 (Compilación 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="91591-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="91591-133">Sí</span><span class="sxs-lookup"><span data-stu-id="91591-133">Yes</span></span>  <br/> |
|<span data-ttu-id="91591-134">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="91591-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="91591-135">Canal diferido publicado el 13 de junio de 2017 - versión 1701 (compilación 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="91591-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="91591-136">Sí</span><span class="sxs-lookup"><span data-stu-id="91591-136">Yes</span></span>  <br/> |
|<span data-ttu-id="91591-137">MSI</span><span class="sxs-lookup"><span data-stu-id="91591-137">MSI</span></span>  <br/> |<span data-ttu-id="91591-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="91591-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="91591-139">No</span><span class="sxs-lookup"><span data-stu-id="91591-139">No</span></span>  <br/> |
|<span data-ttu-id="91591-140">Mac</span><span class="sxs-lookup"><span data-stu-id="91591-140">Mac</span></span>  <br/> |<span data-ttu-id="91591-141">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="91591-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="91591-142">No</span><span class="sxs-lookup"><span data-stu-id="91591-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="91591-143">Identificación de llamadas de entrada</span><span class="sxs-lookup"><span data-stu-id="91591-143">Inbound Caller ID</span></span>

<span data-ttu-id="91591-144">El atributo BlockIncomingCallerID permite bloquear la identificación de llamadas en las llamadas RTC de entrada.</span><span class="sxs-lookup"><span data-stu-id="91591-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="91591-145">Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="91591-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="91591-146">En este momento está solo disponible con la conectividad con RTC en línea.</span><span class="sxs-lookup"><span data-stu-id="91591-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="91591-147">Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="91591-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="91591-148">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="91591-148">Related topics</span></span>
[<span data-ttu-id="91591-149">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="91591-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="91591-150">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="91591-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="91591-151">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="91591-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="91591-152">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="91591-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="91591-153">[Skype for Business Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="91591-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
