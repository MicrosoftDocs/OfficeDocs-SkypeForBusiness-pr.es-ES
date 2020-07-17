---
title: Caso práctico de voz de Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786096"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a><span data-ttu-id="ac3e8-103">Caso práctico de Contoso: los operadores automáticos y las colas de llamadas</span><span class="sxs-lookup"><span data-stu-id="ac3e8-103">Contoso case study: Auto attendants and call queues</span></span>

<span data-ttu-id="ac3e8-104">Contoso está familiarizado con los operadores automáticos y las colas de llamadas desde su implementación local de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-104">Contoso was familiar with auto attendants and call queues from their on-premises Skype for Business deployment.</span></span> <span data-ttu-id="ac3e8-105">Para comprender cómo se configuran los operadores automáticos de la nube, revisan [Qué son los operadores automáticos de la nube](what-are-phone-system-auto-attendants.md) y [ejemplo de Small Business-configurar tutorial de operador automático](tutorial-org-aa.yml).</span><span class="sxs-lookup"><span data-stu-id="ac3e8-105">To understand how to set up Cloud auto attendants, they reviewed [What are Cloud auto attendants?](what-are-phone-system-auto-attendants.md) and [Small business  example - Set up auto attendant tutorial](tutorial-org-aa.yml).</span></span> <span data-ttu-id="ac3e8-106">Para obtener más información sobre las opciones disponibles para configurar las colas de llamadas, contoso ha revisado [crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="ac3e8-106">To learn about the options available to set up call queues, Contoso reviewed [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

## <a name="requirements-depending-on-site-type"></a><span data-ttu-id="ac3e8-107">Requisitos según el tipo de sitio</span><span class="sxs-lookup"><span data-stu-id="ac3e8-107">Requirements depending on site type</span></span>

<span data-ttu-id="ac3e8-108">Según el tipo de sitio, contoso tuvo las siguientes necesidades:</span><span class="sxs-lookup"><span data-stu-id="ac3e8-108">Depending on the site type, Contoso had the following needs:</span></span>

- <span data-ttu-id="ac3e8-109">Tipo de sitio A: sistemas tradicionales de telefonía heredados</span><span class="sxs-lookup"><span data-stu-id="ac3e8-109">Site Type A: Traditional legacy telephony systems</span></span> 

  <span data-ttu-id="ac3e8-110">Tipo de sitio a necesario para mantener el mismo número de teléfono asociado a la recepcionista que el número de sus operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-110">Site Type A needed to keep the same phone number associated with the receptionist as the number for their auto attendants.</span></span> <span data-ttu-id="ac3e8-111">Los departamentos clave de cada uno de estos sitios tendrían sus propias colas de llamadas que se dirigirían a los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-111">The key departments for each of these sites would have their own call queues that would route to team members.</span></span> <span data-ttu-id="ac3e8-112">Había una combinación de sitios que usaban el sistema telefónico con enrutamiento directo y sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-112">There was a mixture of sites that used Phone System with Direct Routing and Phone System with Calling Plans.</span></span>  

- <span data-ttu-id="ac3e8-113">Tipo de sitio B: voz de Skype empresarial Enterprise</span><span class="sxs-lookup"><span data-stu-id="ac3e8-113">Site Type B: Skype for Business Enterprise Voice</span></span> 

  <span data-ttu-id="ac3e8-114">El tipo de sitio B tenía operadores automáticos y colas de llamadas que necesitaban migrar a teams.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-114">Site Type B had existing auto attendants and call queues that needed to migrate to Teams.</span></span> <span data-ttu-id="ac3e8-115">Contoso necesitaba mantener los números de teléfono asociados con los operadores automáticos.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-115">Contoso needed to keep the phone numbers associated with the auto attendants.</span></span> <span data-ttu-id="ac3e8-116">Contoso movió la mayoría de estos sitios a un sistema telefónico con planes de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-116">Contoso moved the majority of these sites to Phone System with Calling Plans.</span></span> <span data-ttu-id="ac3e8-117">Sin embargo, en las pocas ubicaciones en las que los planes de llamadas no estaban disponibles, contoso movió estos sitios a una configuración de enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-117">However, in the few locations where Calling Plans was not available, Contoso moved these sites to a Direct Routing configuration.</span></span>  

