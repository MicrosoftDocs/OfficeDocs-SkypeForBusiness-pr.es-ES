---
title: Administrar la autenticación en dos fases en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumen: Administrar la autenticación de dos factores en Skype para Business Server 2015.'
ms.openlocfilehash: 5933afc311514e841d7fb96f41988d8f495d0bee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server-2015"></a><span data-ttu-id="0a234-103">Administrar la autenticación en dos fases en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="0a234-103">Manage two-factor authentication in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0a234-104">**Resumen:** Administrar la autenticación de dos factores en Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0a234-104">**Summary:** Manage two-factor authentication in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0a234-105">La autenticación en dos fases proporciona seguridad mejorada al exigir a los usuarios que proporcionen dos formas de autenticación o identificación, específicamente una combinación de nombre de usuario/contraseña y un token o certificado.</span><span class="sxs-lookup"><span data-stu-id="0a234-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="0a234-106">Esto también es conocido como "algo que tiene, algo que sabe".</span><span class="sxs-lookup"><span data-stu-id="0a234-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="0a234-p102">Un ejemplo típico de autenticación en dos fases con un certificado es el uso de tarjetas inteligentes. Una tarjeta inteligente contiene un certificado asociado con la cuenta del usuario y se puede validar con información de certificado y usuario almacenada en un servidor. Al comparar la información del usuario (nombre de usuario y contraseña) con el certificado proporcionado, el servidor valida las credenciales y autentica al usuario.</span><span class="sxs-lookup"><span data-stu-id="0a234-p102">A typical example of two-factor authentication with a certificate is the use of smart cards. A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server. By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="0a234-110">Considere a los asuntos siguientes al configurar un Skype para entorno Business Server 2015 para admitir la autenticación de dos factores.</span><span class="sxs-lookup"><span data-stu-id="0a234-110">Consider the following subjects when configuring a Skype for Business Server 2015 environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="0a234-111">Compatibilidad con clientes</span><span class="sxs-lookup"><span data-stu-id="0a234-111">Client Support</span></span>

<span data-ttu-id="0a234-112">Las actualizaciones acumulativas de Lync Server 2013: julio de 2013, cliente de escritorio y el Skype para cliente de negocios son los únicos clientes que actualmente admiten la autenticación de dos factores.</span><span class="sxs-lookup"><span data-stu-id="0a234-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="0a234-113">Requisitos de topología</span><span class="sxs-lookup"><span data-stu-id="0a234-113">Topology Requirements</span></span>

