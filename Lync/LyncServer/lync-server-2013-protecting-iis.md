---
title: 'Lync Server 2013: protección de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Protecting IIS in Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518332(v=OCS.15)
ms:contentKeyID: 62625492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aae84d208df1d7c2945fee641b243bf7110902c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513197"
---
# <a name="protecting-iis-in-lync-server-2013"></a><span data-ttu-id="c53a9-102">Proteger IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c53a9-102">Protecting IIS in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c53a9-103">_**Última modificación del tema:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="c53a9-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="c53a9-104">En Microsoft Office Communications Server 2007 y Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) se ejecutó con una cuenta de usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="c53a9-104">In Microsoft Office Communications Server 2007 and Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) ran under a standard user account.</span></span> <span data-ttu-id="c53a9-105">Esto podía provocar problemas: si la contraseña expiraba, se podían perder los servicios web, un problema que a menudo era difícil de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="c53a9-105">This had the potential to cause issues: if that password expired you could lose your Web Services, an issue that was often difficult to diagnose.</span></span> <span data-ttu-id="c53a9-106">Para evitar un problema de expiración de contraseñas, Microsoft Lync Server 2013 permite crear una cuenta de equipo (para un equipo que no existe realmente) que puede servir como entidad de autenticación para todos los equipos de un sitio que ejecutan IIS.</span><span class="sxs-lookup"><span data-stu-id="c53a9-106">To help avoid the issue of expiring passwords, Microsoft Lync Server 2013 enables you to create a computer account (for a computer that doesn’t actually exist) that can serve as the authentication principal for all the computers in a site that are running IIS.</span></span> <span data-ttu-id="c53a9-107">Dado que estas cuentas usan el protocolo de autenticación Kerberos, se llaman cuentas Kerberos, mientras que el nuevo proceso de autenticación se denomina autenticación web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c53a9-107">Because these accounts use the Kerberos authentication protocol, the accounts are referred to as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="c53a9-108">Esto le permite administrar todos sus servidores IIS usando una sola cuenta.</span><span class="sxs-lookup"><span data-stu-id="c53a9-108">This enables you to manage all your IIS servers by using a single account.</span></span>

<span data-ttu-id="c53a9-109">Para ejecutar los servidores con esta entidad de seguridad de autenticación, antes debe crear una cuenta de equipo usando el cmdlet New-CsKerberosAccount; a continuación, esta cuenta se asigna a uno o más sitios.</span><span class="sxs-lookup"><span data-stu-id="c53a9-109">To run your servers under this authentication principal, you must first create a computer account by using the New-CsKerberosAccount cmdlet; this account is then assigned to one or more sites.</span></span> <span data-ttu-id="c53a9-110">Una vez realizada la asignación, se habilita la asociación entre la cuenta y el sitio de Lync Server 2013 ejecutando el cmdlet Enable-CsTopology.</span><span class="sxs-lookup"><span data-stu-id="c53a9-110">After the assignment has been made, the association between the account and the Lync Server 2013 site is enabled by running the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="c53a9-111">Esta acción crea, entre otras cosas, el nombre de entidad de seguridad de servicio (SPN) necesario en los servicios de dominio de Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c53a9-111">Among other things, this creates the required service principal name (SPN) in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="c53a9-112">Los SPN ofrecen un modo para que las aplicaciones cliente ubiquen un servicio concreto.</span><span class="sxs-lookup"><span data-stu-id="c53a9-112">SPNs provide a way for client applications to locate a particular service.</span></span> <span data-ttu-id="c53a9-113">Para obtener más información, consulte [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="c53a9-113">For details, see [New-CsKerberosAccount](https://docs.microsoft.com/powershell/module/skype/New-CsKerberosAccount) in the Operations documentation.</span></span>

<div>

## <a name="best-practices"></a><span data-ttu-id="c53a9-114">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="c53a9-114">Best Practices</span></span>

<span data-ttu-id="c53a9-p103">Para contribuir a mejorar la seguridad de IIS, le recomendamos que implemente una cuenta Kerberos para IIS. Si no implementa una cuenta Kerberos, IIS se ejecutará con una cuenta de usuario estándar.</span><span class="sxs-lookup"><span data-stu-id="c53a9-p103">To help increase security of IIS, we recommend that you implement a Kerberos account for IIS. If you do not implement a Kerberos account, IIS runs under a standard user account.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

