---
title: Administrar la configuración de configuración del servicio Web en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
description: 'Resumen: Administrar opciones de configuración del servicio Web en Skype para Business Server.'
ms.openlocfilehash: 53d709c9964a665c97ba809ca6f40dceb0be137b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884107"
---
# <a name="manage-web-service-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b52d4-103">Administrar la configuración de configuración del servicio Web en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="b52d4-103">Manage Web Service configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="b52d4-104">**Resumen:** Administrar opciones de configuración del servicio Web en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b52d4-104">**Summary:** Manage Web Service configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="b52d4-105">Puede usar la página **Servicio Web** para configurar los métodos de autenticación para obtener acceso a Skype para Business Server relacionados con servidores web y servicios Web.</span><span class="sxs-lookup"><span data-stu-id="b52d4-105">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="b52d4-106">Siga estos pasos para crear una nueva directiva de servicios web.</span><span class="sxs-lookup"><span data-stu-id="b52d4-106">Follow these steps to create a new Web Service policy.</span></span>
  
### <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="b52d4-107">Para crear opciones de configuración nuevas para un servicio web</span><span class="sxs-lookup"><span data-stu-id="b52d4-107">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="b52d4-108">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .</span><span class="sxs-lookup"><span data-stu-id="b52d4-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b52d4-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b52d4-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b52d4-110">En la barra de navegación izquierda, haga clic en **Seguridad**y, a continuación, en **Servicio web**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="b52d4-111">En la página **Servicio web**, haga clic en **Nuevo** y, a continuación, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b52d4-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="b52d4-p101">Para configurar el servicio web para un sitio, haga clic en **Configuración del sitio**. En **Seleccionar un sitio**, haga clic en el sitio al que se aplicará la directiva de servicios web y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-p101">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
   - <span data-ttu-id="b52d4-p102">Para configurar el servicio web para un grupo de servidores, haga clic en **Configuración del grupo de servidores**. En **Seleccionar un servicio**, haga clic en el servicio al que se aplicará la directiva de servicios web y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-p102">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span> 
    
5. <span data-ttu-id="b52d4-116">En **Nueva configuración de servicio web**, en **Autenticación de Windows**, seleccione **Negociar**, **Autenticación de Windows Integrada** o **Ninguna**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="b52d4-117">Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.</span><span class="sxs-lookup"><span data-stu-id="b52d4-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="b52d4-118">**Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.</span><span class="sxs-lookup"><span data-stu-id="b52d4-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="b52d4-119">**Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="b52d4-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="b52d4-120">**Habilitar descarga de cadena de certificados** para que los servidores a los que se presente un certificado de autenticación descarguen la cadena de certificados para ese certificado.</span><span class="sxs-lookup"><span data-stu-id="b52d4-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="b52d4-121">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-121">Click **Commit**.</span></span>
    
## <a name="modify-existing-web-service-configuration-settings"></a><span data-ttu-id="b52d4-122">Modificar opciones de configuración de un servicio web existente</span><span class="sxs-lookup"><span data-stu-id="b52d4-122">Modify existing Web Service configuration settings</span></span>

<span data-ttu-id="b52d4-123">Puede usar la página **Servicio Web** para configurar los métodos de autenticación para obtener acceso a Skype para Business Server relacionados con servidores web y servicios Web.</span><span class="sxs-lookup"><span data-stu-id="b52d4-123">You can use the **Web Service** page to configure the authentication methods for accessing Skype for Business Server related web servers and Web Services.</span></span>
  
<span data-ttu-id="b52d4-124">Siga estos pasos para modificar una directiva de servicio web existente.</span><span class="sxs-lookup"><span data-stu-id="b52d4-124">Follow these steps to modify an existing Web Service policy.</span></span>
  
### <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="b52d4-125">Para modificar opciones de configuración de un servicio web existente</span><span class="sxs-lookup"><span data-stu-id="b52d4-125">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="b52d4-126">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .</span><span class="sxs-lookup"><span data-stu-id="b52d4-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b52d4-127">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b52d4-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b52d4-128">En la barra de navegación izquierda, haga clic en **Seguridad**y, a continuación, en **Servicio web**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-128">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="b52d4-129">En la página **Servicio web**, haga clic en una configuración, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-129">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b52d4-130">En **Editar configuración de servicio web**, en **Autenticación de Windows integrada**, seleccione **Negociar**, **NTLM** o **Ninguna**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-130">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>
    
6. <span data-ttu-id="b52d4-131">Seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno.</span><span class="sxs-lookup"><span data-stu-id="b52d4-131">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="b52d4-132">**Habilitar autenticación PIN** para habilitar la autenticación de clientes a través de números PIN.</span><span class="sxs-lookup"><span data-stu-id="b52d4-132">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
   - <span data-ttu-id="b52d4-133">**Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="b52d4-133">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
   - <span data-ttu-id="b52d4-134">**Habilitar descarga de cadena de certificados** para que los servidores a los que se presente un certificado de autenticación descarguen la cadena de certificados para ese certificado.</span><span class="sxs-lookup"><span data-stu-id="b52d4-134">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>
    
