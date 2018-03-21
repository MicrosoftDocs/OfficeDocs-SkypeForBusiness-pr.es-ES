---
title: "Configurar y solucionar problemas de Skype para la delegación de los negocios en línea"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "En este artículo se explica cómo configurar y solucionar problemas de Skype para la delegación de los negocios en línea. En este artículo se ofrece instrucciones para instalación recomendaciones, prácticas recomendadas y pasos para solucionar problemas."
ms.openlocfilehash: 36dde5040471979a95be1ec8c9e0eb30fef739de
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="46a40-104">Configurar y solucionar problemas de Skype para la delegación de los negocios en línea</span><span class="sxs-lookup"><span data-stu-id="46a40-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="46a40-105">En este artículo se explica cómo configurar y solucionar problemas de Skype para la delegación de los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="46a40-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="46a40-106">En este artículo se ofrece instrucciones para instalación recomendaciones, prácticas recomendadas y pasos para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="46a40-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="46a40-107">Requisitos y directrices</span><span class="sxs-lookup"><span data-stu-id="46a40-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="46a40-108">Directrices para la delegación</span><span class="sxs-lookup"><span data-stu-id="46a40-108">Guidelines for delegation</span></span>

<span data-ttu-id="46a40-109">Configurar y obtener la delegación funcione correctamente dependen de seguir estas directrices:</span><span class="sxs-lookup"><span data-stu-id="46a40-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="46a40-110">Debe utilizar el Skype para 2015 de negocio cliente completo con las actualizaciones más recientes o el Skype para el cliente completo de 2016 de negocio.</span><span class="sxs-lookup"><span data-stu-id="46a40-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="46a40-111">Debe utilizar el cliente de Outlook 2013 con las últimas actualizaciones o el cliente de Outlook de 2016.</span><span class="sxs-lookup"><span data-stu-id="46a40-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="46a40-112">Asegúrese de que la persona que delega y delegado equipos tienen un perfil de correo de Outlook que es el principal o el perfil predeterminado.</span><span class="sxs-lookup"><span data-stu-id="46a40-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="46a40-113">Que el perfil de correo debe contener sólo una cuenta.</span><span class="sxs-lookup"><span data-stu-id="46a40-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="46a40-114">Skype para el negocio para la persona que delega y el delegado debe ser usuarios en línea.</span><span class="sxs-lookup"><span data-stu-id="46a40-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="46a40-115">Además, los buzones de Exchange Server para cada cuenta debe estar en línea o ser locales.</span><span class="sxs-lookup"><span data-stu-id="46a40-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="46a40-116">El usuario delegado y el delegado deben utilizar la misma versión principal de Outlook.</span><span class="sxs-lookup"><span data-stu-id="46a40-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="46a40-117">El valor del atributo **EnableExchangeDelegateSync** debe establecerse en **true** en la directiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="46a40-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="46a40-118">Puede comprobar esta configuración ejecutando el cmdlet **Get-CSClientPolicy** en el Skype para el módulo de PowerShell en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="46a40-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="46a40-119">El usuario delegado y el delegado deben iniciar sesión en Skype para Outlook y del negocio al mismo tiempo en diferentes estaciones de trabajo.</span><span class="sxs-lookup"><span data-stu-id="46a40-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="46a40-120">Skype no admiten los buzones compartidos para la delegación de los negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="46a40-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="46a40-121">Esto es porque el buzón compartido no tiene la lista de control de acceso (ACL) de **sendonbehalf** .</span><span class="sxs-lookup"><span data-stu-id="46a40-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="46a40-122">Skype para compatibilidad con la versión de cliente de empresa</span><span class="sxs-lookup"><span data-stu-id="46a40-122">Skype for Business client version support</span></span>

