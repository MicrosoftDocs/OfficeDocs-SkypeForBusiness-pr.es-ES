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
f1keywords: None
ms.custom:
- Setup
description: En este artículo se explica cómo configurar y solucionar problemas de delegación de Skype empresarial online. Este artículo le ofrece instrucciones para las recomendaciones de configuración, procedimientos recomendados y pasos de solución de problemas.
ms.openlocfilehash: 0528bbb3dc25e085d38f86c040eb5129c9d039c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285248"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a><span data-ttu-id="5e5de-104">Configurar y solucionar problemas relacionados con la delegación de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5e5de-104">Set up and troubleshoot Skype for Business Online delegation</span></span>

<span data-ttu-id="5e5de-105">En este artículo se explica cómo configurar y solucionar problemas de delegación de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="5e5de-105">This article explains how to set up and troubleshoot Skype for Business Online delegation.</span></span> <span data-ttu-id="5e5de-106">Este artículo le ofrece instrucciones para las recomendaciones de configuración, procedimientos recomendados y pasos de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="5e5de-106">This article gives you guidance for setup recommendations, best practices, and troubleshooting steps.</span></span>
  
## <a name="guidelines-and-requirements"></a><span data-ttu-id="5e5de-107">Pautas y requisitos</span><span class="sxs-lookup"><span data-stu-id="5e5de-107">Guidelines and requirements</span></span>

### <a name="guidelines-for-delegation"></a><span data-ttu-id="5e5de-108">Directrices para la delegación</span><span class="sxs-lookup"><span data-stu-id="5e5de-108">Guidelines for delegation</span></span>

<span data-ttu-id="5e5de-109">La configuración y la obtención de la delegación para funcionar correctamente depende de estas pautas:</span><span class="sxs-lookup"><span data-stu-id="5e5de-109">Setting up and getting delegation to work correctly depends on you following these guidelines:</span></span>
  
- <span data-ttu-id="5e5de-110">Debe usar el cliente completo de Skype empresarial 2015 con las actualizaciones más recientes o el cliente completo de Skype empresarial 2016.</span><span class="sxs-lookup"><span data-stu-id="5e5de-110">You must be using the Skype for Business 2015 full client with the latest updates or the Skype for Business 2016 full client.</span></span>
    
- <span data-ttu-id="5e5de-111">Debe usar el cliente de Outlook 2013 con las actualizaciones más recientes o el cliente de Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="5e5de-111">You must be using the Outlook 2013 client with the latest updates or the Outlook 2016 client.</span></span>
    
- <span data-ttu-id="5e5de-112">Asegúrese de que los delegados y los equipos delegados tienen un perfil de correo de Outlook que es el principal o el predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5e5de-112">Make sure that the delegator and delegate computers have one Outlook mail profile that is the primary or the default profile.</span></span> <span data-ttu-id="5e5de-113">Ese perfil de correo debería contener solo una cuenta.</span><span class="sxs-lookup"><span data-stu-id="5e5de-113">That mail profile should contain only one account.</span></span>
    
- <span data-ttu-id="5e5de-114">Skype empresarial para el delegador y el delegado deben ser usuarios en línea.</span><span class="sxs-lookup"><span data-stu-id="5e5de-114">Skype for Business for the delegator and the delegate should be Online users.</span></span> <span data-ttu-id="5e5de-115">Además, los buzones de Exchange Server para cada cuenta deben estar conectados o ser locales.</span><span class="sxs-lookup"><span data-stu-id="5e5de-115">Also, the Exchange Server mailboxes for each account must either both be Online or both be on-premises.</span></span>
    
- <span data-ttu-id="5e5de-116">Tanto el delegado como el delegado deben usar la misma versión principal de Outlook.</span><span class="sxs-lookup"><span data-stu-id="5e5de-116">Both the delegator and delegate should be using the same major version of Outlook.</span></span>
    
- <span data-ttu-id="5e5de-117">El valor del atributo **EnableExchangeDelegateSync** debe establecerse en **true** en la Directiva de cliente.</span><span class="sxs-lookup"><span data-stu-id="5e5de-117">The **EnableExchangeDelegateSync** attribute value should be set to **true** in the client policy.</span></span> <span data-ttu-id="5e5de-118">Puede comprobar esta configuración ejecutando el cmdlet **Get-ClientPolicy** en el módulo de PowerShell de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="5e5de-118">You can verify this setting by running the **Get-CSClientPolicy** cmdlet in the Skype for Business Online PowerShell module.</span></span>
    