- <span data-ttu-id="ac3e8-118">Tipo de sitio C: Skype empresarial Voice & sistema de telefonía tradicional tradicional</span><span class="sxs-lookup"><span data-stu-id="ac3e8-118">Site Type C: Skype for Business Enterprise Voice & traditional legacy telephony system</span></span> 

  <span data-ttu-id="ac3e8-119">El tipo de sitio C tenía operadores automáticos existentes que residían en el sistema de telefonía tradicional heredado.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-119">Site Type C had existing auto attendants that resided in the traditional legacy telephony system.</span></span> <span data-ttu-id="ac3e8-120">Las decisiones y configuraciones de este sitio eran las mismas que las del tipo A.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-120">The decisions and configurations for this site were the same as Site Type A.</span></span>   

- <span data-ttu-id="ac3e8-121">Para todos los tipos de sitios, contoso preguntó las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="ac3e8-121">For all site types, Contoso asked the following questions:</span></span>

  - <span data-ttu-id="ac3e8-122">P: ¿usaremos números nuevos o existentes?</span><span class="sxs-lookup"><span data-stu-id="ac3e8-122">Q: Will we use new or existing numbers?</span></span> 
    <span data-ttu-id="ac3e8-123">A: contoso decidió usar números de teléfono existentes para asignarlos a la cuenta de servicio del operador automático.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-123">A: Contoso decided to use existing phone numbers to be assigned to the service account for the auto attendant.</span></span> 

  - <span data-ttu-id="ac3e8-124">P: ¿Cuándo estará disponible el operador automático para aceptar las llamadas entrantes?</span><span class="sxs-lookup"><span data-stu-id="ac3e8-124">Q: When will the auto attendant be available to accept incoming calls?</span></span> 
    <span data-ttu-id="ac3e8-125">A: contoso decidió establecer las horas laborales y recibir llamadas después de las horas de oficina redirigidas a un operador automático "fuera del horario".</span><span class="sxs-lookup"><span data-stu-id="ac3e8-125">A: Contoso decided to set business hours and have calls received after business hours redirected to an "after-hours" auto attendant.</span></span>  

  - <span data-ttu-id="ac3e8-126">P: ¿cómo se enrutarán las llamadas a los miembros en una cola de llamadas: operador, serie o enrutamiento Round Robin?</span><span class="sxs-lookup"><span data-stu-id="ac3e8-126">Q: How will the calls be routed to members in a call queue: attendant, serial, or round robin routing?</span></span> 
    <span data-ttu-id="ac3e8-127">A: contoso decidió usar el enrutamiento de operador,</span><span class="sxs-lookup"><span data-stu-id="ac3e8-127">A: Contoso decided to use Attendant routing,</span></span> 

  - <span data-ttu-id="ac3e8-128">P: ¿cómo determinamos Cuándo un usuario debería o no recibir una llamada?</span><span class="sxs-lookup"><span data-stu-id="ac3e8-128">Q: How will we determine when a user should or should not get a call?</span></span> 
    <span data-ttu-id="ac3e8-129">A: contoso decidió usar las opciones de administración de llamadas para determinar si el agente está disponible: enrutamiento basado en presencia.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-129">A: Contoso decided to use call handling options to determine if the agent is available: presence-based routing.</span></span> 


## <a name="configuration"></a><span data-ttu-id="ac3e8-130">Configuración</span><span class="sxs-lookup"><span data-stu-id="ac3e8-130">Configuration</span></span>

<span data-ttu-id="ac3e8-131">Los pasos para configurar un operador automático y una cola de llamadas incluyen los siguientes esquemas en [administrar cuentas de recursos](manage-resource-accounts.md):</span><span class="sxs-lookup"><span data-stu-id="ac3e8-131">The steps to set up an auto attendant and a call queue include the following outlined in [Manage resource accounts](manage-resource-accounts.md):</span></span> 

1. <span data-ttu-id="ac3e8-132">Obtener un número de servicio.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-132">Obtain a service number.</span></span> 

2. <span data-ttu-id="ac3e8-133">Obtener un sistema telefónico gratis: licencia de usuario virtual o una licencia de sistema telefónico de pagos para usar con la cuenta de recursos o una licencia de sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-133">Obtain a free Phone System - Virtual User license or a paid Phone System license to use with the resource account or a Phone System license.</span></span>

3. <span data-ttu-id="ac3e8-134">Crear la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-134">Create the resource account.</span></span> <span data-ttu-id="ac3e8-135">Para tener una cuenta de recursos asociada, es necesario un operador automático o una cola de llamadas.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-135">An auto attendant or call queue is required to have an associated resource account.</span></span> 

