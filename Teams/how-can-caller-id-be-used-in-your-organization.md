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
description: La identificación de llamadas se puede controlar tanto para llamadas entrantes como salientes de usuarios del sistema telefónico mediante una directiva denominada CallingLineIdentity.
ms.openlocfilehash: cd2074fec3027f1172b6ea681013f53994963cb5
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255453"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="59677-103">Cómo se puede usar la identificación de llamadas en su organización</span><span class="sxs-lookup"><span data-stu-id="59677-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="59677-104">La identificación de llamadas se puede controlar tanto para llamadas entrantes como salientes de usuarios del sistema telefónico mediante una directiva denominada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="59677-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="59677-105">La funcionalidad de identificación de llamadas está disponible para todos los usuarios del sistema telefónico con independencia de la conectividad RTC:</span><span class="sxs-lookup"><span data-stu-id="59677-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="59677-106">Planes de llamadas de Microsoft</span><span class="sxs-lookup"><span data-stu-id="59677-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="59677-107">Enrutamiento directo del sistema telefónico</span><span class="sxs-lookup"><span data-stu-id="59677-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="59677-108">Conectividad con RTC en línea</span><span class="sxs-lookup"><span data-stu-id="59677-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="59677-109">Conectividad con RTC local con Skype Empresarial Cloud Connector Edition (requiere Cloud Connector Edition 1.4.2 y posterior)</span><span class="sxs-lookup"><span data-stu-id="59677-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="59677-110">Conectividad con RTC local con Skype Empresarial Server (requiere Skype Empresarial Server 2015 CU5 y posterior)</span><span class="sxs-lookup"><span data-stu-id="59677-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="59677-111">Esta directiva no está disponible en Skype Empresarial 2015 Server.</span><span class="sxs-lookup"><span data-stu-id="59677-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="59677-112">Identificación de llamadas de salida</span><span class="sxs-lookup"><span data-stu-id="59677-112">Outbound caller ID</span></span>

<span data-ttu-id="59677-113">Hay tres opciones disponibles para la identificación de llamadas RTC salientes:</span><span class="sxs-lookup"><span data-stu-id="59677-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="59677-114">El número de teléfono asignado al usuario, que es el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="59677-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="59677-115">Un número de teléfono que se clasifica como un *servicio* y un número *gratuito* en el inventario de números de teléfono de tus planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="59677-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="59677-116">Normalmente, se asigna a una cola de llamadas o de operador automático organizativos.</span><span class="sxs-lookup"><span data-stu-id="59677-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="59677-117">Configurado como anónimo.</span><span class="sxs-lookup"><span data-stu-id="59677-117">Set to anonymous.</span></span>
    
