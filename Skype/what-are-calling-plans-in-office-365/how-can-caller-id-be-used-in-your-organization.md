---
title: "Identificador de uso en su organización"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Identificador de llamadas puede controlarse en llamadas entrantes y salientes para los usuarios del sistema de teléfono utilizando una directiva denominada CallingLineIdentity."
ms.openlocfilehash: b9e889ae9d87277939e844eeb911834f466942c5
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="bd667-103">Identificador de uso en su organización</span><span class="sxs-lookup"><span data-stu-id="bd667-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="bd667-104">Identificador de llamadas puede controlarse en llamadas entrantes y salientes para los usuarios del sistema de teléfono utilizando una directiva denominada CallingLineIdentity.</span><span class="sxs-lookup"><span data-stu-id="bd667-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="bd667-105">La funcionalidad de identificador de llamadas está disponible para todos los usuarios del sistema telefónico independientemente de conectividad RTC:</span><span class="sxs-lookup"><span data-stu-id="bd667-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="bd667-106">Conectividad RTC en línea</span><span class="sxs-lookup"><span data-stu-id="bd667-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="bd667-107">Conectividad de RTC local con Skype para conector de nube Business Edition (requiere nube conector Edition 1.4.2 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="bd667-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="bd667-108">Conectividad de RTC local con Skype para Business Server (requiere Skype para Business Server 2015 CU5 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="bd667-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="bd667-109">Esta directiva no está disponible en Skype para Business Server de 2015.</span><span class="sxs-lookup"><span data-stu-id="bd667-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="bd667-110">Identificador de llamada saliente</span><span class="sxs-lookup"><span data-stu-id="bd667-110">Outbound caller ID</span></span>

<span data-ttu-id="bd667-111">Hay tres opciones disponibles para el identificador de llamadas salientes de RTC:</span><span class="sxs-lookup"><span data-stu-id="bd667-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="bd667-112">El número de teléfono asignado al usuario, que es el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bd667-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="bd667-113">Un número de teléfono que se clasifica como un *servicio* y número de *línea gratuita* en sus planes de llamar en Office 365 teléfono número de inventario.</span><span class="sxs-lookup"><span data-stu-id="bd667-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="bd667-114">Normalmente se asigna a una cola de operador o llamada de organización automática.</span><span class="sxs-lookup"><span data-stu-id="bd667-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="bd667-115">Establece en anónimo.</span><span class="sxs-lookup"><span data-stu-id="bd667-115">Set to anonymous.</span></span>
    
<span data-ttu-id="bd667-116">Sin embargo, no puede asignar a estos tipos de números de teléfono para el identificador de llamadas salientes:</span><span class="sxs-lookup"><span data-stu-id="bd667-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="bd667-117">Número de los números de teléfono que se clasifican como un *usuario* de su teléfono llamando a los planes de inventario</span><span class="sxs-lookup"><span data-stu-id="bd667-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="bd667-118">Un Skype para Business Server número de teléfono local</span><span class="sxs-lookup"><span data-stu-id="bd667-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="bd667-119">Para establecer el identificador de llamadas salientes, vea [establecer el identificador de un usuario](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bd667-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="bd667-120">Control de usuario final de identificador de llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="bd667-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="bd667-121">El atributo EnableUserOverride permite a los usuarios de uno o varios cambiar su configuración del identificador de llamadas a **anónimo**.</span><span class="sxs-lookup"><span data-stu-id="bd667-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="bd667-122">Esto sólo se aplica cuando se configura una directiva de CallingLineIdentity con un parámetro de CallingIDSubstitute de LineURI o sustituto.</span><span class="sxs-lookup"><span data-stu-id="bd667-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="bd667-123">El valor predeterminado de EnableUserOverride es False.</span><span class="sxs-lookup"><span data-stu-id="bd667-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="bd667-124">Los usuarios finales puede establecer su identificador a **anónimo** mediante la ficha **Llamar configuración hacia delante** en el Skype para cliente de escritorio de negocios.</span><span class="sxs-lookup"><span data-stu-id="bd667-124">Your end users can set their caller ID to **Anonymous** by using the **Call Forward Settings** tab in the Skype for Business desktop client.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="bd667-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="bd667-125">**Windows**</span></span> <br/> |<span data-ttu-id="bd667-126">**Versión**</span><span class="sxs-lookup"><span data-stu-id="bd667-126">**Version**</span></span> <br/> |<span data-ttu-id="bd667-127">**Admite**</span><span class="sxs-lookup"><span data-stu-id="bd667-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="bd667-128">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="bd667-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="bd667-129">Canal actual versión de 6 de diciembre de 2016 - 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="bd667-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="bd667-130">Sí</span><span class="sxs-lookup"><span data-stu-id="bd667-130">Yes</span></span>  <br/> |
|<span data-ttu-id="bd667-131">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="bd667-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="bd667-132">Primera versión para canal aplazado lanzado el 22 de febrero de 2017 - versión 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="bd667-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="bd667-133">Sí</span><span class="sxs-lookup"><span data-stu-id="bd667-133">Yes</span></span>  <br/> |
|<span data-ttu-id="bd667-134">Hacer clic y ejecutar</span><span class="sxs-lookup"><span data-stu-id="bd667-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="bd667-135">Deferred canal lanzado el 13 de junio de 2017 - versión 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="bd667-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="bd667-136">Sí</span><span class="sxs-lookup"><span data-stu-id="bd667-136">Yes</span></span>  <br/> |
|<span data-ttu-id="bd667-137">MSI</span><span class="sxs-lookup"><span data-stu-id="bd667-137">MSI</span></span>  <br/> |<span data-ttu-id="bd667-138">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="bd667-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="bd667-139">No</span><span class="sxs-lookup"><span data-stu-id="bd667-139">No</span></span>  <br/> |
|<span data-ttu-id="bd667-140">Mac</span><span class="sxs-lookup"><span data-stu-id="bd667-140">Mac</span></span>  <br/> |<span data-ttu-id="bd667-141">Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="bd667-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="bd667-142">No</span><span class="sxs-lookup"><span data-stu-id="bd667-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="bd667-143">Identificador de llamadas entrantes</span><span class="sxs-lookup"><span data-stu-id="bd667-143">Inbound Caller ID</span></span>

<span data-ttu-id="bd667-144">El atributo BlockIncomingCallerID permite bloquear el identificador de llamadas en las llamadas entrantes de PSTN.</span><span class="sxs-lookup"><span data-stu-id="bd667-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="bd667-145">Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario.</span><span class="sxs-lookup"><span data-stu-id="bd667-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="bd667-146">Y actualmente sólo está disponible con conectividad PSTN en línea.</span><span class="sxs-lookup"><span data-stu-id="bd667-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="bd667-147">Para establecer el identificador de llamadas salientes, vea [establecer el identificador de un usuario](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="bd667-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bd667-148">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="bd667-148">Related topics</span></span>
[<span data-ttu-id="bd667-149">Transferencia de preguntas habituales de los números de teléfono</span><span class="sxs-lookup"><span data-stu-id="bd667-149">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="bd667-150">Diferentes tipos de números de teléfono utilizados para llamar a planes</span><span class="sxs-lookup"><span data-stu-id="bd667-150">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="bd667-151">Administrar números de teléfono de la organización</span><span class="sxs-lookup"><span data-stu-id="bd667-151">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="bd667-152">Términos y condiciones de las llamadas de emergencias</span><span class="sxs-lookup"><span data-stu-id="bd667-152">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="bd667-153">Skype para los negocios en línea: etiqueta de descargo de responsabilidad llamada de emergencia</span><span class="sxs-lookup"><span data-stu-id="bd667-153">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)