- <span data-ttu-id="5e5de-119">Tanto el delegado como el delegado deben haber iniciado sesión en Skype empresarial y Outlook al mismo tiempo en diferentes estaciones de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5e5de-119">Both the delegator and delegate must be signed in to Skype for Business and Outlook at the same time on different workstations.</span></span>
    
- <span data-ttu-id="5e5de-120">Los buzones compartidos no son compatibles con la delegación de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="5e5de-120">Shared mailboxes aren't supported for Skype for Business Online delegation.</span></span> <span data-ttu-id="5e5de-121">Esto se debe a que el buzón de correo compartido no tiene la lista de control de acceso (ACL) **sendonbehalf** .</span><span class="sxs-lookup"><span data-stu-id="5e5de-121">This is because the shared mailbox doesn't have the **sendonbehalf** access control list (ACL).</span></span>
    
### <a name="skype-for-business-client-version-support"></a><span data-ttu-id="5e5de-122">Compatibilidad con versiones de cliente de Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="5e5de-122">Skype for Business client version support</span></span>

||<span data-ttu-id="5e5de-123">**Outlook 2013**</span><span class="sxs-lookup"><span data-stu-id="5e5de-123">**Outlook 2013**</span></span>|<span data-ttu-id="5e5de-124">**Outlook 2016**</span><span class="sxs-lookup"><span data-stu-id="5e5de-124">**Outlook 2016**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e5de-125">**Lync/Skype empresarial para clientes básicos**</span><span class="sxs-lookup"><span data-stu-id="5e5de-125">**Lync/Skype for Business Basic Client**</span></span>| <span data-ttu-id="5e5de-126">No compatible</span><span class="sxs-lookup"><span data-stu-id="5e5de-126">Not supported</span></span> |<span data-ttu-id="5e5de-127">No compatible</span><span class="sxs-lookup"><span data-stu-id="5e5de-127">Not supported</span></span>
|<span data-ttu-id="5e5de-128">**Skype Empresarial 2015**</span><span class="sxs-lookup"><span data-stu-id="5e5de-128">**Skype for Business 2015**</span></span>|<span data-ttu-id="5e5de-129">Compatible</span><span class="sxs-lookup"><span data-stu-id="5e5de-129">Supported</span></span>| <span data-ttu-id="5e5de-130">Compatible</span><span class="sxs-lookup"><span data-stu-id="5e5de-130">Supported</span></span>|
|<span data-ttu-id="5e5de-131">**Skype empresarial 2016**</span><span class="sxs-lookup"><span data-stu-id="5e5de-131">**Skype for Business 2016**</span></span>|<span data-ttu-id="5e5de-132">Compatible</span><span class="sxs-lookup"><span data-stu-id="5e5de-132">Supported</span></span>| <span data-ttu-id="5e5de-133">Compatible</span><span class="sxs-lookup"><span data-stu-id="5e5de-133">Supported</span></span>|

   
### <a name="licensing-requirements"></a><span data-ttu-id="5e5de-134">Requisitos de licencias</span><span class="sxs-lookup"><span data-stu-id="5e5de-134">Licensing requirements</span></span>

<span data-ttu-id="5e5de-135">**Escenario de licencias de Enterprise E3**</span><span class="sxs-lookup"><span data-stu-id="5e5de-135">**Enterprise E3 licensing scenario**</span></span>

|<span data-ttu-id="5e5de-136">**Licencia**</span><span class="sxs-lookup"><span data-stu-id="5e5de-136">**License**</span></span>|<span data-ttu-id="5e5de-137">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="5e5de-137">**Clients**</span></span>|<span data-ttu-id="5e5de-138">**Notas**</span><span class="sxs-lookup"><span data-stu-id="5e5de-138">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e5de-139">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="5e5de-139">Enterprise E3</span></span>  <br/> |<span data-ttu-id="5e5de-140">Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 u Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e5de-140">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="5e5de-141">Skype empresarial 2016 se ha usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e5de-141">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="5e5de-142">El cliente básico de Skype empresarial no es compatible con la delegación.</span><span class="sxs-lookup"><span data-stu-id="5e5de-142">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="5e5de-143">Para los clientes de Mac, puede delegar llamadas, pero no reuniones.</span><span class="sxs-lookup"><span data-stu-id="5e5de-143">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="5e5de-144">Enterprise E3 con Office 365 Phone System + Office 365 plan xCalling</span><span class="sxs-lookup"><span data-stu-id="5e5de-144">Enterprise E3 with Office 365 Phone System + Office 365 xCalling Plan</span></span>  <br/> |<span data-ttu-id="5e5de-145">Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 u Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e5de-145">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="5e5de-146">Skype empresarial 2016 se ha usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e5de-146">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="5e5de-147">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="5e5de-147">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="5e5de-148">El cliente básico de Skype empresarial no es compatible con la delegación.</span><span class="sxs-lookup"><span data-stu-id="5e5de-148">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="5e5de-149">Para los clientes de Mac, puede delegar llamadas, pero no reuniones.</span><span class="sxs-lookup"><span data-stu-id="5e5de-149">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
<span data-ttu-id="5e5de-150">**Escenario de licencias de Enterprise E5**</span><span class="sxs-lookup"><span data-stu-id="5e5de-150">**Enterprise E5 licensing scenario**</span></span>