||<span data-ttu-id="46a40-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="46a40-123">**Outlook 2013**</span></span>|<span data-ttu-id="46a40-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="46a40-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46a40-125">**Lync/Skype para cliente básico de negocio**</span><span class="sxs-lookup"><span data-stu-id="46a40-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="46a40-126">No se admite</span><span class="sxs-lookup"><span data-stu-id="46a40-126">Not supported</span></span> |<span data-ttu-id="46a40-127">No se admite</span><span class="sxs-lookup"><span data-stu-id="46a40-127">Not supported</span></span>
|<span data-ttu-id="46a40-128">**Skype para negocios 2015**</span><span class="sxs-lookup"><span data-stu-id="46a40-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="46a40-129">Compatible</span><span class="sxs-lookup"><span data-stu-id="46a40-129">Supported</span></span>| <span data-ttu-id="46a40-130">Compatible</span><span class="sxs-lookup"><span data-stu-id="46a40-130">Supported</span></span>|
|<span data-ttu-id="46a40-131">**Skype para negocios de 2016**</span><span class="sxs-lookup"><span data-stu-id="46a40-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="46a40-132">Compatible</span><span class="sxs-lookup"><span data-stu-id="46a40-132">Supported</span></span>| <span data-ttu-id="46a40-133">Compatible</span><span class="sxs-lookup"><span data-stu-id="46a40-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="46a40-134">Requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="46a40-134">Licensing requirements</span></span>

<span data-ttu-id="46a40-135">**Escenario de licencias de empresa E3**</span><span class="sxs-lookup"><span data-stu-id="46a40-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="46a40-136">**Licencia**</span><span class="sxs-lookup"><span data-stu-id="46a40-136">**License**</span></span>|<span data-ttu-id="46a40-137">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="46a40-137">**Clients**</span></span>|<span data-ttu-id="46a40-138">**Notas**</span><span class="sxs-lookup"><span data-stu-id="46a40-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46a40-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="46a40-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="46a40-140">Lync 2013 (Skype para negocios 2015) se utiliza con Outlook 2013 o 2016 de Outlook</span><span class="sxs-lookup"><span data-stu-id="46a40-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="46a40-141">Skype para 2016 de negocio se utiliza con Outlook 2013 o 2016 de Outlook</span><span class="sxs-lookup"><span data-stu-id="46a40-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="46a40-142">Skype para cliente Business Basic no admite la delegación.</span><span class="sxs-lookup"><span data-stu-id="46a40-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="46a40-143">Para los clientes de Mac, puede delegar llamadas pero no las reuniones.</span><span class="sxs-lookup"><span data-stu-id="46a40-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="46a40-144">E3 de empresa con sistema de teléfono de Office 365 + xCalling Plan de Office 365</span><span class="sxs-lookup"><span data-stu-id="46a40-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="46a40-145">Lync 2013 (Skype para negocios 2015) se utiliza con Outlook 2013 o 2016 de Outlook</span><span class="sxs-lookup"><span data-stu-id="46a40-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="46a40-146">Skype para 2016 de negocio se utiliza con Outlook 2013 o 2016 de Outlook</span><span class="sxs-lookup"><span data-stu-id="46a40-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="46a40-147">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="46a40-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="46a40-148">Skype para cliente Business Basic no admite la delegación.</span><span class="sxs-lookup"><span data-stu-id="46a40-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="46a40-149">Para los clientes de Mac, puede delegar llamadas pero no las reuniones.</span><span class="sxs-lookup"><span data-stu-id="46a40-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="46a40-150">**Escenario de licencias de empresa E5**</span><span class="sxs-lookup"><span data-stu-id="46a40-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="46a40-151">**Licencia**</span><span class="sxs-lookup"><span data-stu-id="46a40-151">**License**</span></span>|<span data-ttu-id="46a40-152">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="46a40-152">**Clients**</span></span>|<span data-ttu-id="46a40-153">**Notas**</span><span class="sxs-lookup"><span data-stu-id="46a40-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46a40-154">E5 de la empresa</span><span class="sxs-lookup"><span data-stu-id="46a40-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="46a40-155">Lync 2013 (Skype para negocios 2015) se utiliza con Outlook 2013 o 2016 de Outlook.</span><span class="sxs-lookup"><span data-stu-id="46a40-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="46a40-156">Skype para 2016 de negocio se utiliza con Outlook 2013 o 2016 de Outlook</span><span class="sxs-lookup"><span data-stu-id="46a40-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="46a40-157">Skype para cliente Business Basic no admite la delegación.</span><span class="sxs-lookup"><span data-stu-id="46a40-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="46a40-158">Para los clientes de Mac, puede delegar llamadas pero no las reuniones.</span><span class="sxs-lookup"><span data-stu-id="46a40-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="46a40-159">E5 Enterprise plus Plan de llamada Office 365</span><span class="sxs-lookup"><span data-stu-id="46a40-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="46a40-160">Skype para empresas para Mac 2016</span><span class="sxs-lookup"><span data-stu-id="46a40-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="46a40-161">Lync 2013 (Skype para negocios 2015) se utiliza con Outlook 2013 o 2016 de Outlook</span><span class="sxs-lookup"><span data-stu-id="46a40-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="46a40-162">Skype para 2016 de negocio se utiliza con Outlook 2013 o 2016 de Outlook</span><span class="sxs-lookup"><span data-stu-id="46a40-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="46a40-163">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="46a40-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="46a40-164">Skype para cliente Business Basic no admite la delegación.</span><span class="sxs-lookup"><span data-stu-id="46a40-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="46a40-165">Para los clientes de Mac, puede delegar llamadas pero no las reuniones.</span><span class="sxs-lookup"><span data-stu-id="46a40-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="46a40-166">Configurar y comprobar la delegación</span><span class="sxs-lookup"><span data-stu-id="46a40-166">Set up and verify delegation</span></span>