7. <span data-ttu-id="b52d4-135">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-135">Click **Commit**.</span></span>
    
## <a name="delete-existing-web-service-configuration-settings"></a><span data-ttu-id="b52d4-136">Modificar opciones de configuración de un servicio web existente</span><span class="sxs-lookup"><span data-stu-id="b52d4-136">Delete existing Web Service configuration settings</span></span>

<span data-ttu-id="b52d4-137">Siga estos pasos para eliminar opciones de configuración de un servicio web.</span><span class="sxs-lookup"><span data-stu-id="b52d4-137">Follow these steps to delete web service configuration settings.</span></span>
  
### <a name="to-delete-web-service-configuration-settings"></a><span data-ttu-id="b52d4-138">Para eliminar opciones de configuración de un servicio web existente</span><span class="sxs-lookup"><span data-stu-id="b52d4-138">To delete web service configuration settings</span></span>

1.  <span data-ttu-id="b52d4-139">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que se encuentra en la red en el que implementa Skype para Business Server .</span><span class="sxs-lookup"><span data-stu-id="b52d4-139">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="b52d4-140">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b52d4-140">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b52d4-141">En la barra de navegación izquierda, haga clic en **Seguridad**y, a continuación, en **Servicio web**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-141">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>
    
4. <span data-ttu-id="b52d4-142">En la página **Servicio web**, vaya al campo de búsqueda y escriba total o parcialmente el nombre de la directiva que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="b52d4-142">On the **Web Service** page, and in the search field, type all or part of the name of the policy you want to delete.</span></span>
    
5. <span data-ttu-id="b52d4-143">En la lista de directivas, haga clic en la directiva que desea, en **Editar** y, a continuación, en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-143">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="b52d4-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b52d4-144">Click **OK**.</span></span>
    
## <a name="deleting-web-service-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b52d4-145">Eliminación de opciones de configuración del servicio Web mediante el uso de Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b52d4-145">Deleting Web Service Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b52d4-146">Puede eliminar la configuración del servicio web mediante el uso de Windows PowerShell y el cmdlet **Remove-CsWebServiceConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b52d4-146">You can delete web service configuration settings by using Windows PowerShell and the **Remove-CsWebServiceConfiguration** cmdlet.</span></span> <span data-ttu-id="b52d4-147">Puede ejecutar este cmdlet desde el Skype para Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b52d4-147">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b52d4-148">Para obtener información detallada acerca del uso de Windows PowerShell remoto para conectarse a Skype para Business Server, vea el artículo del blog ["rápido iniciar: administración de Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="b52d4-148">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b52d4-149">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b52d4-149">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-delete-a-specific-collection-of-web-service-configuration-settings"></a><span data-ttu-id="b52d4-150">Para eliminar una colección específica de valores de configuración de los servicios web:</span><span class="sxs-lookup"><span data-stu-id="b52d4-150">To delete a specific collection of web service configuration settings</span></span>

- <span data-ttu-id="b52d4-151">El comando siguiente quita los valores de seguridad de los servicios web que se aplican al sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="b52d4-151">The following command removes the Web Service security settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsWebServiceConfiguration -Identity "site:Redmond"
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="b52d4-152">Para eliminar todas las opciones de configuración de los servicios web que se aplican al ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="b52d4-152">To delete all of the web service configuration settings applied to the site scope</span></span>

<span data-ttu-id="b52d4-153">El comando siguiente quita todos los valores de seguridad de los servicios web que se aplican al ámbito del sitio:</span><span class="sxs-lookup"><span data-stu-id="b52d4-153">The following command removes all of the Web Service security settings applied to the service scope:</span></span>
    
  ```
  Get-CsWebServiceConfiguration -Filter "service:*" | Remove-CsWebServiceConfiguration
  ```

### <a name="to-delete-all-of-the-web-service-configuration-settings-that-allow-certificate-authentication"></a><span data-ttu-id="b52d4-154">Para eliminar todas las opciones de configuración de los servicios web que permiten la autenticación de certificados</span><span class="sxs-lookup"><span data-stu-id="b52d4-154">To delete all of the web service configuration settings that allow certificate authentication</span></span>

<span data-ttu-id="b52d4-155">El comando siguiente quita todos los valores de seguridad de los servicios web que permiten el uso de la autenticación de certificados:</span><span class="sxs-lookup"><span data-stu-id="b52d4-155">The following command removes all the Web Service security settings that allow the use of certificate authentication:</span></span>
    
  ```
  Get-CsWebServiceConfiguration | Where-Object {$_.UseCertificateAuth -eq $True} | Remove-CsWebServiceConfiguration
  ```

<span data-ttu-id="b52d4-156">Para obtener más información, consulte [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b52d4-156">For details, see [Remove-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cswebserviceconfiguration?view=skype-ps).</span></span>
  