<span data-ttu-id="0a234-114">Los clientes se recomienda encarecidamente implementar autenticación de dos factores mediante Skype dedicado para Business Server 2015 con borde, Director y grupos de usuario.</span><span class="sxs-lookup"><span data-stu-id="0a234-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server 2015 with Edge, Director, and User Pools.</span></span> <span data-ttu-id="0a234-115">Para habilitar la autenticación pasiva para los usuarios, se necesitan deshabilitar los demás métodos de autenticación para otros roles y servicios, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0a234-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="0a234-116">**Tipo de configuración**</span><span class="sxs-lookup"><span data-stu-id="0a234-116">**Configuration Type**</span></span>|<span data-ttu-id="0a234-117">**Tipo de servicio**</span><span class="sxs-lookup"><span data-stu-id="0a234-117">**Service Type**</span></span>|<span data-ttu-id="0a234-118">**Función de servidor**</span><span class="sxs-lookup"><span data-stu-id="0a234-118">**Server Role**</span></span>|<span data-ttu-id="0a234-119">**Tipo de autenticación para deshabilitar**</span><span class="sxs-lookup"><span data-stu-id="0a234-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0a234-120">Servicio web</span><span class="sxs-lookup"><span data-stu-id="0a234-120">Web Service</span></span>  <br/> |<span data-ttu-id="0a234-121">Servidor Web</span><span class="sxs-lookup"><span data-stu-id="0a234-121">WebServer</span></span>  <br/> |<span data-ttu-id="0a234-122">Director</span><span class="sxs-lookup"><span data-stu-id="0a234-122">Director</span></span>  <br/> |<span data-ttu-id="0a234-123">Kerberos, NTLM y certificado</span><span class="sxs-lookup"><span data-stu-id="0a234-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="0a234-124">Servicio web</span><span class="sxs-lookup"><span data-stu-id="0a234-124">Web Service</span></span>  <br/> |<span data-ttu-id="0a234-125">Servidor Web</span><span class="sxs-lookup"><span data-stu-id="0a234-125">WebServer</span></span>  <br/> |<span data-ttu-id="0a234-126">Front-end</span><span class="sxs-lookup"><span data-stu-id="0a234-126">Front End</span></span>  <br/> |<span data-ttu-id="0a234-127">Kerberos, NTLM y certificado</span><span class="sxs-lookup"><span data-stu-id="0a234-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="0a234-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="0a234-128">Proxy</span></span>  <br/> |<span data-ttu-id="0a234-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="0a234-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="0a234-130">Perimetral</span><span class="sxs-lookup"><span data-stu-id="0a234-130">Edge</span></span>  <br/> |<span data-ttu-id="0a234-131">Kerberos y NTLM</span><span class="sxs-lookup"><span data-stu-id="0a234-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="0a234-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="0a234-132">Proxy</span></span>  <br/> |<span data-ttu-id="0a234-133">Registrador</span><span class="sxs-lookup"><span data-stu-id="0a234-133">Registrar</span></span>  <br/> |<span data-ttu-id="0a234-134">Front-end</span><span class="sxs-lookup"><span data-stu-id="0a234-134">Front End</span></span>  <br/> |<span data-ttu-id="0a234-135">Kerberos y NTLM</span><span class="sxs-lookup"><span data-stu-id="0a234-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="0a234-136">A menos que estos tipos de autenticación se deshabiliten en el nivel de servicio, ninguna de las demás versiones del cliente podrá iniciar sesión correctamente una vez que la autenticación en dos fases esté habilitada dentro de la implementación.</span><span class="sxs-lookup"><span data-stu-id="0a234-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="0a234-137">Detección de servicios de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0a234-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="0a234-138">Registros DNS utilizados por los clientes internos o externos para descubrir Skype para servicios empresariales deben configurarse para resolver como un Skype para Business server que no está habilitado para la autenticación de dos factores.</span><span class="sxs-lookup"><span data-stu-id="0a234-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="0a234-139">Con esta configuración, los usuarios de Skype para grupos de negocios que no están habilitados para autenticación de dos factores no le pedirá que escriba un NIP para autenticar, mientras que los usuarios de Skype para grupos de negocios que están habilitados para la autenticación de dos factores pedirá que introduzca su NIP para autenticar.</span><span class="sxs-lookup"><span data-stu-id="0a234-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="0a234-140">Autenticación de Exchange</span><span class="sxs-lookup"><span data-stu-id="0a234-140">Exchange Authentication</span></span>

<span data-ttu-id="0a234-141">Clientes que han implementado la autenticación de dos factores para Microsoft Exchange pueden encontrar ciertas características en el cliente no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="0a234-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="0a234-142">Actualmente esto es por diseño, como el Skype para Business client no admite la autenticación de dos factores para las características que dependen de la integración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="0a234-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="0a234-143">Contactos</span><span class="sxs-lookup"><span data-stu-id="0a234-143">Contacts</span></span>

<span data-ttu-id="0a234-144">Skype para usuarios profesionales que están configurados para aprovechar la característica almacén de contacto unificado encontrará sus contactos ya no están disponibles después de iniciar sesión con autenticación de dos factores.</span><span class="sxs-lookup"><span data-stu-id="0a234-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="0a234-145">Debe utilizar el cmdlet **Invoke-CsUcsRollback** para quitar contactos de usuario existentes desde el almacén de contacto unificado y almacenarlos en Skype para Business Server 2015 antes de habilitar la autenticación de dos factores.</span><span class="sxs-lookup"><span data-stu-id="0a234-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server 2015 before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="0a234-146">Búsqueda de aptitudes</span><span class="sxs-lookup"><span data-stu-id="0a234-146">Skill Search</span></span>

<span data-ttu-id="0a234-147">Los clientes que han configurado la característica de búsqueda de perfiles en su Skype para el entorno de negocios encontrarán que esta característica no funciona cuando Skype para empresas está habilitado para la autenticación de dos factores.</span><span class="sxs-lookup"><span data-stu-id="0a234-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="0a234-148">Esto sucede por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="0a234-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="0a234-149">Credenciales</span><span class="sxs-lookup"><span data-stu-id="0a234-149">Credentials</span></span>

