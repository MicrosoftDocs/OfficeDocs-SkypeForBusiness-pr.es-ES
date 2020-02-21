---
title: 'Lync Server 2013: configurar el entorno para el portal web administrativo del sistema Lync Room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5198416e3c06dfd83cf7d1cf5bf3c6002ebe72ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195483"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="8d701-102">Configuración del entorno de Lync Server 2013 para el portal web administrativo del sistema Lync Room</span><span class="sxs-lookup"><span data-stu-id="8d701-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d701-103">_**Última modificación del tema:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="8d701-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="8d701-104">Para usar el portal web administrativo de Lync Room System (LRS), tendrá que instalar o configurar los siguientes requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="8d701-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8d701-105">Si el servidor está configurado con autenticación Kerberos y NTLM, y LRS se está ejecutando en un equipo que no está unido al dominio, se producirá un error en la autenticación Kerberos y el usuario no verá el estado de LRS en el portal administrativo.</span><span class="sxs-lookup"><span data-stu-id="8d701-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="8d701-106">Para resolver este problema, configure el servidor con autenticación NTLM o la autenticación NTLM y TLS-DSK (sin Kerberos), o bien, una el equipo LRS al dominio.</span><span class="sxs-lookup"><span data-stu-id="8d701-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="8d701-107">Instale las actualizaciones acumulativas de Lync Server 2013:2013 de julio de en la topología de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d701-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="8d701-108">Para obtener la actualización o ver lo que se incluye con ella, consulte [actualizaciones para Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span><span class="sxs-lookup"><span data-stu-id="8d701-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="8d701-109">Cree un usuario de Active Directory habilitado para SIP.</span><span class="sxs-lookup"><span data-stu-id="8d701-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="8d701-110">El portal web administrativo LRS usa estas credenciales para consultar información de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8d701-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="8d701-111">El nombre de usuario recomendado es LRSApp.</span><span class="sxs-lookup"><span data-stu-id="8d701-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="8d701-112">Cree un grupo de seguridad de Active Directory con el nombre LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="8d701-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="8d701-113">Cree el grupo con el ámbito de grupo global y el tipo de grupo como seguridad.</span><span class="sxs-lookup"><span data-stu-id="8d701-113">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="8d701-114">Los usuarios habilitados para SIP que se agreguen a este grupo tendrán autorización para ver la lista de salas y ejecutar determinados comandos, como la recopilación de registros.</span><span class="sxs-lookup"><span data-stu-id="8d701-114">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="8d701-115">Cree un grupo de seguridad de Active Directory con el nombre LRSFullAccessAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="8d701-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="8d701-116">Cree el grupo con el ámbito de grupo global y el tipo de grupo como seguridad. los usuarios habilitados para SIP que se agregan a este grupo tienen autorización para usar todas las funciones del portal de administración.</span><span class="sxs-lookup"><span data-stu-id="8d701-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="8d701-117">![Lista de grupos de administración con rol de grupo de seguridad](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "Lista de grupos de administración con rol de grupo de seguridad")</span><span class="sxs-lookup"><span data-stu-id="8d701-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="8d701-118">Agregue LRSFullAccessAdminGroup como miembro de LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="8d701-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="8d701-119">![Página de miembros de propiedades de LRSSupportAdminGroup](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "Página de miembros de propiedades de LRSSupportAdminGroup")</span><span class="sxs-lookup"><span data-stu-id="8d701-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="8d701-120">Cree un usuario de Active Directory habilitado para SIP con el nombre LRSSupport.</span><span class="sxs-lookup"><span data-stu-id="8d701-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="8d701-121">Agregue este usuario a LRSSupportAdminGroup.</span><span class="sxs-lookup"><span data-stu-id="8d701-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="8d701-122">![Página de miembros de propiedades de LRSSupportAdminGroup](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "Página de miembros de propiedades de LRSSupportAdminGroup")</span><span class="sxs-lookup"><span data-stu-id="8d701-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="8d701-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 y Visual Web Developer 2010 SP1, disponible en el centro de descarga de [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967)Microsoft en.</span><span class="sxs-lookup"><span data-stu-id="8d701-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