4. <span data-ttu-id="ac3e8-136">Asigne el sistema telefónico o un sistema telefónico (licencia de usuario virtual) a la cuenta de recursos.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-136">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span> <span data-ttu-id="ac3e8-137">Para obtener más información, consulte [Microsoft 365 Phone System-virtual User License](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span><span class="sxs-lookup"><span data-stu-id="ac3e8-137">For more information, see [Microsoft 365 Phone System – Virtual User license](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).</span></span>

5. <span data-ttu-id="ac3e8-138">Asigne un número de teléfono de servicio a la cuenta de recursos a la que asignó licencias.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-138">Assign a service phone number to the resource account you assigned licenses to.</span></span> 

6. <span data-ttu-id="ac3e8-139">Crear una cola de llamadas de sistema telefónicas o un operador automático</span><span class="sxs-lookup"><span data-stu-id="ac3e8-139">Create a Phone System call queue or auto attendant</span></span> 

7. <span data-ttu-id="ac3e8-140">Vincular la cuenta de recursos con una cola de llamadas o un operador automático.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-140">Link the resource account with a call queue or auto attendant.</span></span> 


### <a name="sites-with-phone-system-with-direct-routing"></a><span data-ttu-id="ac3e8-141">Sitios con sistema telefónico con enrutamiento directo</span><span class="sxs-lookup"><span data-stu-id="ac3e8-141">Sites with Phone System with Direct routing</span></span> 

<span data-ttu-id="ac3e8-142">Contoso tenía que configurar el número de teléfono proporcionado por el operador local como número de servicio en Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-142">Contoso had to set up the phone number provided by the local carrier as the service number in Office 365.</span></span> 

- <span data-ttu-id="ac3e8-143">Para configurar un número de teléfono disponible mediante enrutamiento directo, contoso siguió las instrucciones que se encuentran en [administrar cuentas de recursos](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="ac3e8-143">To set up a phone number available through Direct Routing, Contoso followed the instructions located in [Manage Resource Accounts](manage-resource-accounts.md).</span></span> <span data-ttu-id="ac3e8-144">Puesto que Office 365 no reconoce los números de teléfono locales, contoso usó PowerShell para completar la configuración.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-144">Because Office 365 is not aware of the on-premises phone numbers, Contoso used PowerShell to complete the setup.</span></span>   

- <span data-ttu-id="ac3e8-145">Para configurar el operador automático de la nube, contoso siguió los pasos indicados en [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="ac3e8-145">To configure the Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> 

- <span data-ttu-id="ac3e8-146">Para configurar una cola de llamadas en la nube, contoso siguió los pasos indicados en [crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="ac3e8-146">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  


### <a name="sites-with-phone-system-with-calling-plan"></a><span data-ttu-id="ac3e8-147">Sitios con sistema telefónico con plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="ac3e8-147">Sites with Phone System with Calling plan</span></span>

<span data-ttu-id="ac3e8-148">Contoso tenía que migrar el número de teléfono que se usó para los operadores automáticos de Skype empresarial Enterprise Voice al sistema telefónico de Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-148">Contoso had to port the phone number that was used for Skype for Business Enterprise Voice auto attendants to Office 365 Phone System.</span></span> <span data-ttu-id="ac3e8-149">Permite que el mismo número se asigne como un número de servicio para usarlo como un operador automático.</span><span class="sxs-lookup"><span data-stu-id="ac3e8-149">This allowed the same number to be assigned as a service number for use as an auto attendant.</span></span> 

- <span data-ttu-id="ac3e8-150">Para migrar el número de teléfono, contoso siguió las instrucciones de [transferir números de teléfono a teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) y obtener instrucciones adicionales [para administrar los números de teléfono de su organización](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="ac3e8-150">To port the phone number, Contoso followed the instructions in [Transfer phone numbers to Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) and obtained additional guidance at [Manage phone numbers for your organization](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).</span></span>

- <span data-ttu-id="ac3e8-151">Para configurar un operador automático de la nube, contoso siguió los pasos indicados en [configurar un operador automático de la nube](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="ac3e8-151">To configure a Cloud auto attendant, Contoso followed the steps outlined in [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span>

-  <span data-ttu-id="ac3e8-152">Para configurar una cola de llamadas en la nube, contoso siguió los pasos indicados en [crear una cola de llamadas en la nube](create-a-phone-system-call-queue.md).</span><span class="sxs-lookup"><span data-stu-id="ac3e8-152">To set up a Cloud call queue, Contoso followed the steps outlined in [Create a Cloud call queue](create-a-phone-system-call-queue.md).</span></span>  

 