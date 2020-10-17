---
title: 'Lync Server 2013: migración de usuarios a almacén de contactos unificado'
description: 'Lync Server 2013: migrar usuarios a almacén de contactos unificado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migrate users to unified contact store
ms:assetid: 215a8ec1-d63e-4fdf-b73d-75aeb9dddb43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204737(v=OCS.15)
ms:contentKeyID: 48183600
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e9ee9850cc723ae132f15d7c0c6b3769e1240ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568596"
---
# <a name="migrate-users-to-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="86cf8-103">Migrar usuarios a almacén de contactos unificados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86cf8-103">Migrate users to unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86cf8-104">_**Última modificación del tema:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="86cf8-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="86cf8-105">Los contactos de un usuario se migran automáticamente al servidor Exchange 2013 cuando el usuario:</span><span class="sxs-lookup"><span data-stu-id="86cf8-105">A user's contacts are automatically migrated to the Exchange 2013 server when the user:</span></span>

  - <span data-ttu-id="86cf8-106">Tiene asignado una directiva de servicios del usuario que tiene UcsAllowed configurado en True.</span><span class="sxs-lookup"><span data-stu-id="86cf8-106">Has been assigned a user services policy that has UcsAllowed set to True.</span></span>

  - <span data-ttu-id="86cf8-107">Se ha aprovisionado con un buzón de Exchange 2013 y ha iniciado sesión en el buzón al menos una vez.</span><span class="sxs-lookup"><span data-stu-id="86cf8-107">Has been provisioned with an Exchange 2013 mailbox and has signed into the mailbox at least once.</span></span>

  - <span data-ttu-id="86cf8-108">Inicia sesión con un cliente enriquecido de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="86cf8-108">Logs in by using a Lync 2013 rich client.</span></span>

<span data-ttu-id="86cf8-109">Si el usuario inicia sesión con un cliente de Lync 2010 o anterior, o si el usuario no está conectado a un servidor de Exchange 2013, se ignorará la Directiva de servicios de usuario y los contactos del usuario permanecerán en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="86cf8-109">If the user logs in with a Lync 2010 or earlier client, or if the user is not connected to an Exchange 2013 server, the user services policy is ignored and the user's contacts remain in Lync Server.</span></span>

<span data-ttu-id="86cf8-110">Puede determinar si se han migrado los contactos de un usuario usando uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="86cf8-110">You can determine whether a user's contacts have been migrated by using either of the following methods:</span></span>

  - <span data-ttu-id="86cf8-111">Compruebe la siguiente clave del registro en el equipo cliente:</span><span class="sxs-lookup"><span data-stu-id="86cf8-111">Check the following registry key on the client computer:</span></span>
    
    <span data-ttu-id="86cf8-112">HKEY \_ actual \_ software para usuarios de \\ \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ \<SIP URL\> \\ UCS</span><span class="sxs-lookup"><span data-stu-id="86cf8-112">HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\\<SIP URL\>\\UCS</span></span>
    
    <span data-ttu-id="86cf8-113">Si los contactos del usuario se almacenan en Exchange 2013, esta clave contiene un valor de en inucsmode con un valor de 2165.</span><span class="sxs-lookup"><span data-stu-id="86cf8-113">If the user's contacts are stored in Exchange 2013, this key contains a value of InUCSMode with a value of 2165.</span></span>

  - <span data-ttu-id="86cf8-114">Ejecute el cmdlet **Test-CsUnifiedContactStore**.</span><span class="sxs-lookup"><span data-stu-id="86cf8-114">Run the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="86cf8-115">En la línea de comandos del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="86cf8-115">At the Lync Server Management Shell command line, type:</span></span>
    
        Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
    
    <span data-ttu-id="86cf8-116">Si el cmdlet **Test-CsUnifiedContactStore** se lleva a cabo con éxito, quiere decir que los contactos del usuario se han migrado al almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="86cf8-116">If **Test-CsUnifiedContactStore** succeeds, the user's contacts were migrated to unified contact store.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

