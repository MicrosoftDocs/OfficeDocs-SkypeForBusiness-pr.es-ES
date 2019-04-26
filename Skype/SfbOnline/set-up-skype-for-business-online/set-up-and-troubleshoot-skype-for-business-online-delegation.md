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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: En este artículo se explica cómo configurar y solucionar problemas de Skype para la delegación en línea de negocio. En este artículo se ofrece instrucciones para el programa de instalación recomendaciones, procedimientos recomendados y pasos para solucionar problemas.
ms.openlocfilehash: 450aee07691a007b976aafffc05d34c3e7ef85f2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237301"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="6f34e-104">Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6f34e-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="6f34e-105">En este artículo se explica cómo configurar y solucionar problemas de Skype para la delegación en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="6f34e-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="6f34e-106">En este artículo se ofrece instrucciones para el programa de instalación recomendaciones, procedimientos recomendados y pasos para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="6f34e-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="6f34e-107">Instrucciones y requisitos</span><span class="sxs-lookup"><span data-stu-id="6f34e-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="6f34e-108">Directrices para la delegación</span><span class="sxs-lookup"><span data-stu-id="6f34e-108">Guidelines for delegation</span></span>

<span data-ttu-id="6f34e-109">Configurar y obtención de delegación para que funcione correctamente dependen de seguir estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="6f34e-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="6f34e-110">Debe usar la Skype para todo el cliente de 2015 empresarial con las últimas actualizaciones o la Skype para todo el cliente de 2016 empresarial.</span><span class="sxs-lookup"><span data-stu-id="6f34e-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="6f34e-111">Debe usar el cliente de Outlook 2013 con las actualizaciones más recientes o el cliente de Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="6f34e-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="6f34e-112">Asegúrese de que el usuario delegado y equipos de delegado tienen un perfil de correo de Outlook que es la principal o el perfil predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6f34e-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="6f34e-113">Ese perfil de correo debe contener únicamente una cuenta.</span><span class="sxs-lookup"><span data-stu-id="6f34e-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="6f34e-114">Skype para la empresa para el usuario delegado y el delegado debe ser usuarios en línea.</span><span class="sxs-lookup"><span data-stu-id="6f34e-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="6f34e-115">Además, los buzones de Exchange Server para cada cuenta debe ser estar en línea o local.</span><span class="sxs-lookup"><span data-stu-id="6f34e-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="6f34e-116">El usuario delegado y el delegado deben usar la misma versión principal de Outlook.</span><span class="sxs-lookup"><span data-stu-id="6f34e-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="6f34e-117">El valor del atributo **EnableExchangeDelegateSync** debe establecerse en **true** en la directiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="6f34e-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="6f34e-118">Puede comprobar esta configuración, ejecute el cmdlet **Get-CSClientPolicy** en la Skype para el módulo de PowerShell en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="6f34e-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="6f34e-119">El usuario delegado y el delegado deben haber iniciado sesión en Skype para profesionales y Outlook al mismo tiempo en diferentes estaciones de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6f34e-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="6f34e-120">Buzones compartidos no son compatibles para Skype para la delegación en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="6f34e-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="6f34e-121">Esto es debido a que el buzón compartido no tiene la lista de control de acceso (ACL) de **sendonbehalf** .</span><span class="sxs-lookup"><span data-stu-id="6f34e-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="6f34e-122">Skype para compatibilidad con la versión de cliente de negocio</span><span class="sxs-lookup"><span data-stu-id="6f34e-122">Skype for Business client version support</span></span>

