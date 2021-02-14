---
title: Administrar las opciones de configuración del servicio web en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumen: administre las opciones de configuración del servicio web en Skype Empresarial Server.'
ms.openlocfilehash: 68abe01614902d5e6f4c58040b30b6afbd475df8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806500"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e6baa-103">Administrar las opciones de configuración del servicio web en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e6baa-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="e6baa-104">**Resumen:** Administrar las opciones de configuración del servicio web en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="e6baa-105">Puede usar la página **Servicio web** para configurar los métodos de autenticación para obtener acceso a los servidores web y servicios web relacionados con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="e6baa-106">Siga estos pasos para crear una nueva directiva de servicio web.</span><span class="sxs-lookup"><span data-stu-id="e6baa-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="e6baa-107">Para crear nuevas opciones de configuración del servicio web</span><span class="sxs-lookup"><span data-stu-id="e6baa-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="e6baa-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e6baa-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e6baa-110">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.</span><span class="sxs-lookup"><span data-stu-id="e6baa-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="e6baa-111">En la **página Servicio** web, haga clic en **Nuevo** y, a continuación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="e6baa-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="e6baa-112">Para configurar el servicio web para un sitio, haga clic en **Configuración del sitio.**</span><span class="sxs-lookup"><span data-stu-id="e6baa-112">To configure the Web Service for a site, click **Site configuration**.</span></span> <span data-ttu-id="e6baa-113">En **Seleccionar un sitio,** haga clic en el sitio al que se aplicará la directiva de servicio web y haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="e6baa-113">In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="e6baa-114">Para configurar el servicio web para un grupo de servidores, haga clic en **Configuración del grupo de servidores.**</span><span class="sxs-lookup"><span data-stu-id="e6baa-114">To configure the Web Service for a pool, click **Pool configuration**.</span></span> <span data-ttu-id="e6baa-115">En **Seleccionar un servicio,** haga clic en el servicio al que se aplicará la directiva de servicio web y haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="e6baa-115">In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="e6baa-116">En **Nueva configuración del servicio web**, en **Autenticación integrada de Windows**, seleccione **Negociar**, **Autenticación integrada de Windows** o **Ninguno.**</span><span class="sxs-lookup"><span data-stu-id="e6baa-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="e6baa-117">Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.</span><span class="sxs-lookup"><span data-stu-id="e6baa-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="e6baa-118">**Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.</span><span class="sxs-lookup"><span data-stu-id="e6baa-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="e6baa-119">**Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="e6baa-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="e6baa-120">**Habilitar descarga de cadena de certificados** para que los servidores se presenten con un certificado de autenticación, descargue la cadena de certificados para ese certificado.</span><span class="sxs-lookup"><span data-stu-id="e6baa-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="e6baa-121">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e6baa-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="e6baa-122">Modificar las opciones de configuración existentes del servicio web</span><span class="sxs-lookup"><span data-stu-id="e6baa-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="e6baa-123">Puede usar la página **Servicio web** para configurar los métodos de autenticación para obtener acceso a los servidores web y servicios web relacionados con Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="e6baa-124">Siga estos pasos para modificar una directiva de servicio web existente.</span><span class="sxs-lookup"><span data-stu-id="e6baa-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="e6baa-125">Para modificar las opciones de configuración de servicios web existentes</span><span class="sxs-lookup"><span data-stu-id="e6baa-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="e6baa-126">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e6baa-127">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e6baa-128">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.</span><span class="sxs-lookup"><span data-stu-id="e6baa-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="e6baa-129">En la página **Servicio web**, haga clic en una configuración, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="e6baa-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e6baa-130">En **Editar configuración de servicio web**, en **Autenticación de Windows**, seleccione **Negociar**, **NTLM** o **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="e6baa-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="e6baa-131">Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.</span><span class="sxs-lookup"><span data-stu-id="e6baa-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="e6baa-132">**Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.</span><span class="sxs-lookup"><span data-stu-id="e6baa-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="e6baa-133">**Habilitar autenticación de certificados**: para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="e6baa-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="e6baa-134">**Habilitar descarga de cadena de certificados** para que los servidores se presenten con un certificado de autenticación, descargue la cadena de certificados para ese certificado.</span><span class="sxs-lookup"><span data-stu-id="e6baa-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="e6baa-135">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e6baa-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="e6baa-136">Eliminar opciones de configuración de servicio web existentes</span><span class="sxs-lookup"><span data-stu-id="e6baa-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="e6baa-137">Siga estos pasos para eliminar las opciones de configuración del servicio web.</span><span class="sxs-lookup"><span data-stu-id="e6baa-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="e6baa-138">Para eliminar las opciones de configuración del servicio web</span><span class="sxs-lookup"><span data-stu-id="e6baa-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="e6baa-139">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes) o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en la que implementó Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="e6baa-140">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="e6baa-141">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Servicio web**.</span><span class="sxs-lookup"><span data-stu-id="e6baa-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="e6baa-142">En la **página Servicio** web y en el campo de búsqueda, escriba todo o parte del nombre de la directiva que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="e6baa-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="e6baa-143">En la lista de directivas, seleccione la directiva que desee, haga clic en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e6baa-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="e6baa-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e6baa-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e6baa-145">Eliminación de opciones de configuración del servicio web mediante cmdlets Windows PowerShell web</span><span class="sxs-lookup"><span data-stu-id="e6baa-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e6baa-146">Puede eliminar las opciones de configuración del servicio web mediante Windows PowerShell y el cmdlet **Remove-CsWebServiceConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="e6baa-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="e6baa-147">Puede ejecutar este cmdlet desde el shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e6baa-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e6baa-148">Para obtener más información sobre el uso de Windows PowerShell remoto para conectarse a Skype Empresarial Server, consulte el artículo del blog "Inicio rápido: administración de [Microsoft Lync Server 2010 con PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876)</span><span class="sxs-lookup"><span data-stu-id="e6baa-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="e6baa-149">El proceso es el mismo en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e6baa-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="e6baa-150">Para eliminar una colección específica de opciones de configuración de servicios web</span><span class="sxs-lookup"><span data-stu-id="e6baa-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="e6baa-151">El siguiente comando quita la configuración de seguridad del servicio web aplicada al sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="e6baa-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="e6baa-152">Para eliminar todas las opciones de configuración del servicio web aplicadas al ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="e6baa-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="e6baa-153">El siguiente comando quita toda la configuración de seguridad del servicio web aplicada al ámbito de servicio:</span><span class="sxs-lookup"><span data-stu-id="e6baa-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="e6baa-154">Para eliminar todas las opciones de configuración del servicio web que permiten la autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="e6baa-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="e6baa-155">El siguiente comando quita toda la configuración de seguridad del servicio web que permite el uso de la autenticación de certificados:</span><span class="sxs-lookup"><span data-stu-id="e6baa-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```PowerShell
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="e6baa-156">Para obtener más información, [vea Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e6baa-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