<span data-ttu-id="46a40-167">Para configurar Skype para la delegación de los negocios en línea, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="46a40-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="46a40-168">Para clientes Windows</span><span class="sxs-lookup"><span data-stu-id="46a40-168">For Windows clients</span></span>

 <span data-ttu-id="46a40-169">**Ficha de reenvío de llamada**</span><span class="sxs-lookup"><span data-stu-id="46a40-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="46a40-170">Seleccione **Herramientas** > **Opciones de** > **configuración de desvío de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="46a40-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="46a40-171">Seleccione **Editar a los miembros de mi delegado**.</span><span class="sxs-lookup"><span data-stu-id="46a40-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="46a40-172">Seleccione **Agregar**, seleccione al delegado al que desea agregar y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46a40-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="46a40-173">**No hay ficha de reenvío de llamada**</span><span class="sxs-lookup"><span data-stu-id="46a40-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="46a40-174">En Outlook, seleccione **archivo** > **Configuración de la cuenta** > **Acceso delegado** > **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="46a40-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="46a40-175">Busque y, a continuación, agregue el nombre de la persona que va a ser el delegado.</span><span class="sxs-lookup"><span data-stu-id="46a40-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="46a40-176">Seleccione el menú **calendario** y, a continuación, seleccione **Editor (puede leer, crear y modificar elementos)**.</span><span class="sxs-lookup"><span data-stu-id="46a40-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="46a40-177">Para los clientes de Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="46a40-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="46a40-178">**Ficha de reenvío de llamada**</span><span class="sxs-lookup"><span data-stu-id="46a40-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="46a40-179">Si el cliente no tiene una ficha de **Reenvío de llamada** que tiene el vínculo **Editar los miembros de mi delegado** , y el usuario delegado se encuentra en un equipo Mac, la persona que delega debe iniciar sesión en un equipo basado en Windows para configurar la delegación.</span><span class="sxs-lookup"><span data-stu-id="46a40-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="46a40-180">Esto es porque los clientes de Mac no pueden establecer conexiones de MAPI y es un requisito para establecer Skype para la delegación de negocio desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="46a40-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="46a40-181">Verifique el éxito</span><span class="sxs-lookup"><span data-stu-id="46a40-181">Verify success</span></span>

