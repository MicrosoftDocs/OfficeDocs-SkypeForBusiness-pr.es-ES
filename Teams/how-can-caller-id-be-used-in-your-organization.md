---
title: Cómo se puede usar la identificación de llamadas en su organización
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords: ms.teamsadmincenter.voice.callerid.overview
ms.custom:
- Calling Plans
description: La identificación de llamadas se puede controlar tanto para llamadas entrantes como salientes de usuarios del sistema telefónico mediante una directiva denominada CallingLineIdentity.
ms.openlocfilehash: 32dbb3d5b164f2e40e0b8399e2047762ecf882ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680547"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="01f24-103">Cómo se puede usar la identificación de llamadas en su organización</span><span class="sxs-lookup"><span data-stu-id="01f24-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="01f24-104">La identificación de llamadas se puede controlar tanto para llamadas entrantes como salientes de usuarios del sistema telefónico mediante una directiva denominada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="01f24-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="01f24-105">La funcionalidad de identificación de llamadas está disponible para todos los usuarios del sistema telefónico con independencia de la conectividad RTC:</span><span class="sxs-lookup"><span data-stu-id="01f24-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="01f24-106">Conectividad con RTC en línea</span><span class="sxs-lookup"><span data-stu-id="01f24-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="01f24-107">Conectividad con RTC local con Skype Empresarial Cloud Connector Edition (requiere Cloud Connector Edition 1.4.2 y posterior)</span><span class="sxs-lookup"><span data-stu-id="01f24-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="01f24-108">Conectividad con RTC local con Skype Empresarial Server (requiere Skype Empresarial Server 2015 CU5 y posterior)</span><span class="sxs-lookup"><span data-stu-id="01f24-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="01f24-109">Esta directiva no está disponible en Skype Empresarial 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="01f24-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="01f24-110">Identificación de llamadas de salida</span><span class="sxs-lookup"><span data-stu-id="01f24-110">Outbound caller ID</span></span>

<span data-ttu-id="01f24-111">Hay tres opciones disponibles para la identificación de llamadas RTC de salida:</span><span class="sxs-lookup"><span data-stu-id="01f24-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="01f24-112">El número de teléfono asignado al usuario, que es el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="01f24-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="01f24-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="01f24-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="01f24-115">Configurado como anónimo.</span><span class="sxs-lookup"><span data-stu-id="01f24-115">Set to anonymous.</span></span>
    
<span data-ttu-id="01f24-116">Sin embargo, no es posible asignar estos tipos de números de teléfono al identificador de llamadas de salida:</span><span class="sxs-lookup"><span data-stu-id="01f24-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="01f24-117">Números de teléfono que se clasifican como un *usuario* en el inventario de números de teléfono de los planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="01f24-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="01f24-118">Un número de teléfono de Skype Empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="01f24-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="01f24-119">Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="01f24-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="01f24-120">Control de usuario final para la identificación de llamadas de salida</span><span class="sxs-lookup"><span data-stu-id="01f24-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="01f24-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span><span class="sxs-lookup"><span data-stu-id="01f24-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="01f24-124">Los usuarios finales pueden establecer su identificador de llamada en **anónimo** mediante la pestaña **configuración** del cliente de escritorio de Skype empresarial, seleccionar **llamadas a un usuario final** (si lo habilita el administrador), seleccionar **ocultar mi número de teléfono y la información del perfil para todas las llamadas**.</span><span class="sxs-lookup"><span data-stu-id="01f24-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="01f24-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="01f24-125">**Windows**</span></span> <br/> |<span data-ttu-id="01f24-126">**Versión**</span><span class="sxs-lookup"><span data-stu-id="01f24-126">**Version**</span></span> <br/> |<span data-ttu-id="01f24-127">**Compatible**</span><span class="sxs-lookup"><span data-stu-id="01f24-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="01f24-128">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="01f24-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="01f24-129">Canal actual publicado el 6 de diciembre de 2016 - Versión 1611 (Compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="01f24-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="01f24-130">Sí</span><span class="sxs-lookup"><span data-stu-id="01f24-130">Yes</span></span>  <br/> |
|<span data-ttu-id="01f24-131">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="01f24-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="01f24-132">Primera versión para el Canal diferido publicada el 22 de febrero de 2017 - Versión 1701 (Compilación 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="01f24-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="01f24-133">Sí</span><span class="sxs-lookup"><span data-stu-id="01f24-133">Yes</span></span>  <br/> |
|<span data-ttu-id="01f24-134">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="01f24-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="01f24-135">Canal diferido publicado el 13 de junio de 2017 - versión 1701 (compilación 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="01f24-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="01f24-136">Sí</span><span class="sxs-lookup"><span data-stu-id="01f24-136">Yes</span></span>  <br/> |
|<span data-ttu-id="01f24-137">MSI</span><span class="sxs-lookup"><span data-stu-id="01f24-137">MSI</span></span>  <br/> |<span data-ttu-id="01f24-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="01f24-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="01f24-139">No</span><span class="sxs-lookup"><span data-stu-id="01f24-139">No</span></span>  <br/> |
|<span data-ttu-id="01f24-140">Mac</span><span class="sxs-lookup"><span data-stu-id="01f24-140">Mac</span></span>  <br/> |<span data-ttu-id="01f24-141">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="01f24-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="01f24-142">No</span><span class="sxs-lookup"><span data-stu-id="01f24-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="01f24-143">Identificación de llamadas de entrada</span><span class="sxs-lookup"><span data-stu-id="01f24-143">Inbound Caller ID</span></span>

<span data-ttu-id="01f24-144">El sistema telefónico mostrará el identificador denominado para un número de teléfono externo si el número está asociado con un usuario en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="01f24-144">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="01f24-145">Si el número de teléfono no está en Azure AD, se mostrará el nombre para mostrar proporcionado por Telco, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="01f24-145">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="01f24-146">El atributo BlockIncomingCallerID permite bloquear la identificación de llamadas en las llamadas RTC de entrada.</span><span class="sxs-lookup"><span data-stu-id="01f24-146">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="01f24-147">Puede establecer este atributo, pero no está disponible para los usuarios finales en la página Configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="01f24-147">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="01f24-148">En este momento está solo disponible con la conectividad con RTC en línea.</span><span class="sxs-lookup"><span data-stu-id="01f24-148">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="01f24-149">Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="01f24-149">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="01f24-150">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="01f24-150">Related topics</span></span>
[<span data-ttu-id="01f24-151">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="01f24-151">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="01f24-152">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="01f24-152">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="01f24-153">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="01f24-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="01f24-154">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="01f24-154">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="01f24-155">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="01f24-155">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
