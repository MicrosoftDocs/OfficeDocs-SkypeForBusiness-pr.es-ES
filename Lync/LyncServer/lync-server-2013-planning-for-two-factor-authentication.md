---
title: 'Lync Server 2013: Planeación de la autenticación en dos fases'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba76bbc896c1da2929a584611af0607a51d5afcc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="b48e9-102">Planeación de la autenticación en dos fases en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b48e9-102">Planning for two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b48e9-103">_**Última modificación del tema:** 2015-04-06_</span><span class="sxs-lookup"><span data-stu-id="b48e9-103">_**Topic Last Modified:** 2015-04-06_</span></span>

<span data-ttu-id="b48e9-104">La siguiente es una lista de consideraciones de implementación al configurar un entorno de Microsoft Lync Server 2013 para que admita la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-104">The following is a list of deployment considerations when configuring a Microsoft Lync Server 2013 environment to support two-factor authentication.</span></span>

<div>

## <a name="client-support"></a><span data-ttu-id="b48e9-105">Compatibilidad con clientes</span><span class="sxs-lookup"><span data-stu-id="b48e9-105">Client Support</span></span>

<span data-ttu-id="b48e9-106">Las actualizaciones acumulativas de Lync 2013 para Lync Server 2013: el cliente de escritorio de julio de 2013 y todos los clientes móviles admiten actualmente la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-106">The Lync 2013 Cumulative Updates for Lync Server 2013: July 2013 desktop client and all mobile clients currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="b48e9-107">Requisitos de topología</span><span class="sxs-lookup"><span data-stu-id="b48e9-107">Topology Requirements</span></span>

<span data-ttu-id="b48e9-108">Se recomienda encarecidamente a los clientes que implementen la autenticación en dos fases con el servicio dedicado Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: los grupos de usuarios de la periferia, director y usuario de 2013 de julio.</span><span class="sxs-lookup"><span data-stu-id="b48e9-108">Customers are strongly encouraged to deploy two-factor authentication using dedicated Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Edge, Director, and User Pools.</span></span> <span data-ttu-id="b48e9-109">Para habilitar la autenticación pasiva para los usuarios de Lync, deben estar deshabilitados otros métodos de autenticación para otros roles y servicios, incluidos los siguientes:</span><span class="sxs-lookup"><span data-stu-id="b48e9-109">To enable passive authentication for Lync users, other authentication methods must be disabled for other roles and services, including the following:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b48e9-110">Tipo de configuración</span><span class="sxs-lookup"><span data-stu-id="b48e9-110">Configuration Type</span></span></th>
<th><span data-ttu-id="b48e9-111">Tipo de servicio</span><span class="sxs-lookup"><span data-stu-id="b48e9-111">Service Type</span></span></th>
<th><span data-ttu-id="b48e9-112">Rol de servidor</span><span class="sxs-lookup"><span data-stu-id="b48e9-112">Server Role</span></span></th>
<th><span data-ttu-id="b48e9-113">Tipo de autenticación que se va a deshabilitar</span><span class="sxs-lookup"><span data-stu-id="b48e9-113">Authentication Type to Disable</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b48e9-114">Servicio Web</span><span class="sxs-lookup"><span data-stu-id="b48e9-114">Web Service</span></span></p></td>
<td><p><span data-ttu-id="b48e9-115">WebServer</span><span class="sxs-lookup"><span data-stu-id="b48e9-115">WebServer</span></span></p></td>
<td><p><span data-ttu-id="b48e9-116">Dirección</span><span class="sxs-lookup"><span data-stu-id="b48e9-116">Director</span></span></p></td>
<td><p><span data-ttu-id="b48e9-117">Kerberos, NTLM y certificado</span><span class="sxs-lookup"><span data-stu-id="b48e9-117">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b48e9-118">Servicio Web</span><span class="sxs-lookup"><span data-stu-id="b48e9-118">Web Service</span></span></p></td>
<td><p><span data-ttu-id="b48e9-119">WebServer</span><span class="sxs-lookup"><span data-stu-id="b48e9-119">WebServer</span></span></p></td>
<td><p><span data-ttu-id="b48e9-120">Front-end</span><span class="sxs-lookup"><span data-stu-id="b48e9-120">Front End</span></span></p></td>
<td><p><span data-ttu-id="b48e9-121">Kerberos, NTLM y certificado</span><span class="sxs-lookup"><span data-stu-id="b48e9-121">Kerberos, NTLM, and Certificate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b48e9-122">Proxy</span><span class="sxs-lookup"><span data-stu-id="b48e9-122">Proxy</span></span></p></td>
<td><p><span data-ttu-id="b48e9-123">EdgeServer</span><span class="sxs-lookup"><span data-stu-id="b48e9-123">EdgeServer</span></span></p></td>
<td><p><span data-ttu-id="b48e9-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b48e9-124">Edge</span></span></p></td>
<td><p><span data-ttu-id="b48e9-125">Kerberos y NTLM</span><span class="sxs-lookup"><span data-stu-id="b48e9-125">Kerberos and NTLM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b48e9-126">Proxy</span><span class="sxs-lookup"><span data-stu-id="b48e9-126">Proxy</span></span></p></td>
<td><p><span data-ttu-id="b48e9-127">Dominios</span><span class="sxs-lookup"><span data-stu-id="b48e9-127">Registrar</span></span></p></td>
<td><p><span data-ttu-id="b48e9-128">Front-end</span><span class="sxs-lookup"><span data-stu-id="b48e9-128">Front End</span></span></p></td>
<td><p><span data-ttu-id="b48e9-129">Kerberos y NTLM</span><span class="sxs-lookup"><span data-stu-id="b48e9-129">Kerberos and NTLM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b48e9-130">A menos que estos tipos de autenticación estén deshabilitados en el nivel de servicio, todas las demás versiones del cliente de Lync no podrán iniciar sesión correctamente una vez que se haya habilitado la autenticación en dos fases dentro de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b48e9-130">Unless these authentication types are disabled at the service level, all other versions of the Lync client will be unable to sign in successfully once two-factor authentication is enabled within in your deployment.</span></span>

