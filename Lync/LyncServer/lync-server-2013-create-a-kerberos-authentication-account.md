---
title: 'Lync Server 2013: crear una cuenta de autenticación Kerberos'
description: 'Lync Server 2013: crear una cuenta de autenticación Kerberos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f8e87a8ffcc95af4a44e516ac4e1f4d635d737
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542136"
---
# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="5f17c-103">Crear una cuenta de autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f17c-103">Create a Kerberos authentication account in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f17c-104">_**Última modificación del tema:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="5f17c-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="5f17c-105">Para completar correctamente este procedimiento, debe haber iniciado sesión en el servidor o dominio de forma mínima como miembro del grupo administradores del dominio.</span><span class="sxs-lookup"><span data-stu-id="5f17c-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="5f17c-106">Puede crear cuentas de autenticación Kerberos para cada uno de los sitios, o bien crear una sola cuenta de autenticación Kerberos y usarla para todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="5f17c-106">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="5f17c-107">Use los cmdlets de Windows PowerShell para crear y administrar las cuentas, incluida la identificación de las cuentas asignadas a cada sitio.</span><span class="sxs-lookup"><span data-stu-id="5f17c-107">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="5f17c-108">El generador de topologías y el panel de control de Lync Server 2013 no muestran cuentas de autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="5f17c-108">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="5f17c-109">Use el siguiente procedimiento para crear la(s) cuenta(s) de usuario que se usará(n) para la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="5f17c-109">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="5f17c-110">Para crear una cuenta Kerberos</span><span class="sxs-lookup"><span data-stu-id="5f17c-110">To create a Kerberos account</span></span>

1.  <span data-ttu-id="5f17c-111">Como miembro del grupo administradores de dominio, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="5f17c-111">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="5f17c-112">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5f17c-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5f17c-113">Desde la línea de comandos, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5f17c-113">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="5f17c-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5f17c-114">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="5f17c-115">Confirme que se ha creado el objeto Equipo al abrir el usuario y los equipos de Active Directory, expanda el contenedor **Usuarios** y, a continuación, confirme que el objeto Equipo de la cuenta de usuario se encuentra en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="5f17c-115">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