||<span data-ttu-id="6f34e-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="6f34e-123">**Outlook 2013**</span></span>|<span data-ttu-id="6f34e-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="6f34e-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6f34e-125">**Lync/Skype para cliente básico de negocio**</span><span class="sxs-lookup"><span data-stu-id="6f34e-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="6f34e-126">No se admite</span><span class="sxs-lookup"><span data-stu-id="6f34e-126">Not supported</span></span> |<span data-ttu-id="6f34e-127">No se admite</span><span class="sxs-lookup"><span data-stu-id="6f34e-127">Not supported</span></span>
|<span data-ttu-id="6f34e-128">**Skype Empresarial 2015**</span><span class="sxs-lookup"><span data-stu-id="6f34e-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="6f34e-129">Compatible</span><span class="sxs-lookup"><span data-stu-id="6f34e-129">Supported</span></span>| <span data-ttu-id="6f34e-130">Compatible</span><span class="sxs-lookup"><span data-stu-id="6f34e-130">Supported</span></span>|
|<span data-ttu-id="6f34e-131">**Skype para profesionales de 2016**</span><span class="sxs-lookup"><span data-stu-id="6f34e-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="6f34e-132">Compatible</span><span class="sxs-lookup"><span data-stu-id="6f34e-132">Supported</span></span>| <span data-ttu-id="6f34e-133">Compatible</span><span class="sxs-lookup"><span data-stu-id="6f34e-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="6f34e-134">Los requisitos de licencia</span><span class="sxs-lookup"><span data-stu-id="6f34e-134">Licensing requirements</span></span>

<span data-ttu-id="6f34e-135">**Escenario de licencias E3 de empresa**</span><span class="sxs-lookup"><span data-stu-id="6f34e-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="6f34e-136">**Licencia**</span><span class="sxs-lookup"><span data-stu-id="6f34e-136">**License**</span></span>|<span data-ttu-id="6f34e-137">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="6f34e-137">**Clients**</span></span>|<span data-ttu-id="6f34e-138">**Notas**</span><span class="sxs-lookup"><span data-stu-id="6f34e-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6f34e-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="6f34e-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="6f34e-140">Lync 2013 (Skype para profesionales de 2015) se utiliza con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f34e-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6f34e-141">Skype para 2016 empresarial se utiliza con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f34e-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="6f34e-142">Skype para cliente empresarial básica no es compatible con la delegación.</span><span class="sxs-lookup"><span data-stu-id="6f34e-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="6f34e-143">Para los clientes de Mac, puede delegar las llamadas pero no las reuniones.</span><span class="sxs-lookup"><span data-stu-id="6f34e-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="6f34e-144">E3 de empresa con el sistema telefónico de Office 365 + xCalling Plan de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f34e-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="6f34e-145">Lync 2013 (Skype para profesionales de 2015) se utiliza con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f34e-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6f34e-146">Skype para 2016 empresarial se utiliza con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f34e-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6f34e-147">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="6f34e-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="6f34e-148">Skype para cliente empresarial básica no es compatible con la delegación.</span><span class="sxs-lookup"><span data-stu-id="6f34e-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="6f34e-149">Para los clientes de Mac, puede delegar las llamadas pero no las reuniones.</span><span class="sxs-lookup"><span data-stu-id="6f34e-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="6f34e-150">**Escenario de licencia Enterprise E5**</span><span class="sxs-lookup"><span data-stu-id="6f34e-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="6f34e-151">**Licencia**</span><span class="sxs-lookup"><span data-stu-id="6f34e-151">**License**</span></span>|<span data-ttu-id="6f34e-152">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="6f34e-152">**Clients**</span></span>|<span data-ttu-id="6f34e-153">**Notas**</span><span class="sxs-lookup"><span data-stu-id="6f34e-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6f34e-154">E5 de la empresa</span><span class="sxs-lookup"><span data-stu-id="6f34e-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="6f34e-155">Lync 2013 (Skype para profesionales de 2015) se utiliza con Outlook 2013 o 2016 de Outlook.</span><span class="sxs-lookup"><span data-stu-id="6f34e-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="6f34e-156">Skype para 2016 empresarial se utiliza con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f34e-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="6f34e-157">Skype para cliente empresarial básica no es compatible con la delegación.</span><span class="sxs-lookup"><span data-stu-id="6f34e-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="6f34e-158">Para los clientes de Mac, puede delegar las llamadas pero no las reuniones.</span><span class="sxs-lookup"><span data-stu-id="6f34e-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="6f34e-159">E5 Enterprise plus Plan de llamada de Office 365</span><span class="sxs-lookup"><span data-stu-id="6f34e-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="6f34e-160">Skype para la empresa para Mac 2016</span><span class="sxs-lookup"><span data-stu-id="6f34e-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="6f34e-161">Lync 2013 (Skype para profesionales de 2015) se utiliza con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f34e-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6f34e-162">Skype para 2016 empresarial se utiliza con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6f34e-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="6f34e-163">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="6f34e-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="6f34e-164">Skype para cliente empresarial básica no es compatible con la delegación.</span><span class="sxs-lookup"><span data-stu-id="6f34e-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="6f34e-165">Para los clientes de Mac, puede delegar las llamadas pero no las reuniones.</span><span class="sxs-lookup"><span data-stu-id="6f34e-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="6f34e-166">Configurar y comprobar la delegación</span><span class="sxs-lookup"><span data-stu-id="6f34e-166">Set up and verify delegation</span></span>