|<span data-ttu-id="5e5de-151">**Licencia**</span><span class="sxs-lookup"><span data-stu-id="5e5de-151">**License**</span></span>|<span data-ttu-id="5e5de-152">**Clientes**</span><span class="sxs-lookup"><span data-stu-id="5e5de-152">**Clients**</span></span>|<span data-ttu-id="5e5de-153">**Notas**</span><span class="sxs-lookup"><span data-stu-id="5e5de-153">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5e5de-154">Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="5e5de-154">Enterprise E5</span></span>  <br/> |<span data-ttu-id="5e5de-155">Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 u Outlook 2016.</span><span class="sxs-lookup"><span data-stu-id="5e5de-155">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016.</span></span>  <br/> <span data-ttu-id="5e5de-156">Skype empresarial 2016 se ha usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e5de-156">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> |<span data-ttu-id="5e5de-157">El cliente básico de Skype empresarial no es compatible con la delegación.</span><span class="sxs-lookup"><span data-stu-id="5e5de-157">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="5e5de-158">Para los clientes de Mac, puede delegar llamadas, pero no reuniones.</span><span class="sxs-lookup"><span data-stu-id="5e5de-158">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
|<span data-ttu-id="5e5de-159">Enterprise E5 más plan de llamadas de Office 365</span><span class="sxs-lookup"><span data-stu-id="5e5de-159">Enterprise E5 plus Office 365 Calling Plan</span></span>  <br/> |<span data-ttu-id="5e5de-160">Skype empresarial para Mac 2016</span><span class="sxs-lookup"><span data-stu-id="5e5de-160">Skype for Business for Mac 2016</span></span>  <br/> <span data-ttu-id="5e5de-161">Lync 2013 (Skype empresarial 2015) se usa con Outlook 2013 u Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e5de-161">Lync 2013 (Skype for Business 2015) used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="5e5de-162">Skype empresarial 2016 se ha usado con Outlook 2013 o Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5e5de-162">Skype for Business 2016 used with Outlook 2013 or Outlook 2016</span></span>  <br/> <span data-ttu-id="5e5de-163">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="5e5de-163">Lync for Mac 2011</span></span>  <br/> |<span data-ttu-id="5e5de-164">El cliente básico de Skype empresarial no es compatible con la delegación.</span><span class="sxs-lookup"><span data-stu-id="5e5de-164">Skype for Business Basic client doesn't support delegation.</span></span>  <br/> <span data-ttu-id="5e5de-165">Para los clientes de Mac, puede delegar llamadas, pero no reuniones.</span><span class="sxs-lookup"><span data-stu-id="5e5de-165">For Mac clients, you can delegate calls but not meetings.</span></span>  <br/> |
   
## <a name="set-up-and-verify-delegation"></a><span data-ttu-id="5e5de-166">Configurar y comprobar la delegación</span><span class="sxs-lookup"><span data-stu-id="5e5de-166">Set up and verify delegation</span></span>

<span data-ttu-id="5e5de-167">Para configurar la delegación de Skype empresarial online, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5e5de-167">To set up Skype for Business Online delegation, follow these steps:</span></span>
  
### <a name="for-windows-clients"></a><span data-ttu-id="5e5de-168">Para clientes de Windows</span><span class="sxs-lookup"><span data-stu-id="5e5de-168">For Windows clients</span></span>

 <span data-ttu-id="5e5de-169">**Ficha desvío de llamadas**</span><span class="sxs-lookup"><span data-stu-id="5e5de-169">**Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="5e5de-170">Seleccione **herramientas** > **Opciones Opciones** > de**desvío de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="5e5de-170">Select **Tools** > **Options** > **Call Forwarding Settings**.</span></span>
    
2. <span data-ttu-id="5e5de-171">Seleccione **Editar mis miembros**delegados.</span><span class="sxs-lookup"><span data-stu-id="5e5de-171">Select **Edit my delegate members**.</span></span>
    