</div>

<div>

## <a name="lync-service-discovery"></a><span data-ttu-id="b48e9-131">Detección de servicios de Lync</span><span class="sxs-lookup"><span data-stu-id="b48e9-131">Lync Service Discovery</span></span>

<span data-ttu-id="b48e9-132">Los registros DNS que usan los clientes internos o externos para detectar servicios de Lync deben configurarse para que se resuelvan en un servidor de Lync que no está habilitado para la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-132">DNS records used by internal and/or external clients to discover Lync services should be configured to resolve to a Lync server that is not enabled for two-factor authentication.</span></span> <span data-ttu-id="b48e9-133">Con esta configuración, los usuarios de los grupos de Lync que no están habilitados para la autenticación en dos fases no tendrán que especificar un PIN para autenticarse, mientras que los usuarios de los grupos de Lync que estén habilitados para la autenticación en dos fases tendrán que escribir su PIN para autenticar.</span><span class="sxs-lookup"><span data-stu-id="b48e9-133">With this configuration, users from Lync Pools that are not enabled for two-factor authentication will not be required to enter a PIN to authenticate, while users from Lync Pools that are enabled for two-factor authentication will be required to enter their PIN to authenticate.</span></span>

</div>

<div>

## <a name="exchange-authentication"></a><span data-ttu-id="b48e9-134">Autenticación de Exchange</span><span class="sxs-lookup"><span data-stu-id="b48e9-134">Exchange Authentication</span></span>

<span data-ttu-id="b48e9-135">Los clientes que hayan implementado la autenticación en dos fases de Microsoft Exchange podrían encontrar que determinadas características del cliente de Lync no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="b48e9-135">Customers who have deployed two-factor authentication for Microsoft Exchange may find that certain features in the Lync client are unavailable.</span></span> <span data-ttu-id="b48e9-136">Actualmente es una característica de diseño, ya que el cliente de Lync no admite la autenticación en dos fases para las características que dependen de la integración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="b48e9-136">This is currently by design, as the Lync client does not support two-factor authentication for features that are dependent on Exchange integration.</span></span>

</div>

<div>

## <a name="lync-contacts"></a><span data-ttu-id="b48e9-137">Contactos de Lync</span><span class="sxs-lookup"><span data-stu-id="b48e9-137">Lync Contacts</span></span>

<span data-ttu-id="b48e9-138">Los usuarios de Lync que están configurados para aprovechar la característica de almacenamiento de contactos unificado comprobarán que sus contactos ya no están disponibles después de iniciar sesión con la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-138">Lync users who are configured to leverage the Unified Contact Store feature will find that their contacts are no longer available after signing in with two-factor authentication.</span></span>

<span data-ttu-id="b48e9-139">Debe usar el cmdlet **Invoke-CsUcsRollback** para quitar los contactos de usuario existentes del almacén de contactos unificados y almacenarlos en Lync Server 2013 antes de habilitar la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-139">You should use the **Invoke-CsUcsRollback** cmdlet to remove existing user contacts from the Unified Contact Store and store them in Lync Server 2013 before enabling two-factor authentication.</span></span>

</div>

<div>

