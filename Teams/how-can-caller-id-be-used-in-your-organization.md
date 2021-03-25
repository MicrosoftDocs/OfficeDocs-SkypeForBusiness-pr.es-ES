---
title: Cómo se puede usar la identificación de llamadas en su organización
ms.author: mikeplum
author: MikePlumleyMSFT
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
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: El identificador de llamadas se puede controlar tanto para las llamadas entrantes como salientes para los usuarios del sistema telefónico mediante una directiva denominada CallingLineIdentity.
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120681"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="0417a-103">Cómo se puede usar la identificación de llamadas en su organización</span><span class="sxs-lookup"><span data-stu-id="0417a-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="0417a-104">El identificador de llamadas se puede controlar tanto para las llamadas entrantes como salientes para los usuarios del sistema telefónico mediante una directiva denominada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="0417a-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="0417a-105">La funcionalidad de identificación de llamadas está disponible para todos los usuarios del sistema telefónico independientemente de la conectividad RTC:</span><span class="sxs-lookup"><span data-stu-id="0417a-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="0417a-106">Planes de llamadas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="0417a-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="0417a-107">Enrutamiento directo del sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="0417a-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="0417a-108">Conectividad con RTC en línea</span><span class="sxs-lookup"><span data-stu-id="0417a-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="0417a-109">Conectividad con RTC local con Skype Empresarial Cloud Connector Edition (requiere Cloud Connector Edition 1.4.2 y posterior)</span><span class="sxs-lookup"><span data-stu-id="0417a-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="0417a-110">Conectividad con RTC local con Skype Empresarial Server (requiere Skype Empresarial Server 2015 CU5 y posterior)</span><span class="sxs-lookup"><span data-stu-id="0417a-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="0417a-111">Esta directiva no está disponible en Skype Empresarial 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="0417a-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="0417a-112">Identificación de llamadas de salida</span><span class="sxs-lookup"><span data-stu-id="0417a-112">Outbound caller ID</span></span>

<span data-ttu-id="0417a-113">Hay tres opciones disponibles para el identificador de llamada RTC saliente:</span><span class="sxs-lookup"><span data-stu-id="0417a-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="0417a-114">El número de teléfono asignado al usuario, que es el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0417a-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="0417a-115">Un número de teléfono que  se clasifica como servicio *y* número gratuito en el inventario de números de teléfono planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0417a-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="0417a-116">Normalmente, se asigna a una cola de llamadas o de operador automático organizativos.</span><span class="sxs-lookup"><span data-stu-id="0417a-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="0417a-117">Configurado como anónimo.</span><span class="sxs-lookup"><span data-stu-id="0417a-117">Set to anonymous.</span></span>
    
