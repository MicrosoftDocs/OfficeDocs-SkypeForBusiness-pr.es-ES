---
title: Administrar la autenticación en dos fases en Skype Empresarial Server
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
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumen: administre la autenticación en dos fases en Skype Empresarial Server.'
ms.openlocfilehash: 415eb23779450bc09cdaa25ea2e60b6cf3526e40
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806550"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a><span data-ttu-id="3d9fb-103">Administrar la autenticación en dos fases en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3d9fb-103">Manage two-factor authentication in Skype for Business Server</span></span>
 
<span data-ttu-id="3d9fb-104">**Resumen:** Administrar la autenticación en dos fases en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-104">**Summary:** Manage two-factor authentication in Skype for Business Server.</span></span>
  
<span data-ttu-id="3d9fb-105">La autenticación en dos fases proporciona una seguridad mejorada al requerir que los usuarios proporcionen dos formas de autenticación o identificación, es decir, una combinación de nombre de usuario y contraseña y un token o certificado.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-105">Two-factor authentication provides improved security by requiring users to provide two forms of authentication or identification, namely a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="3d9fb-106">Esto también se conoce como "algo que tienes, algo que sabes".</span><span class="sxs-lookup"><span data-stu-id="3d9fb-106">This is also known as "something you have, something you know."</span></span> 
  
<span data-ttu-id="3d9fb-107">Un ejemplo típico de autenticación en dos fases con un certificado es el uso de tarjetas inteligentes.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-107">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="3d9fb-108">Una tarjeta inteligente contiene un certificado asociado a la cuenta de usuario y se puede validar con la información de usuario y certificado almacenada en un servidor.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-108">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="3d9fb-109">Al comparar la información de usuario (nombre de usuario y contraseña) con el certificado proporcionado, el servidor valida las credenciales y autentica al usuario.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-109">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>
  
<span data-ttu-id="3d9fb-110">Tenga en cuenta los siguientes temas al configurar un entorno de Skype Empresarial Server para admitir la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-110">Consider the following subjects when configuring a Skype for Business Server environment to support two-factor authentication.</span></span>
  
## <a name="client-support"></a><span data-ttu-id="3d9fb-111">Compatibilidad con clientes</span><span class="sxs-lookup"><span data-stu-id="3d9fb-111">Client Support</span></span>

<span data-ttu-id="3d9fb-112">Las actualizaciones acumulativas para Lync Server 2013: el cliente de escritorio de julio de 2013 y el cliente de Skype Empresarial son los únicos clientes que admiten actualmente la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-112">The Cumulative Updates for Lync Server 2013: July 2013 desktop client and the Skype for Business client are the only clients that currently support two-factor authentication.</span></span>
  
## <a name="topology-requirements"></a><span data-ttu-id="3d9fb-113">Requisitos de topología</span><span class="sxs-lookup"><span data-stu-id="3d9fb-113">Topology Requirements</span></span>

<span data-ttu-id="3d9fb-114">Se recomienda encarecidamente a los clientes implementar la autenticación en dos fases con Skype Empresarial Server dedicado con grupos de servidores perimetrales, directores y usuarios.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-114">Customers are strongly encouraged to deploy two-factor authentication using dedicated Skype for Business Server with Edge, Director, and User Pools.</span></span> <span data-ttu-id="3d9fb-115">Para habilitar la autenticación pasiva para los usuarios, deben deshabilitarse otros métodos de autenticación para otros roles y servicios, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="3d9fb-115">To enable passive authentication for users, other authentication methods must be disabled for other roles and services, including the following:</span></span>
  