## <a name="skill-search"></a><span data-ttu-id="b48e9-140">Búsqueda de aptitudes</span><span class="sxs-lookup"><span data-stu-id="b48e9-140">Skill Search</span></span>

<span data-ttu-id="b48e9-141">Los clientes que hayan configurado la característica de búsqueda de aptitudes en su entorno de Lync comprobarán que esta característica no funciona cuando Lync está habilitado para la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-141">Customers who have configured the Skill Search feature in their Lync environment will find that this feature does not work when Lync is enabled for two-factor authentication.</span></span> <span data-ttu-id="b48e9-142">Esto es así por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-142">This is by design, as Microsoft SharePoint does not currently support two-factor authentication.</span></span>

</div>

<div>

## <a name="lync-credentials"></a><span data-ttu-id="b48e9-143">Credenciales de Lync</span><span class="sxs-lookup"><span data-stu-id="b48e9-143">Lync Credentials</span></span>

<span data-ttu-id="b48e9-144">Hay varias consideraciones de implementación que implican las credenciales de Lync guardadas que pueden afectar a los usuarios que están configurados para usar la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-144">There are a number of deployment considerations involving saved Lync credentials which may impact users who are configured to use two-factor authentication.</span></span>

<div>

## <a name="deleting-saved-credentials"></a><span data-ttu-id="b48e9-145">Eliminación de credenciales guardadas</span><span class="sxs-lookup"><span data-stu-id="b48e9-145">Deleting Saved Credentials</span></span>

<span data-ttu-id="b48e9-146">Los usuarios de clientes de escritorio deben usar la opción **eliminar mi información de inicio de sesión** en el cliente Lync y eliminar su carpeta de perfil\\SIP\\de\\%\\LocalAppData% Microsoft Office 15,0 Lync antes de intentar iniciar sesión por primera vez mediante la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-146">Desktop client users should use the **Delete my sign-in info** option in the Lync client and delete their SIP profile folder from %localappdata%\\Microsoft\\Office\\15.0\\Lync before attempting to sign for the first time using two-factor authentication.</span></span>

</div>

<div>

## <a name="disablentcredentials"></a><span data-ttu-id="b48e9-147">DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="b48e9-147">DisableNTCredentials</span></span>

<span data-ttu-id="b48e9-148">Con el método de autenticación Kerberos o NTLM, las credenciales de Windows del usuario se usan automáticamente para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="b48e9-148">With the Kerberos or NTLM authentication method, the user’s Windows credentials are used automatically for authentication.</span></span> <span data-ttu-id="b48e9-149">En una implementación típica de Lync Server 2013 en la que se habilita Kerberos o NTLM para la autenticación, los usuarios no deben especificar sus credenciales cada vez que inicien sesión.</span><span class="sxs-lookup"><span data-stu-id="b48e9-149">In a typical Lync Server 2013 deployment where Kerberos and/or NTLM is enabled for authentication, users should not have to enter their credentials every time that they sign in.</span></span>

<span data-ttu-id="b48e9-150">Si se solicitan involuntariamente las credenciales a los usuarios antes de que se les pida que especifiquen su PIN, es posible que la clave del registro **DisableNTCredentials** no esté configurada de forma accidental en los equipos cliente, posiblemente a través de la Directiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="b48e9-150">If users are unintentionally prompted for credentials before they are prompted to enter their PIN, the **DisableNTCredentials** registry key may be unintentionally configured on client computers, possibly through Group Policy.</span></span>

<span data-ttu-id="b48e9-151">Para evitar la solicitud adicional de credenciales, cree la siguiente entrada del registro en la estación de trabajo local o use la plantilla administrativa de Lync para aplicarla a todos los usuarios de un grupo de servidores dado mediante la Directiva de Grupo:</span><span class="sxs-lookup"><span data-stu-id="b48e9-151">To prevent the additional prompt for credentials, create the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="b48e9-152">HKEY\_directivas\_\\de\\software\\del equipo\\local\\de\\Microsoft Office 15,0 Lync</span><span class="sxs-lookup"><span data-stu-id="b48e9-152">HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="b48e9-153">REG\_DWORD: DisableNTCredentials</span><span class="sxs-lookup"><span data-stu-id="b48e9-153">REG\_DWORD: DisableNTCredentials</span></span>

<span data-ttu-id="b48e9-154">Value: 0X0</span><span class="sxs-lookup"><span data-stu-id="b48e9-154">Value: 0x0</span></span>

</div>

<div>

## <a name="savepassword"></a><span data-ttu-id="b48e9-155">SavePassword</span><span class="sxs-lookup"><span data-stu-id="b48e9-155">SavePassword</span></span>