<span data-ttu-id="0417a-118">Sin embargo, no es posible asignar estos tipos de números de teléfono al identificador de llamadas de salida:</span><span class="sxs-lookup"><span data-stu-id="0417a-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="0417a-119">Cualquier número de teléfono que se clasifique como  *usuario en*  el inventario de números de teléfono de planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="0417a-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="0417a-120">Un número de teléfono de Skype Empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="0417a-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="0417a-121">Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](./set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="0417a-121">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="0417a-122">Control de usuario final del identificador de llamada saliente</span><span class="sxs-lookup"><span data-stu-id="0417a-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="0417a-123">El atributo EnableUserOverride permite que uno o varios usuarios cambien su configuración de identificador de llamada a **Anónimo.**</span><span class="sxs-lookup"><span data-stu-id="0417a-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="0417a-124">Esto solo se aplica cuando una directiva de CallingLineIdentity se configura con un parámetro CallingIDSubstitute de LineURI o Substitute.</span><span class="sxs-lookup"><span data-stu-id="0417a-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="0417a-125">El valor predeterminado de EnableUserOverride es False.</span><span class="sxs-lookup"><span data-stu-id="0417a-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="0417a-126">Los usuarios finales pueden  establecer su  identificador de llamada en Anónimo mediante la pestaña Configuración del cliente de escritorio de Skype Empresarial, seleccionar Llamadas **a** un usuario final (si está habilitado por el administrador) y, después, seleccionar Ocultar mi número de teléfono e información de perfil para todas las **llamadas.**</span><span class="sxs-lookup"><span data-stu-id="0417a-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="0417a-127">En Teams, los usuarios pueden ir a su imagen de perfil en la esquina superior derecha, seleccionar Llamadas de configuración y, a continuación, en Identificador de llamada, seleccione Ocultar mi número de teléfono e información de perfil para todas las  >   **llamadas.** </span><span class="sxs-lookup"><span data-stu-id="0417a-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="0417a-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="0417a-128">**Windows**</span></span> <br/> |<span data-ttu-id="0417a-129">**Versión**</span><span class="sxs-lookup"><span data-stu-id="0417a-129">**Version**</span></span> <br/> |<span data-ttu-id="0417a-130">**Compatible**</span><span class="sxs-lookup"><span data-stu-id="0417a-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="0417a-131">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="0417a-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="0417a-132">Canal actual publicado el 6 de diciembre de 2016 - Versión 1611 (Compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="0417a-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="0417a-133">Sí</span><span class="sxs-lookup"><span data-stu-id="0417a-133">Yes</span></span>  <br/> |
|<span data-ttu-id="0417a-134">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="0417a-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="0417a-135">Primera versión para el Canal diferido publicada el 22 de febrero de 2017 - Versión 1701 (Compilación 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="0417a-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="0417a-136">Sí</span><span class="sxs-lookup"><span data-stu-id="0417a-136">Yes</span></span>  <br/> |
|<span data-ttu-id="0417a-137">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="0417a-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="0417a-138">Canal diferido publicado el 13 de junio de 2017 - versión 1701 (compilación 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="0417a-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="0417a-139">Sí</span><span class="sxs-lookup"><span data-stu-id="0417a-139">Yes</span></span>  <br/> |
|<span data-ttu-id="0417a-140">MSI</span><span class="sxs-lookup"><span data-stu-id="0417a-140">MSI</span></span>  <br/> |<span data-ttu-id="0417a-141">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0417a-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="0417a-142">No</span><span class="sxs-lookup"><span data-stu-id="0417a-142">No</span></span>  <br/> |
|<span data-ttu-id="0417a-143">Mac</span><span class="sxs-lookup"><span data-stu-id="0417a-143">Mac</span></span>  <br/> |<span data-ttu-id="0417a-144">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0417a-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="0417a-145">No</span><span class="sxs-lookup"><span data-stu-id="0417a-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="0417a-146">Id. de llamada entrante</span><span class="sxs-lookup"><span data-stu-id="0417a-146">Inbound caller ID</span></span>

<span data-ttu-id="0417a-147">Sistema telefónico mostrará el id. llamado para un número de teléfono externo si el número está asociado con un usuario en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0417a-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="0417a-148">Si el número de teléfono no está en Azure AD, se mostrará el nombre para mostrar proporcionado por la compañía telefónica si está disponible.</span><span class="sxs-lookup"><span data-stu-id="0417a-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="0417a-149">El atributo BlockIncomingCallerID permite bloquear la identificación de llamadas en las llamadas RTC de entrada.</span><span class="sxs-lookup"><span data-stu-id="0417a-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="0417a-150">Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="0417a-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="0417a-151">En este momento está solo disponible con la conectividad con RTC en línea.</span><span class="sxs-lookup"><span data-stu-id="0417a-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="0417a-152">Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](./set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="0417a-152">To set the outbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0417a-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0417a-153">Related topics</span></span>
[<span data-ttu-id="0417a-154">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="0417a-154">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="0417a-155">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="0417a-155">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="0417a-156">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="0417a-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="0417a-157">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="0417a-157">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="0417a-158">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0417a-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