|<span data-ttu-id="3d9fb-116">**Tipo de configuración**</span><span class="sxs-lookup"><span data-stu-id="3d9fb-116">**Configuration Type**</span></span>|<span data-ttu-id="3d9fb-117">**Tipo de servicio**</span><span class="sxs-lookup"><span data-stu-id="3d9fb-117">**Service Type**</span></span>|<span data-ttu-id="3d9fb-118">**Rol del servidor**</span><span class="sxs-lookup"><span data-stu-id="3d9fb-118">**Server Role**</span></span>|<span data-ttu-id="3d9fb-119">**Tipo de autenticación que se deshabilitará**</span><span class="sxs-lookup"><span data-stu-id="3d9fb-119">**Authentication Type to Disable**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3d9fb-120">Servicio Web</span><span class="sxs-lookup"><span data-stu-id="3d9fb-120">Web Service</span></span>  <br/> |<span data-ttu-id="3d9fb-121">WebServer</span><span class="sxs-lookup"><span data-stu-id="3d9fb-121">WebServer</span></span>  <br/> |<span data-ttu-id="3d9fb-122">Director</span><span class="sxs-lookup"><span data-stu-id="3d9fb-122">Director</span></span>  <br/> |<span data-ttu-id="3d9fb-123">Kerberos, NTLM y certificado</span><span class="sxs-lookup"><span data-stu-id="3d9fb-123">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="3d9fb-124">Servicio Web</span><span class="sxs-lookup"><span data-stu-id="3d9fb-124">Web Service</span></span>  <br/> |<span data-ttu-id="3d9fb-125">WebServer</span><span class="sxs-lookup"><span data-stu-id="3d9fb-125">WebServer</span></span>  <br/> |<span data-ttu-id="3d9fb-126">Front-end</span><span class="sxs-lookup"><span data-stu-id="3d9fb-126">Front End</span></span>  <br/> |<span data-ttu-id="3d9fb-127">Kerberos, NTLM y certificado</span><span class="sxs-lookup"><span data-stu-id="3d9fb-127">Kerberos, NTLM, and Certificate</span></span>  <br/> |
|<span data-ttu-id="3d9fb-128">Proxy</span><span class="sxs-lookup"><span data-stu-id="3d9fb-128">Proxy</span></span>  <br/> |<span data-ttu-id="3d9fb-129">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="3d9fb-129">EdgeServer</span></span>  <br/> |<span data-ttu-id="3d9fb-130">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3d9fb-130">Edge</span></span>  <br/> |<span data-ttu-id="3d9fb-131">Kerberos y NTLM</span><span class="sxs-lookup"><span data-stu-id="3d9fb-131">Kerberos and NTLM</span></span>  <br/> |
|<span data-ttu-id="3d9fb-132">Proxy</span><span class="sxs-lookup"><span data-stu-id="3d9fb-132">Proxy</span></span>  <br/> |<span data-ttu-id="3d9fb-133">Registrador</span><span class="sxs-lookup"><span data-stu-id="3d9fb-133">Registrar</span></span>  <br/> |<span data-ttu-id="3d9fb-134">Front-end</span><span class="sxs-lookup"><span data-stu-id="3d9fb-134">Front End</span></span>  <br/> |<span data-ttu-id="3d9fb-135">Kerberos y NTLM</span><span class="sxs-lookup"><span data-stu-id="3d9fb-135">Kerberos and NTLM</span></span>  <br/> |
   
<span data-ttu-id="3d9fb-136">A menos que estos tipos de autenticación estén deshabilitados en el nivel de servicio, todas las demás versiones del cliente no podrán iniciar sesión correctamente una vez habilitada la autenticación en dos fases en la implementación.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-136">Unless these authentication types are disabled at the service level, all other versions of the client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>
  
## <a name="skype-for-business-service-discovery"></a><span data-ttu-id="3d9fb-137">Detección de servicio de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="3d9fb-137">Skype for Business Service Discovery</span></span>

<span data-ttu-id="3d9fb-138">Los registros DNS usados por clientes internos o externos para detectar los servicios de Skype Empresarial deben configurarse para resolverse en un servidor de Skype Empresarial que no esté habilitado para la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-138">DNS records used by internal and/or external clients to discover Skype for Business services should be configured to resolve to a Skype for Business server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="3d9fb-139">Con esta configuración, los usuarios de los grupos de Skype Empresarial que no estén habilitados para la autenticación en dos fases no tendrán que escribir un PIN para autenticarse, mientras que los usuarios de los grupos de Skype Empresarial habilitados para la autenticación en dos fases tendrán que escribir su PIN para autenticarse.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-139">With this configuration, users from Skype for Business Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Skype for Business Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>
  