<span data-ttu-id="6f34e-167">Para configurar Skype para la delegación en línea de negocio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6f34e-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="6f34e-168">Para los clientes de Windows</span><span class="sxs-lookup"><span data-stu-id="6f34e-168">For Windows clients</span></span>

 <span data-ttu-id="6f34e-169">**Ficha de desvío de llamadas**</span><span class="sxs-lookup"><span data-stu-id="6f34e-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="6f34e-170">Seleccione **Herramientas** > **Opciones de** > **configuración de desvío de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="6f34e-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="6f34e-171">Seleccione **Editar a Mis miembros delegados**.</span><span class="sxs-lookup"><span data-stu-id="6f34e-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="6f34e-172">Seleccione **Agregar**, seleccione al delegado que desea agregar y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f34e-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="6f34e-173">**Ninguna ficha de desvío de llamadas**</span><span class="sxs-lookup"><span data-stu-id="6f34e-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="6f34e-174">En Outlook, seleccione **archivo** > **Configuración de la cuenta** > **Acceso delegado** > **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6f34e-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="6f34e-175">Busque y, a continuación, agregue el nombre de la persona que se va a ser el delegado.</span><span class="sxs-lookup"><span data-stu-id="6f34e-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="6f34e-176">Seleccione el menú **calendario** y, a continuación, seleccione **Editor (puede leer, crear y modificar elementos)**.</span><span class="sxs-lookup"><span data-stu-id="6f34e-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="6f34e-177">Para los clientes de Mac - Lync</span><span class="sxs-lookup"><span data-stu-id="6f34e-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="6f34e-178">**Ficha de desvío de llamadas**</span><span class="sxs-lookup"><span data-stu-id="6f34e-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="6f34e-179">Si el cliente no tiene una ficha de **Desvío de llamadas** que tiene el vínculo **Editar mis miembros a delegados** y el usuario delegado se encuentra en un equipo Mac, el usuario delegado debe iniciar sesión en un equipo basado en Windows con el fin de configurar la delegación.</span><span class="sxs-lookup"><span data-stu-id="6f34e-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="6f34e-180">Esto es debido a que los clientes de Mac no pueden realizar conexiones de MAPI y es un requisito para establecer Skype para la delegación de negocio desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="6f34e-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="6f34e-181">Compruebe el éxito</span><span class="sxs-lookup"><span data-stu-id="6f34e-181">Verify success</span></span>

