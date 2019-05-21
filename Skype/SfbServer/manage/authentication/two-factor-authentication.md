---
title: Administrar la autenticación en dos fases en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumen: administre la autenticación en dos fases en Skype empresarial Server.'
ms.openlocfilehash: ccda6795fa5033c792c293701d951e3111666e82
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297564"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="9e969-103">Administrar la autenticación en dos fases en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9e969-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="9e969-104">**Resumen:** Administrar la autenticación en dos fases en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9e969-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="9e969-105">La autenticación en dos fases proporciona seguridad mejorada al exigir a los usuarios que proporcionen dos formas de autenticación o identificación, específicamente una combinación de nombre de usuario/contraseña y un token o certificado.</span><span class="sxs-lookup"><span data-stu-id="9e969-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="9e969-106">Esto también se conoce como "algo que tienes, algo que conoces".</span><span class="sxs-lookup"><span data-stu-id="9e969-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="9e969-p102">Un ejemplo típico de autenticación en dos fases con un certificado es el uso de tarjetas inteligentes. Una tarjeta inteligente contiene un certificado asociado con la cuenta del usuario y se puede validar con información de certificado y usuario almacenada en un servidor. Al comparar la información del usuario (nombre de usuario y contraseña) con el certificado proporcionado, el servidor valida las credenciales y autentica al usuario.</span><span class="sxs-lookup"><span data-stu-id="9e969-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="9e969-110">Tenga en cuenta lo siguiente cuando configure un entorno de Skype empresarial Server para que admita la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="9e969-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="9e969-111">Compatibilidad con clientes</span><span class="sxs-lookup"><span data-stu-id="9e969-111">Client Support</span></span>

<span data-ttu-id="9e969-112">Las actualizaciones acumulativas para Lync Server 2013: el cliente de escritorio de julio de 2013 y el cliente de Skype empresarial son los únicos clientes que admiten actualmente la autenticación de dos factores.</span><span class="sxs-lookup"><span data-stu-id="9e969-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="9e969-113">Requisitos de topología</span><span class="sxs-lookup"><span data-stu-id="9e969-113">Topology Requirements</span></span>