## <a name="exchange-authentication"></a><span data-ttu-id="3d9fb-140">Autenticación de Exchange</span><span class="sxs-lookup"><span data-stu-id="3d9fb-140">Exchange Authentication</span></span>

<span data-ttu-id="3d9fb-141">Los clientes que han implementado la autenticación en dos fases para Microsoft Exchange pueden encontrar que ciertas características del cliente no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-141">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the client are unavailable.</span></span> <span data-ttu-id="3d9fb-142">Esto es actualmente por diseño, ya que el cliente de Skype Empresarial no admite la autenticación en dos fases para las características que dependen de la integración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-142">This is currently by design, as the Skype for Business client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>
  
## <a name="contacts"></a><span data-ttu-id="3d9fb-143">Contactos</span><span class="sxs-lookup"><span data-stu-id="3d9fb-143">Contacts</span></span>

<span data-ttu-id="3d9fb-144">Los usuarios de Skype Empresarial que estén configurados para aprovechar la característica Almacén de contactos unificados verán que sus contactos ya no están disponibles después de iniciar sesión con la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-144">Skype for Business users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>
  
<span data-ttu-id="3d9fb-145">Debe usar el cmdlet **Invoke-CsUcsRollback** para quitar contactos de usuario existentes del almacén de contactos unificados y almacenarlos en Skype Empresarial Server antes de habilitar la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-145">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Skype for Business Server before enabling two-factor authentication.</span></span>
  
## <a name="skill-search"></a><span data-ttu-id="3d9fb-146">Búsqueda de aptitudes</span><span class="sxs-lookup"><span data-stu-id="3d9fb-146">Skill Search</span></span>

<span data-ttu-id="3d9fb-147">Los clientes que han configurado la característica de búsqueda de aptitudes en su entorno de Skype Empresarial verán que esta característica no funciona cuando Skype Empresarial está habilitado para la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-147">Customers who have configured the Skill Search feature in their Skype for Business environment will find that this feature does not work when Skype for Business is enabled for two-factor authentication.</span></span> <span data-ttu-id="3d9fb-148">Esto es por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-148">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>
  
## <a name="credentials"></a><span data-ttu-id="3d9fb-149">Credenciales</span><span class="sxs-lookup"><span data-stu-id="3d9fb-149">Credentials</span></span>

<span data-ttu-id="3d9fb-150">Hay una serie de consideraciones de implementación relacionadas con las credenciales guardadas de Skype Empresarial que pueden afectar a los usuarios que están configurados para usar la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-150">There are a number of deployment considerations involving saved Skype for Business credentials which may impact users who are configured to use two-factor authentication.</span></span>
  
### <a name="deleting-saved-credentials"></a><span data-ttu-id="3d9fb-151">Eliminación de credenciales guardadas</span><span class="sxs-lookup"><span data-stu-id="3d9fb-151">Deleting Saved Credentials</span></span>

<span data-ttu-id="3d9fb-152">Los usuarios  deben usar la opción Eliminar mi información de inicio de sesión en el cliente de Skype Empresarial y eliminar su carpeta de perfil SIP de %localappdata%\Microsoft\Office\15.0\Skype Empresarial antes de intentar iniciar sesión por primera vez mediante la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-152">Users should use the **Delete my sign-in info** option in the Skype for Business client and delete their SIP profile folder from %localappdata%\Microsoft\Office\15.0\Skype for Business before attempting to sign for the first time using two-factor authentication.</span></span>
  
### <a name="disablentcredentials"></a><span data-ttu-id="3d9fb-153">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="3d9fb-153">DisableNTCredentials</span></span>

<span data-ttu-id="3d9fb-154">Con el método de autenticación Kerberos o NTLM, las credenciales de Windows del usuario se usan automáticamente para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-154">With the Kerberos or NTLM authentication method, the user's Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="3d9fb-155">En una implementación típica de Skype Empresarial Server en la que Kerberos o NTLM están habilitados para la autenticación, los usuarios no deben tener que escribir sus credenciales cada vez que inician sesión.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-155">In a typical Skype for Business Server deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>
  
