---
title: Administrar opciones de configuración de registrador en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
description: 'Resumen: Administrar configuración registrador de Skype para Business Server 2015.'
ms.openlocfilehash: 5cdcf1cba045f5105b1f375fbcebb22b7b00a25d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-registrar-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="b5ace-103">Administrar opciones de configuración de registrador en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="b5ace-103">Manage Registrar configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b5ace-104">**Resumen:** Administrar configuración registrador de Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b5ace-104">**Summary:** Manage Registrar configuration settings for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b5ace-p101">Puede usar el registrador para configurar los métodos de autenticación de servidores proxy. El protocolo de autenticación que especifique definirá el tipo de desafío que presentarán los servidores del grupo a los clientes. Los protocolos disponibles son:</span><span class="sxs-lookup"><span data-stu-id="b5ace-p101">You can use the Registrar to configure proxy server authentication methods. The authentication protocol you specify determines which type of challenges the servers in the pool issue to clients. The available protocols are:</span></span>
  
- <span data-ttu-id="b5ace-108">**Kerberos** Este es el esquema de autenticación basado en contraseñas más seguro disponible para los clientes, pero está normalmente disponible sólo para clientes de empresas ya que requiere conexión de cliente a un centro de distribución de claves (controlador de dominio de Kerberos).</span><span class="sxs-lookup"><span data-stu-id="b5ace-108">**Kerberos** This is the strongest password-based authentication scheme available to clients, but it is normally available only to enterprise clients because it requires client connection to a Key Distribution Center (Kerberos domain controller).</span></span> <span data-ttu-id="b5ace-109">Esta configuración es apropiada si el servidor autentica a sólo clientes de empresas.</span><span class="sxs-lookup"><span data-stu-id="b5ace-109">This setting is appropriate if the server authenticates only enterprise clients.</span></span>
    
- <span data-ttu-id="b5ace-110">**NTLM** Se trata de la autenticación basada en contraseñas disponible para clientes que utilizan un esquema de hash de desafío y respuesta de la contraseña.</span><span class="sxs-lookup"><span data-stu-id="b5ace-110">**NTLM** This is the password-based authentication available to clients that use a challenge-response hashing scheme on the password.</span></span> <span data-ttu-id="b5ace-111">Esta es la única forma de autenticación disponible para clientes sin conectividad con un centro de distribución de claves (controlador de dominio de Kerberos), como los usuarios remotos.</span><span class="sxs-lookup"><span data-stu-id="b5ace-111">This is the only form of authentication available to clients without connectivity to a Key Distribution Center (Kerberos domain controller), such as remote users.</span></span> <span data-ttu-id="b5ace-112">Si un servidor autentica sólo los usuarios remotos, debe elegir NTLM.</span><span class="sxs-lookup"><span data-stu-id="b5ace-112">If a server authenticates only remote users, you should choose NTLM.</span></span>
    
- <span data-ttu-id="b5ace-113">**Autenticación de certificados** Este es el nuevo método de autenticación cuando el servidor necesita obtener certificados de clientes de Lync Phone Edition, teléfonos de área común, Skype para el negocio y la aplicación Lync Windows Store.</span><span class="sxs-lookup"><span data-stu-id="b5ace-113">**Certificate authentication** This is the new authentication method when the server needs to obtain certificates from Lync Phone Edition clients, common area phones, Skype for Business and the Lync Windows Store app.</span></span> <span data-ttu-id="b5ace-114">En los clientes de Lync Phone Edition, después de que un usuario inicia sesión en y se autentica correctamente proporcionando un número de identificación personal (PIN), Skype para Business Server 2015 después aprovisiona el URI de SIP para el teléfono y disposiciones un Skype para Business Server firmado certificado o un certificado de usuario que identifica Joe (Ex: SN=joe@contoso.com) al teléfono.</span><span class="sxs-lookup"><span data-stu-id="b5ace-114">On Lync Phone Edition clients, after a user signs in and is successfully authenticated by providing a personal identification number (PIN), Skype for Business Server 2015 then provisions the SIP URI to the phone and provisions a Skype for Business Server signed certificate or a user certificate that identifies Joe (Ex: SN=joe@contoso.com ) to the phone.</span></span> <span data-ttu-id="b5ace-115">Este certificado se usa para autenticarse con el Registrador y los Servicios web.</span><span class="sxs-lookup"><span data-stu-id="b5ace-115">This certificate is used for authenticating with the Registrar and Web Services.</span></span>
    