<span data-ttu-id="46a40-182">Si la configuración es correcta, el delegado debería ver la **ha sido agregado como delegado para < nombre >** mensaje y también se crea el grupo de **personas administrar llamadas para** .</span><span class="sxs-lookup"><span data-stu-id="46a40-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="46a40-183">La persona que delega debe ver que se crea el grupo de **delegados** .</span><span class="sxs-lookup"><span data-stu-id="46a40-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="46a40-184">Permisos de delegación suelen aparecerán dentro de 30 minutos del proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="46a40-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="46a40-185">Sin embargo, este proceso puede tardar hasta 24 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="46a40-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="46a40-186">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="46a40-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="46a40-187">Problemas comunes</span><span class="sxs-lookup"><span data-stu-id="46a40-187">Common issues</span></span>

- > <span data-ttu-id="46a40-188">**Problema 1** La entrada de delegado sigue apareciendo en el grupo de **personas administrar llamadas para** después el usuario delegado quitó al delegado desde el cliente de Outlook.</span><span class="sxs-lookup"><span data-stu-id="46a40-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="46a40-189">**Resolución 1** En Skype para Business client, haga al delegado en el grupo de **delegados** y, a continuación, seleccione **Quitar del grupo**.</span><span class="sxs-lookup"><span data-stu-id="46a40-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="46a40-190">**Problema 2** Una vez concedido el acceso de delegado a través del cliente de Outlook, el mensaje de confirmación ni el grupo de **personas administrar llamadas para** aparecen para el delegado.</span><span class="sxs-lookup"><span data-stu-id="46a40-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="46a40-191">**Resolución 2** Quitar la delegación desde el cliente Outlook, espere unos 15 minutos para la replicación y, a continuación, vuelva a agregar al delegado.</span><span class="sxs-lookup"><span data-stu-id="46a40-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="46a40-192">Otros problemas comunes</span><span class="sxs-lookup"><span data-stu-id="46a40-192">Other common issues</span></span>

- <span data-ttu-id="46a40-193">La delegación no funcionará si se excede el umbral de 25 delegators y 25 delegados.</span><span class="sxs-lookup"><span data-stu-id="46a40-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="46a40-194">No se admite el Skype para cliente empresarial básico.</span><span class="sxs-lookup"><span data-stu-id="46a40-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="46a40-195">Si instala el Skype para cliente empresarial básico, quitará y romper la delegación.</span><span class="sxs-lookup"><span data-stu-id="46a40-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="46a40-196">Si el valor de **Estado de MAPI** no es **Aceptar**, asegúrese de que coinciden con los valores **SIP** y **SMTP** .</span><span class="sxs-lookup"><span data-stu-id="46a40-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="46a40-197">Puede tardar varios minutos para que el estado MAPI mostrar como **Aceptar** después de iniciar por primera vez Skype para Outlook y del negocio.</span><span class="sxs-lookup"><span data-stu-id="46a40-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="46a40-198">Crear un grupo de seguridad y agregar permisos de delegación de ese grupo de seguridad no es compatible.</span><span class="sxs-lookup"><span data-stu-id="46a40-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="46a40-199">MAPI no está disponible.</span><span class="sxs-lookup"><span data-stu-id="46a40-199">MAPI is unavailable.</span></span> <span data-ttu-id="46a40-200">Vea el [error de "MAPI no disponible" de Skype para 2016 de negocio cliente](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="46a40-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="46a40-201">El buzón de Exchange en línea no es accesible a través del Skype para Business client.</span><span class="sxs-lookup"><span data-stu-id="46a40-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="46a40-202">Si esto ocurre, ejecute la [prueba de conectividad de Outlook](https://testconnectivity.microsoft.com/) para asegurarse de que pasa.</span><span class="sxs-lookup"><span data-stu-id="46a40-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="46a40-203">See also</span><span class="sxs-lookup"><span data-stu-id="46a40-203">Related topics</span></span>
[<span data-ttu-id="46a40-204">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="46a40-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="46a40-205">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="46a40-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a><span data-ttu-id="46a40-206">¿Comentarios?</span><span class="sxs-lookup"><span data-stu-id="46a40-206">Feedback?</span></span>
<span data-ttu-id="46a40-207">Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="46a40-207">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>