3. <span data-ttu-id="5e5de-172">Seleccione **Agregar**, seleccione el delegado que desea agregar y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e5de-172">Select **Add**, select the delegate that you want to add, and then select **OK**.</span></span>
    
 <span data-ttu-id="5e5de-173">**Pestaña sin desvío de llamadas**</span><span class="sxs-lookup"><span data-stu-id="5e5de-173">**No Call Forwarding tab**</span></span>
  
1. <span data-ttu-id="5e5de-174">En Outlook, seleccione \*\*\*\* > **configuración** > de la cuenta de archivo**delegar acceso** > **Add**.</span><span class="sxs-lookup"><span data-stu-id="5e5de-174">In Outlook, select **File** > **Account Settings** > **Delegate Access** > **Add**.</span></span>
    
2. <span data-ttu-id="5e5de-175">Busque y agregue el nombre de la persona que será el delegado.</span><span class="sxs-lookup"><span data-stu-id="5e5de-175">Locate and then add the name of the person who is going to be the delegate.</span></span>
    
3. <span data-ttu-id="5e5de-176">Seleccione el menú **calendario** y, a continuación, seleccione **Editor (puede leer, crear y modificar elementos)**.</span><span class="sxs-lookup"><span data-stu-id="5e5de-176">Select the **Calendar** menu, and then select **Editor (can read, create, and modify items)**.</span></span>
    
### <a name="for-mac-clients---lync"></a><span data-ttu-id="5e5de-177">Para clientes Mac: Lync</span><span class="sxs-lookup"><span data-stu-id="5e5de-177">For Mac clients - Lync</span></span>

 <span data-ttu-id="5e5de-178">**Ficha desvío de llamadas**</span><span class="sxs-lookup"><span data-stu-id="5e5de-178">**Call Forwarding tab**</span></span>
  
- <span data-ttu-id="5e5de-179">Si el cliente no tiene una ficha de **desvío de llamadas** que tiene el vínculo **Editar mis miembros del delegado** y el delegador se encuentra en un equipo Mac, el delegadodor debe iniciar sesión en un equipo basado en Windows para poder configurar la delegación.</span><span class="sxs-lookup"><span data-stu-id="5e5de-179">If the client doesn't have a **Call Forwarding** tab that has the **Edit my Delegate Members** link, and the delegator is located on a Mac computer, the delegator must sign in to a Windows-based computer in order to set up the delegation.</span></span> <span data-ttu-id="5e5de-180">Esto se debe a que los clientes de Mac no pueden hacer conexiones MAPI, y esto es un requisito para establecer la delegación de Skype empresarial desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="5e5de-180">This is because Mac clients can't make MAPI connections, and this is a requirement to establish Skype for Business delegation from Outlook.</span></span>
    
### <a name="verify-success"></a><span data-ttu-id="5e5de-181">Comprobar el éxito</span><span class="sxs-lookup"><span data-stu-id="5e5de-181">Verify success</span></span>

<span data-ttu-id="5e5de-182">Si la configuración se realiza correctamente, el delegado debería ver lo **que se agregó como delegado de _LT_ Name>** mensaje y también se crean las personas a las que administro las **llamadas para** el grupo.</span><span class="sxs-lookup"><span data-stu-id="5e5de-182">If the setup is successful, the delegate should see the **You were added as a delegate for < Name>** message and also that the **People I Manage Calls For** group is created.</span></span> <span data-ttu-id="5e5de-183">El delegador debe ver que \*\*\*\* se crea el grupo delegados.</span><span class="sxs-lookup"><span data-stu-id="5e5de-183">The delegator should see that the **Delegates** group is created.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5e5de-184">Los permisos de delegación suelen aparecer dentro de los 30 minutos del proceso de configuración.</span><span class="sxs-lookup"><span data-stu-id="5e5de-184">Delegation permissions usually appear within 30 minutes of the setup process.</span></span> <span data-ttu-id="5e5de-185">Sin embargo, este proceso puede demorar hasta 24 horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="5e5de-185">However, this process can take up to 24 hours to complete.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="5e5de-186">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="5e5de-186">Troubleshooting</span></span>

### <a name="common-issues"></a><span data-ttu-id="5e5de-187">Problemas comunes</span><span class="sxs-lookup"><span data-stu-id="5e5de-187">Common issues</span></span>

- > <span data-ttu-id="5e5de-188">**Problema 1** La entrada de delegado continúa apareciendo en las **llamadas de grupo personas que administro** después de que el delegador haya eliminado el delegado del cliente de Outlook.</span><span class="sxs-lookup"><span data-stu-id="5e5de-188">**Issue 1** The delegate entry continues to appear in the **People I Manage Calls For** group after the delegator has removed the delegate from the Outlook client.</span></span>
    
  - > <span data-ttu-id="5e5de-189">**Solución 1** En el cliente de Skype empresarial, haga clic con el botón derecho en \*\*\*\* el delegado en el grupo delegados y, a continuación, seleccione **quitar del grupo**.</span><span class="sxs-lookup"><span data-stu-id="5e5de-189">**Resolution 1** On the Skype for Business client, right-click the delegate in the **Delegates** group, and then select **Remove from Group**.</span></span>
    