<span data-ttu-id="9e969-114">Se recomienda a los clientes implementar la autenticación en dos fases con un servidor dedicado de Skype empresarial con las agrupaciones de Edge, director y usuario.</span><span class="sxs-lookup"><span data-stu-id="9e969-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="9e969-115">Para habilitar la autenticación pasiva para los usuarios, se necesitan deshabilitar los demás métodos de autenticación para otros roles y servicios, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9e969-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="9e969-116">**Tipo de configuración**</span><span class="sxs-lookup"><span data-stu-id="9e969-116">**Configuration Type**</span></span>|<span data-ttu-id="9e969-117">**Tipo de servicio**</span><span class="sxs-lookup"><span data-stu-id="9e969-117">**Service Type**</span></span>|<span data-ttu-id="9e969-118">**Rol de servidor**</span><span class="sxs-lookup"><span data-stu-id="9e969-118">**Server Role**</span></span>|<span data-ttu-id="9e969-119">**Tipo de autenticación para deshabilitar**</span><span class="sxs-lookup"><span data-stu-id="9e969-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e969-120">Servicio web</span><span class="sxs-lookup"><span data-stu-id="9e969-120">Web Service</span></span>  <br/> |<span data-ttu-id="9e969-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="9e969-121">WebServer</span></span>  <br/> |<span data-ttu-id="9e969-122">Director</span><span class="sxs-lookup"><span data-stu-id="9e969-122">Director</span></span>  <br/> |<span data-ttu-id="9e969-123">Kerberos, NTLM y certificado</span><span class="sxs-lookup"><span data-stu-id="9e969-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="9e969-124">Servicio web</span><span class="sxs-lookup"><span data-stu-id="9e969-124">Web Service</span></span>  <br/> |<span data-ttu-id="9e969-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="9e969-125">WebServer</span></span>  <br/> |<span data-ttu-id="9e969-126">Front-end</span><span class="sxs-lookup"><span data-stu-id="9e969-126">Front End</span></span>  <br/> |<span data-ttu-id="9e969-127">Kerberos, NTLM y certificado</span><span class="sxs-lookup"><span data-stu-id="9e969-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="9e969-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="9e969-128">Proxy</span></span>  <br/> |<span data-ttu-id="9e969-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="9e969-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="9e969-130">Perimetral</span><span class="sxs-lookup"><span data-stu-id="9e969-130">Edge</span></span>  <br/> |<span data-ttu-id="9e969-131">Kerberos y NTLM</span><span class="sxs-lookup"><span data-stu-id="9e969-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="9e969-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="9e969-132">Proxy</span></span>  <br/> |<span data-ttu-id="9e969-133">Registrador</span><span class="sxs-lookup"><span data-stu-id="9e969-133">Registrar</span></span>  <br/> |<span data-ttu-id="9e969-134">Front-end</span><span class="sxs-lookup"><span data-stu-id="9e969-134">Front End</span></span>  <br/> |<span data-ttu-id="9e969-135">Kerberos y NTLM</span><span class="sxs-lookup"><span data-stu-id="9e969-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="9e969-136">A menos que estos tipos de autenticación se deshabiliten en el nivel de servicio, ninguna de las demás versiones del cliente podrá iniciar sesión correctamente una vez que la autenticación en dos fases esté habilitada dentro de la implementación.</span><span class="sxs-lookup"><span data-stu-id="9e969-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="9e969-137">Detección de servicios de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="9e969-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="9e969-138">Los registros DNS usados por clientes internos o externos para descubrir servicios de Skype empresarial se deben configurar para que se resuelvan en un servidor de Skype empresarial que no esté habilitado para la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="9e969-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="9e969-139">Con esta configuración, los usuarios de grupos de Skype para empresas que no estén habilitados para la autenticación de dos factores no tendrán que introducir un PIN para autenticar, mientras que los usuarios de los grupos de Skype empresarial habilitados para la autenticación en dos fases se necesario para introducir su PIN para autenticar.</span><span class="sxs-lookup"><span data-stu-id="9e969-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="9e969-140">Autenticación de Exchange</span><span class="sxs-lookup"><span data-stu-id="9e969-140">Exchange Authentication</span></span>

<span data-ttu-id="9e969-141">Es posible que los clientes que hayan implementado la autenticación en dos fases de Microsoft Exchange no encuentren disponibles determinadas características del cliente.</span><span class="sxs-lookup"><span data-stu-id="9e969-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="9e969-142">Esto se ha hecho por diseño, ya que el cliente de Skype empresarial no admite la autenticación en dos fases para características que dependen de la integración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="9e969-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="9e969-143">Contactos</span><span class="sxs-lookup"><span data-stu-id="9e969-143">Contacts</span></span>

<span data-ttu-id="9e969-144">Los usuarios de Skype empresarial que estén configurados para aprovechar la característica de almacenamiento de contactos unificado encontrarán que sus contactos ya no están disponibles después de iniciar sesión con la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="9e969-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="9e969-145">Debe usar el cmdlet **Invoke-CsUcsRollback** para quitar los contactos de usuario existentes del almacén de contactos unificado y almacenarlos en Skype empresarial Server antes de habilitar la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="9e969-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="9e969-146">Búsqueda de aptitudes</span><span class="sxs-lookup"><span data-stu-id="9e969-146">Skill Search</span></span>

<span data-ttu-id="9e969-147">Los clientes que hayan configurado la característica de búsqueda de aptitudes en su entorno de Skype empresarial encontrarán que esta característica no funciona cuando Skype empresarial está habilitado para la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="9e969-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="9e969-148">Esto sucede por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="9e969-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="9e969-149">Credenciales</span><span class="sxs-lookup"><span data-stu-id="9e969-149">Credentials</span></span>