<span data-ttu-id="59677-118">Sin embargo, no es posible asignar estos tipos de números de teléfono al identificador de llamadas de salida:</span><span class="sxs-lookup"><span data-stu-id="59677-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="59677-119">Números de teléfono que se clasifican como un  *usuario*  en el inventario de números de teléfono de los planes de llamadas</span><span class="sxs-lookup"><span data-stu-id="59677-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="59677-120">Un número de teléfono de Skype Empresarial Server local.</span><span class="sxs-lookup"><span data-stu-id="59677-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="59677-121">Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="59677-121">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="59677-122">Control del usuario final de la identificación de llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="59677-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="59677-123">El atributo EnableUserOverride permite a los usuarios únicos o múltiples cambiar la configuración de identificación de llamadas a **anónimo**.</span><span class="sxs-lookup"><span data-stu-id="59677-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="59677-124">Esto solo se aplica cuando una directiva de CallingLineIdentity se configura con un parámetro CallingIDSubstitute de LineURI o Substitute.</span><span class="sxs-lookup"><span data-stu-id="59677-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="59677-125">El valor predeterminado de EnableUserOverride es False.</span><span class="sxs-lookup"><span data-stu-id="59677-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="59677-126">Los usuarios finales pueden establecer la identificación de llamadas en **anónimo** mediante la pestaña **configuración** del cliente de escritorio de Skype empresarial, seleccione **llamadas a un usuario final** (si lo habilita el administrador) y, a continuación, seleccione **ocultar mi número de teléfono y la información del perfil para todas las llamadas**.</span><span class="sxs-lookup"><span data-stu-id="59677-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="59677-127">En Teams, los usuarios pueden ir a su imagen de perfil en la esquina superior derecha **Settings**, seleccionar  >  **llamadas**de configuración y, a continuación, en **identificación de llamadas**, seleccionar **ocultar mi número de teléfono y la información del perfil para todas las llamadas**.</span><span class="sxs-lookup"><span data-stu-id="59677-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="59677-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="59677-128">**Windows**</span></span> <br/> |<span data-ttu-id="59677-129">**Versión**</span><span class="sxs-lookup"><span data-stu-id="59677-129">**Version**</span></span> <br/> |<span data-ttu-id="59677-130">**Compatible**</span><span class="sxs-lookup"><span data-stu-id="59677-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="59677-131">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="59677-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="59677-132">Canal actual publicado el 6 de diciembre de 2016 - Versión 1611 (Compilación 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="59677-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="59677-133">Sí</span><span class="sxs-lookup"><span data-stu-id="59677-133">Yes</span></span>  <br/> |
|<span data-ttu-id="59677-134">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="59677-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="59677-135">Primera versión para el Canal diferido publicada el 22 de febrero de 2017 - Versión 1701 (Compilación 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="59677-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="59677-136">Sí</span><span class="sxs-lookup"><span data-stu-id="59677-136">Yes</span></span>  <br/> |
|<span data-ttu-id="59677-137">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="59677-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="59677-138">Canal diferido publicado el 13 de junio de 2017 - versión 1701 (compilación 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="59677-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="59677-139">Sí</span><span class="sxs-lookup"><span data-stu-id="59677-139">Yes</span></span>  <br/> |
|<span data-ttu-id="59677-140">MSI</span><span class="sxs-lookup"><span data-stu-id="59677-140">MSI</span></span>  <br/> |<span data-ttu-id="59677-141">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="59677-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="59677-142">No</span><span class="sxs-lookup"><span data-stu-id="59677-142">No</span></span>  <br/> |
|<span data-ttu-id="59677-143">Mac</span><span class="sxs-lookup"><span data-stu-id="59677-143">Mac</span></span>  <br/> |<span data-ttu-id="59677-144">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="59677-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="59677-145">No</span><span class="sxs-lookup"><span data-stu-id="59677-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="59677-146">IDENTIFICACIÓN de llamadas entrantes</span><span class="sxs-lookup"><span data-stu-id="59677-146">Inbound caller ID</span></span>

<span data-ttu-id="59677-147">El sistema telefónico mostrará el identificador denominado para un número de teléfono externo si el número está asociado con un usuario en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="59677-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="59677-148">Si el número de teléfono no está en Azure AD, se mostrará el nombre para mostrar proporcionado por Telco, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="59677-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="59677-149">El atributo BlockIncomingCallerID permite bloquear la identificación de llamadas en las llamadas RTC de entrada.</span><span class="sxs-lookup"><span data-stu-id="59677-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="59677-150">Puede establecer este atributo, pero no está disponible para los usuarios finales en la página Configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="59677-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="59677-151">En este momento está solo disponible con la conectividad con RTC en línea.</span><span class="sxs-lookup"><span data-stu-id="59677-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="59677-152">Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="59677-152">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="59677-153">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="59677-153">Related topics</span></span>
[<span data-ttu-id="59677-154">Preguntas comunes sobre la transferencia de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="59677-154">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="59677-155">Diferentes tipos de números de teléfono que se usan para Planes de llamada</span><span class="sxs-lookup"><span data-stu-id="59677-155">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="59677-156">Administrar los números de teléfono para su organización</span><span class="sxs-lookup"><span data-stu-id="59677-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="59677-157">Términos y condiciones de las llamadas de emergencia</span><span class="sxs-lookup"><span data-stu-id="59677-157">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="59677-158">[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="59677-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