<span data-ttu-id="6f34e-182">Si el programa de instalación se realiza correctamente, el delegado debería ver la **ha sido agregado como delegado para < Name>** mensaje y también que se crea el grupo **de personas puedo administrar las llamadas para** .</span><span class="sxs-lookup"><span data-stu-id="6f34e-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="6f34e-183">El usuario delegado debería ver que se ha creado el grupo de **delegados** .</span><span class="sxs-lookup"><span data-stu-id="6f34e-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6f34e-184">Permisos de delegación suelen aparecerán dentro de 30 minutos al proceso de instalación.</span><span class="sxs-lookup"><span data-stu-id="6f34e-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="6f34e-185">Sin embargo, este proceso puede tardar hasta 24 horas para llevar a cabo.</span><span class="sxs-lookup"><span data-stu-id="6f34e-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="6f34e-186">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="6f34e-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="6f34e-187">Problemas comunes</span><span class="sxs-lookup"><span data-stu-id="6f34e-187">Common issues</span></span>

- > <span data-ttu-id="6f34e-188">**Problema 1** La entrada de delegado sigue apareciendo en el grupo **de personas puedo administrar las llamadas para** una vez que el usuario delegado quite al delegado desde el cliente de Outlook.</span><span class="sxs-lookup"><span data-stu-id="6f34e-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="6f34e-189">**Resolución 1** En Skype para clientes empresariales, secundario del delegado en el grupo de **delegados** y, a continuación, seleccione **quitar de grupo**.</span><span class="sxs-lookup"><span data-stu-id="6f34e-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="6f34e-190">**Problema 2** Una vez concedido el acceso de delegado a través del cliente de Outlook, ni en el mensaje de confirmación ni en el grupo **de personas puedo administrar las llamadas para** aparecen para el delegado.</span><span class="sxs-lookup"><span data-stu-id="6f34e-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="6f34e-191">**Resolución 2** Quitar la delegación desde el cliente de Outlook, espere unos 15 minutos para la replicación y, a continuación, vuelva a agregar al delegado.</span><span class="sxs-lookup"><span data-stu-id="6f34e-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="6f34e-192">Otros problemas comunes</span><span class="sxs-lookup"><span data-stu-id="6f34e-192">Other common issues</span></span>

- <span data-ttu-id="6f34e-193">Delegación no funciona si se supera el umbral de 25 delegators y 25 delegados.</span><span class="sxs-lookup"><span data-stu-id="6f34e-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="6f34e-194">No se admite la Skype para cliente empresarial básico.</span><span class="sxs-lookup"><span data-stu-id="6f34e-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f34e-195">Si instala el Skype para cliente empresarial básico, quitará y delegación de interrupción.</span><span class="sxs-lookup"><span data-stu-id="6f34e-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="6f34e-196">Si el valor de **Estado de MAPI** no es **Aceptar**, asegúrese de que coinciden con los valores de **SIP** y **SMTP** .</span><span class="sxs-lookup"><span data-stu-id="6f34e-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6f34e-197">Puede tardar varios minutos para el estado MAPI mostrar como **Aceptar** después de iniciar en primer lugar Skype para profesionales y Outlook.</span><span class="sxs-lookup"><span data-stu-id="6f34e-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="6f34e-198">No se admiten la creación de un grupo de seguridad y agregar los permisos de delegación para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="6f34e-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="6f34e-199">MAPI no está disponible.</span><span class="sxs-lookup"><span data-stu-id="6f34e-199">MAPI is unavailable.</span></span> <span data-ttu-id="6f34e-200">Vea el [error de "MAPI no está disponible" de Skype para cliente de 2016 empresarial](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="6f34e-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="6f34e-201">El buzón de Exchange Online no está accesible a través de la Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="6f34e-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="6f34e-202">Si esto ocurre, ejecute la [prueba de conectividad de Outlook](https://testconnectivity.microsoft.com/) para asegurarse de que se pasa.</span><span class="sxs-lookup"><span data-stu-id="6f34e-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6f34e-203">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6f34e-203">Related topics</span></span>
[<span data-ttu-id="6f34e-204">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="6f34e-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="6f34e-205">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="6f34e-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