<span data-ttu-id="b48e9-156">Cuando un usuario inicia sesión en Lync por primera vez, se le pide al usuario que guarde su contraseña.</span><span class="sxs-lookup"><span data-stu-id="b48e9-156">When a user signs in to Lync for the first time, the user is prompted to save his or her password.</span></span> <span data-ttu-id="b48e9-157">Si se selecciona, esta opción permite que el certificado de cliente del usuario se almacene en el almacén de certificados personales y que las credenciales de Windows del usuario se almacenen en el administrador de credenciales del equipo local.</span><span class="sxs-lookup"><span data-stu-id="b48e9-157">If selected, this option allows the user’s client certificate to be stored in the personal certificate store and the user’s Windows credentials to be stored in the Credential Manager of the local computer.</span></span>

<span data-ttu-id="b48e9-158">La configuración del registro **SavePassword** debe estar deshabilitada cuando Lync está configurado para admitir la autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="b48e9-158">The **SavePassword** registry setting should be disabled when Lync is configured to support two-factor authentication.</span></span> <span data-ttu-id="b48e9-159">Para evitar que los usuarios guarden sus contraseñas, cambie la siguiente entrada del registro en la estación de trabajo local o use la plantilla administrativa de Lync para aplicarla a todos los usuarios de un grupo de servidores dado mediante la Directiva de Grupo:</span><span class="sxs-lookup"><span data-stu-id="b48e9-159">To prevent users from saving their passwords, change the following registry entry on the local workstation or use the Lync administrative template to apply to all users for a given pool using Group Policy:</span></span>

<span data-ttu-id="b48e9-160">HKEY\_actual\_software\\\\para usuarios\\de\\Microsoft\\Office 15,0 Lync</span><span class="sxs-lookup"><span data-stu-id="b48e9-160">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync</span></span>

<span data-ttu-id="b48e9-161">REG\_DWORD: SavePassword</span><span class="sxs-lookup"><span data-stu-id="b48e9-161">REG\_DWORD: SavePassword</span></span>

<span data-ttu-id="b48e9-162">Value: 0X0</span><span class="sxs-lookup"><span data-stu-id="b48e9-162">Value: 0x0</span></span>

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a><span data-ttu-id="b48e9-163">Reproducción de tokens 2,0 de AD FS</span><span class="sxs-lookup"><span data-stu-id="b48e9-163">AD FS 2.0 Token Replay</span></span>

<span data-ttu-id="b48e9-164">AD FS 2,0 proporciona una característica denominada detección de reproducción de tokens, por la que se pueden detectar varias solicitudes de tokens que usan el mismo token y, a continuación, descartarse.</span><span class="sxs-lookup"><span data-stu-id="b48e9-164">AD FS 2.0 provides a feature referred to as token replay detection, by which multiple token requests using the same token can be detected and then discarded.</span></span> <span data-ttu-id="b48e9-165">Si esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación tanto en el perfil de WS-Federation Passive como en el perfil de SAML WebSSO asegurándose de que el mismo token no se use nunca más de una vez.</span><span class="sxs-lookup"><span data-stu-id="b48e9-165">When this feature is enabled, token replay detection protects the integrity of authentication requests in both the WS-Federation passive profile and the SAML WebSSO profile by making sure that the same token is never used more than once.</span></span>

<span data-ttu-id="b48e9-166">Esta característica debe estar habilitada en situaciones en las que la seguridad es una preocupación muy importante, como cuando se usan quioscos.</span><span class="sxs-lookup"><span data-stu-id="b48e9-166">This feature should be enabled in situations where security is a very high concern such as when using kiosks.</span></span> <span data-ttu-id="b48e9-167">Para obtener más información acerca de la detección de reproducción de tokens, consulte Best Practices for Secure Planning and [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)Deployment of AD FS 2,0 en.</span><span class="sxs-lookup"><span data-stu-id="b48e9-167">For more information about token replay detection, see Best Practices for Secure Planning and Deployment of AD FS 2.0 at [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).</span></span>

</div>

<div>

## <a name="external-user-access"></a><span data-ttu-id="b48e9-168">Acceso de usuarios externos</span><span class="sxs-lookup"><span data-stu-id="b48e9-168">External User Access</span></span>

<span data-ttu-id="b48e9-169">En estos temas no se incluye la configuración de un proxy de AD FS o proxy inverso para admitir la autenticación de dos factores de Lync desde redes externas.</span><span class="sxs-lookup"><span data-stu-id="b48e9-169">Configuring an AD FS Proxy or Reverse Proxy to support Lync two-factor authentication from external networks is not covered in these topics.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