<span data-ttu-id="3d9fb-156">Si se piden credenciales a los usuarios sin especificar antes de que se les pida que escriban su PIN, es posible que la clave del Registro **DisableNTCredentials** esté configurada de forma involuntarla en los equipos cliente, posiblemente a través de la directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-156">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>
  
<span data-ttu-id="3d9fb-157">Para evitar la solicitud adicional de credenciales, cree la siguiente entrada del Registro en la estación de trabajo local o use la plantilla administrativa de Skype Empresarial para aplicar a todos los usuarios de un grupo determinado mediante la directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="3d9fb-157">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a><span data-ttu-id="3d9fb-158">SavePassword</span><span class="sxs-lookup"><span data-stu-id="3d9fb-158">SavePassword</span></span>

<span data-ttu-id="3d9fb-159">Cuando un usuario inicia sesión en Skype Empresarial por primera vez, se le pide que guarde su contraseña.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-159">When a user signs in to Skype for Business for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="3d9fb-160">Si se selecciona, esta opción permite que el certificado de cliente del usuario se almacene en el almacén de certificados personales y que las credenciales de Windows del usuario se almacenen en el Administrador de credenciales del equipo local.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-160">If selected, this option allows the user's client certificate to be stored in the personal certificate store and the user's Windows credentials to be stored in the Credential Manager of the local computer.</span></span>
  
<span data-ttu-id="3d9fb-161">La configuración del Registro **SavePassword** debe deshabilitarse cuando Skype Empresarial está configurado para admitir la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-161">The **SavePassword** registry setting should be disabled when Skype for Business is configured to support two-factor authentication.</span></span> <span data-ttu-id="3d9fb-162">Para evitar que los usuarios guarden sus contraseñas, cambie la siguiente entrada del Registro en la estación de trabajo local o use la plantilla administrativa de Skype Empresarial para aplicar a todos los usuarios de un grupo determinado mediante la directiva de grupo:</span><span class="sxs-lookup"><span data-stu-id="3d9fb-162">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Skype for Business administrative template to apply to all users for a given pool using Group Policy:</span></span>
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="3d9fb-163">Reproducción de tokens de AD FS 2.0</span><span class="sxs-lookup"><span data-stu-id="3d9fb-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="3d9fb-164">AD FS 2.0 proporciona una característica denominada detección de reproducción de tokens, mediante la cual se pueden detectar y descartar varias solicitudes de token que usan el mismo token.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="3d9fb-165">Cuando esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación tanto en el perfil pasivo de WS-Federation como en el perfil webSSO de SAML al asegurarse de que el mismo token nunca se usa más de una vez.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>
  
<span data-ttu-id="3d9fb-166">Esta característica debe habilitarse en situaciones en las que la seguridad es una preocupación muy alta, como cuando se usan quioscos.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="3d9fb-167">Para obtener más información acerca de la detección de reproducción de tokens, vea Procedimientos recomendados para la planeación e implementación seguras de [AD FS 2.0.](https://go.microsoft.com/fwlink/p/?LinkId=309215)</span><span class="sxs-lookup"><span data-stu-id="3d9fb-167">For more information about token replay detection, see [Best Practices for Secure Planning and Deployment of AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).</span></span>
  
## <a name="external-user-access"></a><span data-ttu-id="3d9fb-168">Acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="3d9fb-168">External User Access</span></span>

<span data-ttu-id="3d9fb-169">La configuración de un proxy ADFS o proxy inverso para admitir la autenticación en dos fases de Skype Empresarial desde redes externas no se trata en estos temas.</span><span class="sxs-lookup"><span data-stu-id="3d9fb-169">Configuring an ADFS Proxy or Reverse Proxy to support Skype for Business two-factor authentication from external networks is not covered in these topics.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d9fb-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d9fb-170">See also</span></span>

[<span data-ttu-id="3d9fb-171">Configurar la autenticación en dos fases en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="3d9fb-171">Configure two-factor authentication in Skype for Business Server</span></span>](configure-two-factor.md)
  
