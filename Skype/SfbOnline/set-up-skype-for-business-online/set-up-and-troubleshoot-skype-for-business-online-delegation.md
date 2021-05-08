---
title: Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
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
- Setup
description: En este artículo se explica cómo configurar y solucionar problemas Skype Empresarial delegación en línea. En este artículo se proporcionan instrucciones para las recomendaciones de configuración, los procedimientos recomendados y los pasos de solución de problemas.
ms.openlocfilehash: e5c710849f5829a4a270dc327f71d98185e85c89
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239829"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="a209d-104">Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a209d-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="a209d-105">En este artículo se explica cómo configurar y solucionar problemas Skype Empresarial delegación en línea.</span><span class="sxs-lookup"><span data-stu-id="a209d-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="a209d-106">En este artículo se proporcionan instrucciones para las recomendaciones de configuración, los procedimientos recomendados y los pasos de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="a209d-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="a209d-107">Directrices y requisitos</span><span class="sxs-lookup"><span data-stu-id="a209d-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="a209d-108">Directrices para la delegación</span><span class="sxs-lookup"><span data-stu-id="a209d-108">Guidelines for delegation</span></span>

<span data-ttu-id="a209d-109">Configurar y conseguir que la delegación funcione correctamente depende de si sigue estas directrices:</span><span class="sxs-lookup"><span data-stu-id="a209d-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="a209d-110">Debe usar el cliente completo Skype Empresarial 2015 con las últimas actualizaciones o el cliente completo Skype Empresarial 2016.</span><span class="sxs-lookup"><span data-stu-id="a209d-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="a209d-111">Debe usar el cliente Outlook 2013 con las últimas actualizaciones o el Outlook 2016 cliente.</span><span class="sxs-lookup"><span data-stu-id="a209d-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="a209d-112">Asegúrese de que el delegado y los equipos delegados tienen un Outlook de correo electrónico que es el perfil principal o el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a209d-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="a209d-113">Ese perfil de correo solo debe contener una cuenta.</span><span class="sxs-lookup"><span data-stu-id="a209d-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="a209d-114">Skype Empresarial para el delegado y el delegado deben ser usuarios en línea.</span><span class="sxs-lookup"><span data-stu-id="a209d-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="a209d-115">Además, los Exchange Server para cada cuenta deben ser en línea o ambos locales.</span><span class="sxs-lookup"><span data-stu-id="a209d-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="a209d-116">Tanto el delegado como el delegado deben usar la misma versión principal de Outlook.</span><span class="sxs-lookup"><span data-stu-id="a209d-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="a209d-117">El valor del atributo **EnableExchangeDelegateSync** debe establecerse en **true** en la directiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="a209d-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="a209d-118">Puede comprobar esta configuración ejecutando el cmdlet **Get-CSClientPolicy** en el módulo Skype Empresarial PowerShell en línea.</span><span class="sxs-lookup"><span data-stu-id="a209d-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="a209d-119">Tanto el delegado como el delegado deben haber iniciado sesión en Skype Empresarial y Outlook al mismo tiempo en diferentes estaciones de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a209d-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="a209d-120">Los buzones compartidos no son compatibles con Skype Empresarial delegación en línea.</span><span class="sxs-lookup"><span data-stu-id="a209d-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="a209d-121">Esto se debe a que el buzón compartido no tiene la lista de control de acceso (ACL) **de sendonbehalf.**</span><span class="sxs-lookup"><span data-stu-id="a209d-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="a209d-122">Skype Empresarial versión de cliente</span><span class="sxs-lookup"><span data-stu-id="a209d-122">Skype for Business client version support</span></span>

||<span data-ttu-id="a209d-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="a209d-123">**Outlook 2013**</span></span>|<span data-ttu-id="a209d-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="a209d-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a209d-125">**Lync/Skype Empresarial cliente básico**</span><span class="sxs-lookup"><span data-stu-id="a209d-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="a209d-126">No se admite</span><span class="sxs-lookup"><span data-stu-id="a209d-126">Not supported</span></span> |<span data-ttu-id="a209d-127">No se admite</span><span class="sxs-lookup"><span data-stu-id="a209d-127">Not supported</span></span>
|<span data-ttu-id="a209d-128">**Skype Empresarial 2015**</span><span class="sxs-lookup"><span data-stu-id="a209d-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="a209d-129">Compatible</span><span class="sxs-lookup"><span data-stu-id="a209d-129">Supported</span></span>| <span data-ttu-id="a209d-130">Compatible</span><span class="sxs-lookup"><span data-stu-id="a209d-130">Supported</span></span>|
|<span data-ttu-id="a209d-131">**Skype Empresarial 2016**</span><span class="sxs-lookup"><span data-stu-id="a209d-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="a209d-132">Compatible</span><span class="sxs-lookup"><span data-stu-id="a209d-132">Supported</span></span>| <span data-ttu-id="a209d-133">Compatible</span><span class="sxs-lookup"><span data-stu-id="a209d-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="a209d-134">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="a209d-134">Licensing requirements</span></span>