> [!NOTE]
> <span data-ttu-id="b5ace-p105">Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b5ace-p105">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="b5ace-120">Si va a utilizar a los clientes de Lync almacén de Windows de la aplicación, debe habilitar la autenticación de certificado.</span><span class="sxs-lookup"><span data-stu-id="b5ace-120">If you will use Lync Windows Store app clients, you must enable certificate authentication.</span></span>
  
### <a name="to-create-new-registrar-configuration-settings"></a><span data-ttu-id="b5ace-121">Para crear nuevas opciones de configuración de registrador</span><span class="sxs-lookup"><span data-stu-id="b5ace-121">To create new Registrar configuration settings</span></span>

1.  <span data-ttu-id="b5ace-122">Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b5ace-122">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="b5ace-123">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b5ace-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b5ace-124">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-124">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="b5ace-125">En la página **Registrador**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-125">On the **Registrar** page, click **New**</span></span>
    
5. <span data-ttu-id="b5ace-126">En **Seleccionar un servicio**, haga clic en el servicio al que se aplicará el Registrador y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-126">In **Select a Service**, click the service to which the Registrar is to be applied and then click **OK**.</span></span>
    
6. <span data-ttu-id="b5ace-127">En **Nueva configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las funciones de los clientes y la compatibilidad de su entorno:</span><span class="sxs-lookup"><span data-stu-id="b5ace-127">In **New Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="b5ace-128">**Habilitar autenticación Kerberos** para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b5ace-128">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="b5ace-129">**Habilitar autenticación NTLM** para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.</span><span class="sxs-lookup"><span data-stu-id="b5ace-129">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="b5ace-130">**Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="b5ace-130">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
7. <span data-ttu-id="b5ace-131">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-131">Click **Commit**.</span></span>
    
## <a name="modify-existing-registrar-configuration-settings"></a><span data-ttu-id="b5ace-132">Modificar opciones de configuración de un registrador existente</span><span class="sxs-lookup"><span data-stu-id="b5ace-132">Modify existing Registrar configuration settings</span></span>