<span data-ttu-id="0a234-150">Hay una serie de consideraciones de implementación que implican Skype guardado las credenciales de negocios que puede afectar a los usuarios que están configurados para usar la autenticación de dos factores.</span><span class="sxs-lookup"><span data-stu-id="0a234-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="0a234-151">Eliminación de credenciales guardadas</span><span class="sxs-lookup"><span data-stu-id="0a234-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="0a234-152">Usuarios deben utilizar la opción **Eliminar mi información de inicio de sesión** en el Skype para cliente de empresa y eliminar su carpeta de perfil SIP de %localappdata%\Microsoft\Office\15.0\Skype para el negocio antes de intentar iniciar sesión por primera vez mediante dos factores autenticación.</span><span class="sxs-lookup"><span data-stu-id="0a234-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="0a234-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="0a234-153">DisableNTCredentials</span></span>

<span data-ttu-id="0a234-154">Con el método de autenticación Kerberos o NTLM, las credenciales de Windows se utilizan automáticamente para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="0a234-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="0a234-155">En un típico Skype para la implementación de Business Server 2015 donde está habilitado Kerberos o NTLM para la autenticación, los usuarios no deben tener que escribir sus credenciales cada vez que inician sesión en.</span><span class="sxs-lookup"><span data-stu-id="0a234-155">In a typical Skype for Business Server 2015 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="0a234-156">Si se les solicitan de manera no intencionada las credenciales a los usuarios antes de que se les pida especificar su PIN, la clave del Registro **DisableNTCredentials** puede configurarse de manera no intencionada en los equipos cliente, posiblemente a través de la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="0a234-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="0a234-157">Para evitar que la solicitud de credenciales adicional, cree la entrada de registro siguiente en la estación de trabajo o utilizar el Skype para plantillas administrativas de negocio para aplicar a todos los usuarios de un grupo determinado mediante Directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="0a234-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="0a234-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="0a234-158">SavePassword</span></span>

<span data-ttu-id="0a234-159">Cuando un usuario inicia sesión en Skype para el negocio por primera vez, se pide al guardar su contraseña de usuario.</span><span class="sxs-lookup"><span data-stu-id="0a234-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="0a234-160">Si se selecciona, esta opción permite que el certificado del usuario cliente para almacenarse en el almacén de certificados personales y credenciales de Windows del usuario se almacenan en el Administrador de credenciales del equipo local.</span><span class="sxs-lookup"><span data-stu-id="0a234-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="0a234-161">La configuración del registro **SavePassword** debe deshabilitarse cuando Skype para empresas está configurado para admitir la autenticación de dos factores.</span><span class="sxs-lookup"><span data-stu-id="0a234-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="0a234-162">Para impedir que los usuarios guarden sus contraseñas, cambiar la entrada de registro siguiente en la estación de trabajo o utilizar el Skype para plantillas administrativas de negocio para aplicar a todos los usuarios de un grupo determinado mediante Directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="0a234-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="0a234-163">Reproducción de tokens de AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="0a234-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="0a234-p110">AD FS 2.0 proporciona una característica que se conoce como detección de reproducción de tokens, con la cual varias solicitudes de tokens que usan el mismo token se pueden detectar y descartar. Cuando esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación en el perfil pasivo de la federación WS y el perfil de SAML WebSSO asegurándose de que el mismo token nunca se use más de una vez.</span><span class="sxs-lookup"><span data-stu-id="0a234-p110">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded. When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="0a234-166">Esta característica necesita habilitarse en situaciones donde la seguridad es extremadamente preocupante como cuando se usan quioscos.</span><span class="sxs-lookup"><span data-stu-id="0a234-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="0a234-167">Para obtener más información acerca de la detección de reproducción token, vea [Prácticas recomendadas para proteger planeamiento e implementación de AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span><span class="sxs-lookup"><span data-stu-id="0a234-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="0a234-168">Acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="0a234-168">External User Access</span></span>

<span data-ttu-id="0a234-169">Configurar un Proxy ADFS o Proxy inverso para admitir Skype para autenticación de dos factores de negocios desde redes externas que no se trata en estos temas.</span><span class="sxs-lookup"><span data-stu-id="0a234-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0a234-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a234-170">See also</span></span>

#### 

[<span data-ttu-id="0a234-171">Configurar la autenticación de dos factores en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0a234-171">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)
  
[<span data-ttu-id="0a234-172">Configurar la autenticación de dos factores en Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0a234-172">Configure two-factor authentication in Skype for Business Server 2015</span></span>](configure.md)