<span data-ttu-id="9e969-150">Existen diversas consideraciones de implementación que afectan a las credenciales de Skype empresarial guardadas, que pueden afectar a los usuarios que están configurados para usar la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="9e969-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="9e969-151">Eliminación de credenciales guardadas</span><span class="sxs-lookup"><span data-stu-id="9e969-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="9e969-152">Los usuarios deben usar la opción **eliminar mi información de inicio de sesión** en el cliente de Skype empresarial y eliminar su carpeta de perfil SIP de%LocalAppData%\Microsoft\Office\15.0\Skype para empresas antes de intentar iniciar sesión por primera vez con dos factores autenticación.</span><span class="sxs-lookup"><span data-stu-id="9e969-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="9e969-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="9e969-153">DisableNTCredentials</span></span>

<span data-ttu-id="9e969-154">Con el método de autenticación Kerberos o NTLM, las credenciales de Windows del usuario se usan automáticamente para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9e969-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="9e969-155">En una implementación típica de Skype empresarial Server donde se habilita Kerberos o NTLM para la autenticación, los usuarios no deben especificar sus credenciales cada vez que inicien sesión.</span><span class="sxs-lookup"><span data-stu-id="9e969-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="9e969-156">Si se les solicitan de manera no intencionada las credenciales a los usuarios antes de que se les pida especificar su PIN, la clave del Registro **DisableNTCredentials** puede configurarse de manera no intencionada en los equipos cliente, posiblemente a través de la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="9e969-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="9e969-157">Para evitar la solicitud de credenciales adicionales, cree la siguiente entrada de registro en la estación de trabajo local o use la plantilla administrativa de Skype empresarial para aplicar a todos los usuarios de un grupo determinado mediante una directiva de Grupo:</span><span class="sxs-lookup"><span data-stu-id="9e969-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="9e969-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="9e969-158">SavePassword</span></span>

<span data-ttu-id="9e969-159">Cuando un usuario inicia sesión en Skype empresarial por primera vez, se le pide al usuario que guarde su contraseña.</span><span class="sxs-lookup"><span data-stu-id="9e969-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="9e969-160">Si se selecciona, esta opción permite que el certificado de cliente del usuario se almacene en el almacén de certificados personales y las credenciales de Windows del usuario para que se almacenen en el administrador de credenciales del equipo local.</span><span class="sxs-lookup"><span data-stu-id="9e969-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="9e969-161">La configuración del registro **SavePassword** debe estar deshabilitada cuando Skype empresarial está configurado para admitir la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="9e969-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="9e969-162">Para impedir que los usuarios guarden sus contraseñas, cambie la siguiente entrada del registro en la estación de trabajo local o use la plantilla administrativa de Skype empresarial para aplicar a todos los usuarios de un grupo determinado mediante una directiva de Grupo:</span><span class="sxs-lookup"><span data-stu-id="9e969-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="9e969-163">Reproducción de tokens de AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="9e969-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="9e969-p110">AD FS 2.0 proporciona una característica que se conoce como detección de reproducción de tokens, con la cual varias solicitudes de tokens que usan el mismo token se pueden detectar y descartar. Cuando esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación en el perfil pasivo de la federación WS y el perfil de SAML WebSSO asegurándose de que el mismo token nunca se use más de una vez.</span><span class="sxs-lookup"><span data-stu-id="9e969-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="9e969-166">Esta característica necesita habilitarse en situaciones donde la seguridad es extremadamente preocupante como cuando se usan quioscos.</span><span class="sxs-lookup"><span data-stu-id="9e969-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="9e969-167">Para obtener más información sobre la detección de reproducción de tokens, vea [procedimientos recomendados para la planeación y la implementación de AD FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span><span class="sxs-lookup"><span data-stu-id="9e969-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="9e969-168">Acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="9e969-168">External User Access</span></span>

<span data-ttu-id="9e969-169">En estos temas no se aborda la configuración de un proxy de ADFS o proxy inverso para admitir la autenticación de dos factores de Skype empresarial desde redes externas.</span><span class="sxs-lookup"><span data-stu-id="9e969-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e969-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e969-170">See also</span></span>

[<span data-ttu-id="9e969-171">Configurar la autenticación en dos fases en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9e969-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
