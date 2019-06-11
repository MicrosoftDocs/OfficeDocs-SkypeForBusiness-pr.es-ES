---
title: 'Lync Server 2013: Proteger IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 711adaec00e37cbd826f8aabcadc45948548c3f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="64f27-102">Proteger IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64f27-102">Protecting IIS in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64f27-103">_**Última modificación del tema:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="64f27-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="64f27-104">En Microsoft Office Communications Server 2007 y Microsoft Office Communications Server 2007 R2, servicios de Internet Information Server (IIS) se ejecutó con una cuenta de usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="64f27-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="64f27-105">Esto tenía el potencial de causar problemas: Si la contraseña ha expirado, podrías perder los servicios Web, un problema que a menudo era difícil de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="64f27-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="64f27-106">Para evitar el problema de caducidad de las contraseñas, Microsoft Lync Server 2013 le permite crear una cuenta de equipo (para un equipo que realmente no existe) que puede ser el principal de autenticación de todos los equipos de un sitio que ejecutan IIS.</span><span class="sxs-lookup"><span data-stu-id="64f27-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="64f27-107">Dado que estas cuentas usan el protocolo de autenticación Kerberos, se llaman cuentas Kerberos y el nuevo proceso de autenticación se denomina autenticación web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="64f27-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="64f27-108">Esto permite administrar todos los servidores IIS usando una única cuenta.</span><span class="sxs-lookup"><span data-stu-id="64f27-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="64f27-109">Para ejecutar los servidores en esta entidad de autenticación, primero debe crear una cuenta de equipo mediante el cmdlet New-CsKerberosAccount; a continuación, esta cuenta se asigna a uno o varios sitios.</span><span class="sxs-lookup"><span data-stu-id="64f27-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="64f27-110">Después de realizar la asignación, la asociación entre la cuenta y el sitio de Lync Server 2013 se habilita al ejecutar el cmdlet enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="64f27-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="64f27-111">Entre otras cosas, esto crea el nombre principal de servicio (SPN) necesario en servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="64f27-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="64f27-112">Los SPN ofrecen a las aplicaciones cliente una manera de ubicar un servicio en particular.</span><span class="sxs-lookup"><span data-stu-id="64f27-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="64f27-113">Para obtener más información, vea [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="64f27-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="64f27-114">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="64f27-114">Best Practices</span></span>

<span data-ttu-id="64f27-115">Para ayudar a mejorar la seguridad de IIS, recomendamos implementar una cuenta de Kerberos para IIS.</span><span class="sxs-lookup"><span data-stu-id="64f27-115">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS.</span></span> <span data-ttu-id="64f27-116">Si no implementa una cuenta de Kerberos, IIS se ejecutará con una cuenta de usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="64f27-116">If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