- > <span data-ttu-id="5e5de-190">**Problema 2** Después de conceder acceso delegado a través del cliente de Outlook, no se muestra para el delegado ni el mensaje de confirmación ni las **personas que administro las llamadas para** el grupo.</span><span class="sxs-lookup"><span data-stu-id="5e5de-190">**Issue 2** After delegate access is granted through the Outlook client, neither the confirmation message nor the **People I Manage Calls For** group appear for the delegate.</span></span>
    
  - > <span data-ttu-id="5e5de-191">**Solución 2** Quite la delegación del cliente de Outlook, espere aproximadamente 15 minutos para la replicación y, a continuación, vuelva a agregar el delegado.</span><span class="sxs-lookup"><span data-stu-id="5e5de-191">**Resolution 2** Remove the delegation from the Outlook client, wait about 15 minutes for replication, and then add the delegate again.</span></span>
    
### <a name="other-common-issues"></a><span data-ttu-id="5e5de-192">Otros problemas comunes</span><span class="sxs-lookup"><span data-stu-id="5e5de-192">Other common issues</span></span>

- <span data-ttu-id="5e5de-193">La delegación no funciona si se supera el umbral de 25 delegados y 25 delegados.</span><span class="sxs-lookup"><span data-stu-id="5e5de-193">Delegation doesn't work if the threshold of 25 delegators and 25 delegates is exceeded.</span></span>
    
- <span data-ttu-id="5e5de-194">No se admite el cliente de Skype empresarial Basic.</span><span class="sxs-lookup"><span data-stu-id="5e5de-194">The Skype for Business Basic client isn't supported.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e5de-195">Si instala el cliente de Skype empresarial Basic, se eliminará y interrumpirá la delegación.</span><span class="sxs-lookup"><span data-stu-id="5e5de-195">If you install the Skype for Business Basic client, it will remove and break delegation.</span></span> 
  
- <span data-ttu-id="5e5de-196">Si el valor de **Estado de MAPI** no es **correcto**, asegúrese de que los valores **SIP** y **SMTP** coinciden.</span><span class="sxs-lookup"><span data-stu-id="5e5de-196">If the **MAPI Status** value isn't **OK**, make sure that the **SIP** and **SMTP** values match.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5e5de-197">El estado de MAPI puede tardar varios minutos en mostrarse como **correcto** después de iniciar Skype empresarial y Outlook.</span><span class="sxs-lookup"><span data-stu-id="5e5de-197">It can take several minutes for the MAPI status to display as **OK** after you first start Skype for Business and Outlook.</span></span>
  
- <span data-ttu-id="5e5de-198">No se admite la creación de un grupo de seguridad ni la adición de permisos de delegación para ese grupo de seguridad.</span><span class="sxs-lookup"><span data-stu-id="5e5de-198">Creating a security group and adding delegation permissions for that security group isn't supported.</span></span>
    
- <span data-ttu-id="5e5de-199">MAPI no está disponible.</span><span class="sxs-lookup"><span data-stu-id="5e5de-199">MAPI is unavailable.</span></span> <span data-ttu-id="5e5de-200">Consulte el [error "MAPI unavailable" en el cliente de Skype empresarial 2016](https://support.microsoft.com/en-us/help/3147130).</span><span class="sxs-lookup"><span data-stu-id="5e5de-200">See ["MAPI unavailable" error in Skype for Business 2016 client](https://support.microsoft.com/en-us/help/3147130).</span></span>
    
- <span data-ttu-id="5e5de-201">No se puede obtener acceso al buzón de Exchange Online a través del cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="5e5de-201">The Exchange Online mailbox isn't accessible through the Skype for Business client.</span></span> <span data-ttu-id="5e5de-202">Si esto sucede, ejecute la [prueba de conectividad de Outlook](https://testconnectivity.microsoft.com/) para asegurarse de que pasa.</span><span class="sxs-lookup"><span data-stu-id="5e5de-202">If this occurs, run the [Outlook connectivity test](https://testconnectivity.microsoft.com/) to make sure that it passes.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="5e5de-203">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="5e5de-203">Related topics</span></span>
[<span data-ttu-id="5e5de-204">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5e5de-204">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="5e5de-205">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="5e5de-205">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
