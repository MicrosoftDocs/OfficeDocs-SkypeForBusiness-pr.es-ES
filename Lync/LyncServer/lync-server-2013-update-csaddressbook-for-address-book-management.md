---
title: 'Lync Server 2013: actualización-CsAddressBook para la administración de libretas de direcciones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Update-CsAddressBook for Address Book management
ms:assetid: 0ffd2ef8-201c-44aa-8c64-1c7b0eaa7d48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429695(v=OCS.15)
ms:contentKeyID: 48183428
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22923d0227c75ee6f2055d4a2ac350a6df6b37bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-csaddressbook-for-address-book-management-in-lync-server-2013"></a><span data-ttu-id="8a220-102">Actualización-CsAddressBook para la administración de libretas de direcciones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a220-102">Update-CsAddressBook for Address Book management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a220-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8a220-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8a220-104">¿Quién puede ejecutar este cmdlet? de forma predeterminada, los miembros de los siguientes grupos tienen autorización para ejecutar el cmdlet Update-CsAddressBook localmente: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8a220-104">Who can run this cmdlet: By default, members of the following groups are authorized to run the Update-CsAddressBook cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span> <span data-ttu-id="8a220-105">Para devolver una lista de todas las funciones de control de acceso basado en roles (RBAC) a las que se ha asignado este cmdlet (incluidos los roles RBAC que haya creado usted mismo), ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8a220-105">To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Update-CsAddressBook"}

<span data-ttu-id="8a220-106">El cmdlet Update-CsAddressBook reemplaza el comando ABserver **. exe – syncNow** de Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="8a220-106">The Update-CsAddressBook cmdlet replaces the **abserver.exe –syncNow** command from Office Communications Server.</span></span> <span data-ttu-id="8a220-107">El propósito del cmdlet es iniciar una sincronización inmediatamente en lugar de esperar la hora programada.</span><span class="sxs-lookup"><span data-stu-id="8a220-107">The cmdlet’s purpose is to initiate a synchronization immediately rather than waiting for the scheduled time.</span></span> <span data-ttu-id="8a220-108">El primer comando de ejemplo actualiza todas las libretas de direcciones de la organización.</span><span class="sxs-lookup"><span data-stu-id="8a220-108">The first example command updates all Address Books in the organization.</span></span> <span data-ttu-id="8a220-109">La segunda solo actualiza la libreta de direcciones asociada al servidor definido.</span><span class="sxs-lookup"><span data-stu-id="8a220-109">The second updates only the Address Book associated with the defined server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a220-110">En Lync Server 2013, el replicador de usuarios de Lync Server atenderá los cambios de Active Directory y actualizará la base de datos de usuarios de Lync Server en función de un intervalo configurado.</span><span class="sxs-lookup"><span data-stu-id="8a220-110">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="8a220-111">El replicador de usuarios de Lync Server también propagará los cambios a la base de datos de RTCab rápidamente sin que el Administrador tenga que ejecutar Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="8a220-111">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="8a220-112">Los administradores solo tendrán que ejecutar Update-CSAddressBook si está habilitada la descarga del archivo de la libreta de direcciones.</span><span class="sxs-lookup"><span data-stu-id="8a220-112">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>



</div>

<span data-ttu-id="8a220-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a220-113">For example:</span></span>

   ```
    Update-CsAddressBook
   ```

   ```
    Update-CsAddressBook -Fqdn atl-abs-001.contoso.com
   ```

<div>

## <a name="see-also"></a><span data-ttu-id="8a220-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a220-114">See Also</span></span>


[<span data-ttu-id="8a220-115">Update-CsAddressBook</span><span class="sxs-lookup"><span data-stu-id="8a220-115">Update-CsAddressBook</span></span>](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

