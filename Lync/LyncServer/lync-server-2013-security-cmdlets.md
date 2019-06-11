---
title: 'Lync Server 2013: cmdlets de seguridad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31ede87f55754528fc7164c6d7d828eaada662e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-cmdlets-in-lync-server-2013"></a><span data-ttu-id="27e1a-102">Cmdlets de seguridad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="27e1a-102">Security cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27e1a-103">_**Última modificación del tema:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="27e1a-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="27e1a-104">Los cmdlets de seguridad incluidos en Microsoft Lync Server 2013 se usan principalmente para administrar la autenticación y los permisos y derechos de usuario.</span><span class="sxs-lookup"><span data-stu-id="27e1a-104">The security cmdlets included in Microsoft Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="27e1a-105">Hay una gran variedad de cmdlets para administrar la autenticación, por ejemplo cmdlets para certificado y autenticación del PIN.</span><span class="sxs-lookup"><span data-stu-id="27e1a-105">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="27e1a-106">Además, varios cmdlets permiten usar la nueva característica de control de acceso basado en roles (RBAC) para delegar el control administrativo de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27e1a-106">In addition, a number of cmdlets enable you to use the new role-based access control (RBAC) feature to delegate administrative control of Lync Server.</span></span>

<div>

## <a name="security-cmdlets"></a><span data-ttu-id="27e1a-107">Cmdlets de seguridad</span><span class="sxs-lookup"><span data-stu-id="27e1a-107">Security Cmdlets</span></span>

<span data-ttu-id="27e1a-108">Muchas de las tareas de administración que se aplican a la configuración de seguridad se pueden realizar en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="27e1a-108">Many management tasks that apply to security settings can be performed from the Lync Server Control Panel.</span></span> <span data-ttu-id="27e1a-109">Una excepción importante son los cmdlets de permisos de usuario.</span><span class="sxs-lookup"><span data-stu-id="27e1a-109">One major exception is the user permission cmdlets.</span></span> <span data-ttu-id="27e1a-110">Sin embargo, todas las tareas de administración de seguridad se pueden realizar con cmdlets desde el shell de administración de Lync Server o desde una secuencia de comandos; el uso de una secuencia de comandos le permite automatizar determinadas tareas.</span><span class="sxs-lookup"><span data-stu-id="27e1a-110">However, all security management tasks can be performed using cmdlets from the Lync Server Management Shell or from within a script; using a script enables you to automate certain tasks.</span></span> <span data-ttu-id="27e1a-111">A continuación se muestra una lista de cmdlets que se relacionan directamente con la administración de la configuración de seguridad:</span><span class="sxs-lookup"><span data-stu-id="27e1a-111">The following is a list of cmdlets that relate directly to managing security settings:</span></span>

<span data-ttu-id="27e1a-112">**[Cmdlets de certificados y autenticación en Lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="27e1a-112">**[Certificate and authentication cmdlets in Lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-113">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-113">[Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-114">[Importar-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-114">[Import-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-115">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-115">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-116">[Solicitud-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-116">[Request-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-117">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-117">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-118">[Prueba-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-118">[Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-119">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-119">[Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-120">[REVOKE-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-120">[Revoke-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-121">[Bloquear: CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-121">[Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-122">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-122">[Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-123">[Desbloquear: CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-123">[Unlock-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-124">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-124">[Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-125">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-125">[New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-126">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-126">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-127">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-127">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-128">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-128">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-129">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-129">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-130">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-130">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-131">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-131">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-132">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-132">[Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-133">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-133">[Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-134">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-134">[New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-135">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-135">[Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-136">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-136">[Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-137">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-137">[Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-138">[Nuevo: CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-138">[New-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-139">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-139">[Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-140">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-140">[Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-141">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-141">[Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-142">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-142">[New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-143">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-143">[Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-144">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-144">[Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))</span></span>

<span data-ttu-id="27e1a-145">**[Cmdlets de permisos y derechos de usuario en Lync Server 2013](lync-server-2013-user-rights-and-permissions-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="27e1a-145">**[User rights and permissions cmdlets in Lync Server 2013](lync-server-2013-user-rights-and-permissions-cmdlets.md)**</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-146">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-146">[Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-147">[Nuevo: CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-147">[New-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-148">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-148">[Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-149">[Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-149">[Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-150">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-150">[Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-151">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-151">[Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-152">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-152">[Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-153">[REVOKE-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-153">[Revoke-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-154">[Prueba-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-154">[Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="27e1a-155">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-155">[Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-156">[REVOKE-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-156">[Revoke-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="27e1a-157">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-157">[Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))</span></span>

<span data-ttu-id="27e1a-158">**[Cmdlets de interoperabilidad en Lync Server 2013](lync-server-2013-interoperability-cmdlets.md)**</span><span class="sxs-lookup"><span data-stu-id="27e1a-158">**[Interoperability cmdlets in Lync Server 2013](lync-server-2013-interoperability-cmdlets.md)**</span></span>

  - <span data-ttu-id="27e1a-159">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-159">[Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))</span></span>

  - <span data-ttu-id="27e1a-160">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-160">[Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="27e1a-161">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-161">[Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))</span></span>

  - <span data-ttu-id="27e1a-162">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-162">[New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))</span></span>

  - <span data-ttu-id="27e1a-163">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-163">[Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))</span></span>

  - <span data-ttu-id="27e1a-164">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-164">[Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="27e1a-165">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-165">[Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))</span></span>

  - <span data-ttu-id="27e1a-166">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-166">[New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))</span></span>

  - <span data-ttu-id="27e1a-167">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-167">[Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))</span></span>

  - <span data-ttu-id="27e1a-168">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="27e1a-168">[Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27e1a-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="27e1a-169">See Also</span></span>


[<span data-ttu-id="27e1a-170">Blog de Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="27e1a-170">Lync Server PowerShell Blog</span></span>](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