<span data-ttu-id="a209d-135">**Enterprise Escenario de licencias E3**</span><span class="sxs-lookup"><span data-stu-id="a209d-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="a209d-136">**Licencia**</span><span class="sxs-lookup"><span data-stu-id="a209d-136">**License**</span></span>|<span data-ttu-id="a209d-137">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="a209d-137">**Clients**</span></span>|<span data-ttu-id="a209d-138">**Notas**</span><span class="sxs-lookup"><span data-stu-id="a209d-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a209d-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="a209d-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="a209d-140">Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a209d-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a209d-141">Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a209d-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="a209d-142">Skype Empresarial El cliente básico no admite la delegación.</span><span class="sxs-lookup"><span data-stu-id="a209d-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="a209d-143">Para los clientes Mac, puede delegar llamadas, pero no reuniones.</span><span class="sxs-lookup"><span data-stu-id="a209d-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="a209d-144">Enterprise E3 con Sistema telefónico de Office 365 + Office 365 xCalling Plan</span><span class="sxs-lookup"><span data-stu-id="a209d-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="a209d-145">Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a209d-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a209d-146">Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a209d-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a209d-147">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="a209d-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="a209d-148">Skype Empresarial El cliente básico no admite la delegación.</span><span class="sxs-lookup"><span data-stu-id="a209d-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="a209d-149">Para los clientes Mac, puede delegar llamadas, pero no reuniones.</span><span class="sxs-lookup"><span data-stu-id="a209d-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="a209d-150">**Enterprise Escenario de licencias E5**</span><span class="sxs-lookup"><span data-stu-id="a209d-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="a209d-151">**Licencia**</span><span class="sxs-lookup"><span data-stu-id="a209d-151">**License**</span></span>|<span data-ttu-id="a209d-152">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="a209d-152">**Clients**</span></span>|<span data-ttu-id="a209d-153">**Notas**</span><span class="sxs-lookup"><span data-stu-id="a209d-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a209d-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="a209d-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="a209d-155">Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="a209d-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="a209d-156">Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a209d-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="a209d-157">Skype Empresarial El cliente básico no admite la delegación.</span><span class="sxs-lookup"><span data-stu-id="a209d-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="a209d-158">Para los clientes Mac, puede delegar llamadas, pero no reuniones.</span><span class="sxs-lookup"><span data-stu-id="a209d-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="a209d-159">Enterprise E5 más Office 365 plan de llamadas</span><span class="sxs-lookup"><span data-stu-id="a209d-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="a209d-160">Skype Empresarial para Mac 2016</span><span class="sxs-lookup"><span data-stu-id="a209d-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="a209d-161">Lync 2013 (Skype Empresarial 2015) usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a209d-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a209d-162">Skype Empresarial 2016 usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a209d-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="a209d-163">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="a209d-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="a209d-164">Skype Empresarial El cliente básico no admite la delegación.</span><span class="sxs-lookup"><span data-stu-id="a209d-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="a209d-165">Para los clientes Mac, puede delegar llamadas, pero no reuniones.</span><span class="sxs-lookup"><span data-stu-id="a209d-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="a209d-166">Configurar y comprobar la delegación</span><span class="sxs-lookup"><span data-stu-id="a209d-166">Set up and verify delegation</span></span>

<span data-ttu-id="a209d-167">Para configurar la Skype Empresarial en línea, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a209d-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="a209d-168">Para Windows clientes</span><span class="sxs-lookup"><span data-stu-id="a209d-168">For Windows clients</span></span>

 <span data-ttu-id="a209d-169">**Pestaña Reenvío de llamadas**</span><span class="sxs-lookup"><span data-stu-id="a209d-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="a209d-170">Seleccione **Herramientas Opciones**  >  **de** reenvío de llamadas  >  **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="a209d-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="a209d-171">Seleccione **Editar mis miembros delegados.**</span><span class="sxs-lookup"><span data-stu-id="a209d-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="a209d-172">Seleccione **Agregar**, seleccione el delegado que desea agregar y, a continuación, seleccione **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="a209d-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="a209d-173">**Pestaña Sin reenvío de llamadas**</span><span class="sxs-lookup"><span data-stu-id="a209d-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="a209d-174">En Outlook, seleccione Cuenta  >  **de archivo Configuración** Agregar acceso  >    >  **delegado.**</span><span class="sxs-lookup"><span data-stu-id="a209d-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="a209d-175">Busque y agregue el nombre de la persona que va a ser el delegado.</span><span class="sxs-lookup"><span data-stu-id="a209d-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="a209d-176">Seleccione el **menú** Calendario y, a continuación, **seleccione Editor (puede leer, crear y modificar elementos).**</span><span class="sxs-lookup"><span data-stu-id="a209d-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="a209d-177">Para clientes Mac: Lync</span><span class="sxs-lookup"><span data-stu-id="a209d-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="a209d-178">**Pestaña Reenvío de llamadas**</span><span class="sxs-lookup"><span data-stu-id="a209d-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="a209d-179">Si el cliente no  tiene una pestaña Desviado de llamadas que tiene el vínculo Editar mis miembros delegados y el delegado se encuentra en un equipo Mac, el delegado debe iniciar sesión en un equipo basado en Windows para configurar la delegación. </span><span class="sxs-lookup"><span data-stu-id="a209d-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="a209d-180">Esto se debe a que los clientes Mac no pueden realizar conexiones MAPI y este es un requisito para establecer Skype Empresarial delegación desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="a209d-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="a209d-181">Comprobar el éxito</span><span class="sxs-lookup"><span data-stu-id="a209d-181">Verify success</span></span>