<span data-ttu-id="b5ace-133">Puede usar el registrador para configurar los protocolos de autenticación del servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="b5ace-133">You can use the Registrar to configure proxy server authentication protocols.</span></span> <span data-ttu-id="b5ace-134">Para obtener información acerca de los protocolos disponibles, vea [Registrar Administrar configuración de Skype para Business Server 2015](registrar-configuration-settings.md).</span><span class="sxs-lookup"><span data-stu-id="b5ace-134">For information about the available protocols, see [Manage Registrar configuration settings in Skype for Business Server 2015](registrar-configuration-settings.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5ace-p107">Se recomienda habilitar Kerberos y NTLM cuando un servidor admita la autenticación para los clientes remotos y de empresa. El servidor perimetral y los servidores internos se comunican para garantizar que solamente se ofrezca la autenticación NTLM a clientes remotos. Si solamente se habilita Kerberos en estos servidores, no podrán autenticar usuarios remotos. Si los usuarios de empresa también se autentican frente al servidor, se usa Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b5ace-p107">We recommend that you enable both Kerberos and NTLM when a server supports authentication for both remote and enterprise clients. The Edge Server and internal servers communicate to ensure that only NTLM authentication is offered to remote clients. If only Kerberos is enabled on these servers, they cannot authenticate remote users. If enterprise users also authenticate against the server, Kerberos is used.</span></span> 
  
<span data-ttu-id="b5ace-139">Siga los pasos a continuación para modificar un registrador existente.</span><span class="sxs-lookup"><span data-stu-id="b5ace-139">Follow these steps to modify an existing Registrar.</span></span> 
  
### <a name="to-modify-existing-registrar-configuration-settings"></a><span data-ttu-id="b5ace-140">Para modificar las opciones de configuración de un registrador existente</span><span class="sxs-lookup"><span data-stu-id="b5ace-140">To modify existing registrar configuration settings</span></span>

1.  <span data-ttu-id="b5ace-141">Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b5ace-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="b5ace-142">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b5ace-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="b5ace-143">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-143">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="b5ace-144">En la página **Registrador**, haga clic en un servicio, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-144">On the **Registrar** page, click a service, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b5ace-145">En **Editar configuración de registrador**, seleccione uno o más de los siguientes elementos en función de las capacidades de los clientes y compatibilidad de su entorno:</span><span class="sxs-lookup"><span data-stu-id="b5ace-145">In **Edit Registrar Setting**, select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
   - <span data-ttu-id="b5ace-146">**Habilitar autenticación Kerberos** para que los servidores del grupo emitan desafíos mediante la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b5ace-146">**Enable Kerberos authentication** to have the servers in the pool issue challenges using Kerberos authentication.</span></span>
    
   - <span data-ttu-id="b5ace-147">**Habilitar autenticación NTLM** para que los servidores del grupo emitan desafíos mediante la autenticación NTLM.</span><span class="sxs-lookup"><span data-stu-id="b5ace-147">**Enable NTLM authentication** to have the servers in the pool issue challenges using NTLM.</span></span>
    
   - <span data-ttu-id="b5ace-148">**Habilitar autenticación de certificados** para que los servidores del grupo emitan desafíos mediante la autenticación de certificados.</span><span class="sxs-lookup"><span data-stu-id="b5ace-148">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
6. <span data-ttu-id="b5ace-149">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-149">Click **Commit**.</span></span>
    
### <a name="to-delete-registrar-configuration-settings"></a><span data-ttu-id="b5ace-150">Para eliminar las opciones de configuración del registrador</span><span class="sxs-lookup"><span data-stu-id="b5ace-150">To delete Registrar configuration settings</span></span>

1. <span data-ttu-id="b5ace-151">Desde una cuenta de usuario que es miembro del grupo RTCUniversalServerAdmins (o tiene derechos de usuario equivalentes), o asignados a la función CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo que esté en la red en el que implementa Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b5ace-151">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="b5ace-152">Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="b5ace-152">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b5ace-153">En la barra de navegación izquierda, haga clic en **Seguridad** y, a continuación, en **Registrador**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-153">In the left navigation bar, click **Security** and then click **Registrar**.</span></span>
    
4. <span data-ttu-id="b5ace-154">En la página **Registrador**, en el campo de búsqueda, escriba el nombre completo o parcial del registrador que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="b5ace-154">On the **Registrar** page, and in the search field, type all or part of the name of the Registrar you want to delete.</span></span>
    
5. <span data-ttu-id="b5ace-155">En la lista, haga clic en el registrador que desee, haga clic en **Editar** y luego en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-155">In the list, click the Registrar that you want, click **Edit**, and then click **Delete**.</span></span>
    
6. <span data-ttu-id="b5ace-156">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b5ace-156">Click **OK**.</span></span>
    
## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b5ace-157">Quitar configuración de Registrar mediante Cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5ace-157">Removing Registrar Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b5ace-158">Puede eliminar la configuración del registro mediante Windows PowerShell y el cmdlet **Remove-CsProxyConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="b5ace-158">You can delete the Registrar configuration settings by using Windows PowerShell and the **Remove-CsProxyConfiguration** cmdlet.</span></span> <span data-ttu-id="b5ace-159">Puede ejecutar este cmdlet desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5ace-159">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b5ace-160">Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="b5ace-160">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="b5ace-161">El proceso es el mismo en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="b5ace-161">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specific-set-of-registrar-security-settings"></a><span data-ttu-id="b5ace-162">Para quitar un conjunto específico de opciones de configuración de seguridad del registrador</span><span class="sxs-lookup"><span data-stu-id="b5ace-162">To remove a specific set of Registrar security settings</span></span>

- <span data-ttu-id="b5ace-163">El siguiente comando quita las opciones de configuración de seguridad del registrador aplicadas al servidor perimetral atl-edge-011.litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="b5ace-163">The following command removes the Registrar security settings applied to the edge Server atl-edge-011.litwareinc.com:</span></span>
    
  ```
  Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a><span data-ttu-id="b5ace-164">Para quitar todas las opciones de configuración de seguridad del registrador aplicadas al ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="b5ace-164">To remove all of the Registrar security settings applied to the site scope</span></span>

- <span data-ttu-id="b5ace-165">El siguiente comando quita todas las opciones de configuración de seguridad del registrador aplicadas al servicio del registrador:</span><span class="sxs-lookup"><span data-stu-id="b5ace-165">The following command removes all the Registrar security settings applied to the Registrar service:</span></span>
    
  ```
  Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration
  ```

### <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a><span data-ttu-id="b5ace-166">Para quitar todas las opciones de configuración de seguridad del registrador que permiten la autenticación NTLM</span><span class="sxs-lookup"><span data-stu-id="b5ace-166">To remove all of the Registrar security settings that allow NTLM authentication</span></span>

- <span data-ttu-id="b5ace-167">El siguiente comando elimina todas las opciones de configuración de seguridad del registrador que permiten el uso de NTLM para la autenticación de cliente:</span><span class="sxs-lookup"><span data-stu-id="b5ace-167">The following command deletes all the Registrar security settings that allow the use of NTLM for client authentication:</span></span>
    
  ```
  Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration
  ```

<span data-ttu-id="b5ace-168">Para obtener más información, vea [Quitar CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b5ace-168">For details, see [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csproxyconfiguration?view=skype-ps).</span></span>
  