<span data-ttu-id="a209d-182">Si la configuración se realiza correctamente, el delegado debería ver el mensaje Se le agregó  como delegado para < Nombre>y también que se crea el grupo Personas que administra llamadas **para.**</span><span class="sxs-lookup"><span data-stu-id="a209d-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="a209d-183">El delegado debe ver que se crea el **grupo** Delegados.</span><span class="sxs-lookup"><span data-stu-id="a209d-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a209d-184">Los permisos de delegación suelen aparecer en un plazo de 30 minutos desde el proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="a209d-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="a209d-185">Sin embargo, este proceso puede tardar hasta 24 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="a209d-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="a209d-186">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="a209d-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="a209d-187">Problemas comunes</span><span class="sxs-lookup"><span data-stu-id="a209d-187">Common issues</span></span>

- > <span data-ttu-id="a209d-188">**Problema 1** La entrada de delegado sigue apareciendo en el grupo Personas que administra llamadas **para** después de que el delegado haya quitado el delegado del Outlook cliente.</span><span class="sxs-lookup"><span data-stu-id="a209d-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="a209d-189">**Resolución 1** En el Skype Empresarial, haga clic con el botón derecho en el delegado en el grupo **Delegados** y, a continuación, **seleccione Quitar del grupo.**</span><span class="sxs-lookup"><span data-stu-id="a209d-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="a209d-190">**Problema 2** Una vez concedido el acceso delegado a través del cliente Outlook, ni el mensaje de confirmación ni el grupo Personas que administra llamadas **para** aparecen para el delegado.</span><span class="sxs-lookup"><span data-stu-id="a209d-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="a209d-191">**Resolución 2** Quite la delegación del Outlook, espere unos 15 minutos para la replicación y, a continuación, agregue de nuevo el delegado.</span><span class="sxs-lookup"><span data-stu-id="a209d-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="a209d-192">Otros problemas comunes</span><span class="sxs-lookup"><span data-stu-id="a209d-192">Other common issues</span></span>

- <span data-ttu-id="a209d-193">La delegación no funciona si se supera el umbral de 25 delegados y 25 delegados.</span><span class="sxs-lookup"><span data-stu-id="a209d-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="a209d-194">El Skype Empresarial basic no es compatible.</span><span class="sxs-lookup"><span data-stu-id="a209d-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a209d-195">Si instala el Skype Empresarial Basic, quitará y interrumpirá la delegación.</span><span class="sxs-lookup"><span data-stu-id="a209d-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="a209d-196">Si el **valor Estado MAPI** no es **correcto,** asegúrese de que los valores **SIP** y **SMTP** coinciden.</span><span class="sxs-lookup"><span data-stu-id="a209d-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a209d-197">El estado MAPI puede tardar varios  minutos en mostrarse como correcto después de iniciar por primera vez Skype Empresarial y Outlook.</span><span class="sxs-lookup"><span data-stu-id="a209d-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="a209d-198">No se admite la creación de un grupo de seguridad y la adición de permisos de delegación para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="a209d-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="a209d-199">MAPI no está disponible.</span><span class="sxs-lookup"><span data-stu-id="a209d-199">MAPI is unavailable.</span></span> <span data-ttu-id="a209d-200">Vea [el error "MAPI no disponible" en Skype Empresarial cliente de 2016.](https://support.microsoft.com/help/3147130)</span><span class="sxs-lookup"><span data-stu-id="a209d-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/help/3147130).</span></span>
    
- <span data-ttu-id="a209d-201">El Exchange Online de correo electrónico no es accesible a través Skype Empresarial cliente.</span><span class="sxs-lookup"><span data-stu-id="a209d-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="a209d-202">Si esto ocurre, ejecute la prueba [Outlook de conectividad para](https://testconnectivity.microsoft.com/) asegurarse de que se supera.</span><span class="sxs-lookup"><span data-stu-id="a209d-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a209d-203">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a209d-203">Related topics</span></span>
[<span data-ttu-id="a209d-204">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="a209d-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="a209d-205">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="a209d-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
