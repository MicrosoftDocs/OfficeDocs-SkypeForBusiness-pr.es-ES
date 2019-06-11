---
title: 'Lync Server 2013: Revertir usuarios migrados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57462cee6c4996f0beb51290f8382a1736d3e635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a><span data-ttu-id="e7883-102">Revertir usuarios migrados en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7883-102">Roll back migrated users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7883-103">_**Última modificación del tema:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="e7883-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="e7883-104">Si necesita revertir la característica de almacenamiento de contactos unificado, revierta los contactos solo si vuelve a colocar el usuario en Exchange 2010 o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e7883-104">If you need to roll back the unified contact store feature, roll back the contacts only if you move the user back to Exchange 2010 or Lync Server 2010.</span></span> <span data-ttu-id="e7883-105">Para hacer la reversión, deshabilite la directiva del usuario y ejecute el cmdlet **Invoke-CsUcsRollback**.</span><span class="sxs-lookup"><span data-stu-id="e7883-105">To roll back, disable the policy for the user, and then run the **Invoke-CsUcsRollback** cmdlet.</span></span> <span data-ttu-id="e7883-106">Ejecutar solo **Invoke-CsUcsRollback** no es suficiente para que la reversión sea permanente, porque la migración del almacén de contactos unificado se iniciará de nuevo si la directiva no se deshabilita.</span><span class="sxs-lookup"><span data-stu-id="e7883-106">Just running **Invoke-CsUcsRollback** alone is not enough to ensure permanent rollback, because unified contact store migration will be initiated again if the policy is not disabled.</span></span> <span data-ttu-id="e7883-107">Por ejemplo, si un usuario se deshace porque Exchange 2013 se ha revertido a Exchange 2010 y, a continuación, el buzón del usuario se mueve a Exchange 2013, la migración del almacén de contactos unificado se iniciará de nuevo siete días después de la reversión, siempre que el almacén de contactos unificado aún está habilitado para el usuario en la Directiva de servicios de usuario.</span><span class="sxs-lookup"><span data-stu-id="e7883-107">For example, if a user is rolled back because Exchange 2013 is rolled back to Exchange 2010, and then the user’s mailbox is moved to Exchange 2013, the unified contact store migration will be initiated again seven days after the rollback, as long as unified contact store is still enabled for the user in the user services policy.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7883-108">El cmdlet <STRONG>Move-CsUser</STRONG> revierte automáticamente el almacén de contactos del usuario de Exchange 2013 a Lync Server 2013 en las situaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="e7883-108">The <STRONG>Move-CsUser</STRONG> cmdlet automatically rolls back the user's contact store from Exchange 2013 to Lync Server 2013 in the following situations:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e7883-109">Cuando se mueven usuarios de Lync Server 2013 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e7883-109">When users are moved from Lync Server 2013 to Lync Server 2010.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7883-110">Cuando se migran usuarios cruzados, como cuando un usuario se mueve de Lync Online a Lync Server 2013 local, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="e7883-110">When users are migrated cross premises, such as when a user is moved from Lync Online to Lync Server 2013 on-premises, or vice versa.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7883-p102">La importación de datos del almacén de contactos unificado desde una base de datos de copia de seguridad puede dañar los datos del almacén de contactos unificado y del usuario si el modo de almacén de contactos unificado cambia entre la exportación y la importación. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7883-p102">Importing unified contact store data from a backup database can cause unified contact store data and user data to become corrupted if the unified contact store mode changed between the export and the import. For example:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="e7883-113">Si exporta listas de contactos antes de migrar los contactos de los usuarios a Exchange 2013 y, después de la migración, importar los mismos datos, se dañarán los datos del almacén de contactos unificado y las listas de contactos.</span><span class="sxs-lookup"><span data-stu-id="e7883-113">If you export contact lists before the users' contacts are migrated to Exchange 2013 and then, after the migration, import the same data, the unified contact store data and contact lists will be corrupted.</span></span></P>
> <LI>
> <P><span data-ttu-id="e7883-114">Si exporta UserData después de migrar usuarios a Exchange 2013, revierte la migración y, por algún motivo, importa los datos de después de la migración, los datos del almacén de contactos unificados y las listas de contactos se dañan.</span><span class="sxs-lookup"><span data-stu-id="e7883-114">If you export userdata after you migrate users to Exchange 2013, roll back the migration, and then for some reason you import the data from after the migration, the unified contact store data and contact lists will be corrupted.</span></span></P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e7883-115">Antes de mover un buzón de Exchange de Exchange 2013 a Exchange 2010, el administrador de Exchange debe asegurarse de que el administrador de Lync Server haya revertido primero los contactos de usuario de Lync Server de Exchange 2013 a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7883-115">Before you move an Exchange mailbox from Exchange 2013 to Exchange 2010, the Exchange administrator must make sure that the Lync Server administrator has first rolled back the Lync Server user contacts from Exchange 2013 to Lync Server.</span></span> <span data-ttu-id="e7883-116">Para deshacer los contactos de la tienda de contactos unificada a Lync Server, consulte el procedimiento "para revertir contactos de almacenamiento de contactos Unificado de Exchange 2013 a Lync Server 2013", más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="e7883-116">To roll back unified contact store contacts to Lync Server, see procedure "To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013," later in this section.</span></span>



</div>

<span data-ttu-id="e7883-117">El procedimiento siguiente describe cómo revertir los contactos del usuario.</span><span class="sxs-lookup"><span data-stu-id="e7883-117">The following procedure describes how to roll back user contacts.</span></span> <span data-ttu-id="e7883-118">Si usa el cmdlet **Move-CsUser** para mover usuarios entre lync Server 2013 y lync Server 2010, puede omitir estos pasos porque el cmdlet **Move-CsUser** automáticamente deshace unifed almacén de contactos cuando mueve usuarios de Lync Server 2013 a Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e7883-118">If you use the **Move-CsUser** cmdlet to move users between Lync Server 2013 and Lync Server 2010, you can skip these steps because the **Move-CsUser** cmdlet automatically rolls back unifed contact store when it moves users from Lync Server 2013 to Lync Server 2010.</span></span> <span data-ttu-id="e7883-119">**Mover-CsUser** no deshabilita la Directiva de almacén de contactos unificado, por lo que la migración al almacén de contactos unificado se repetirá si el usuario se vuelve a mover a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7883-119">**Move-CsUser** does not disable unified contact store policy, so the migration to unified contact store will recur if the user is moved back to Lync Server 2013.</span></span>

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a><span data-ttu-id="e7883-120">Para deshacer los contactos de usuario de Lync Server 2013 a Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="e7883-120">To roll back user contacts from Lync Server 2013 to Lync Server 2010</span></span>

1.  <span data-ttu-id="e7883-121">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7883-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7883-122">Deshabilite el almacén de contactos unificado para que los usuarios se deshagan para que no se vuelvan a migrar después de la reversión.</span><span class="sxs-lookup"><span data-stu-id="e7883-122">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="e7883-123">(Realice este paso solo si desea asegurarse de que los usuarios no volverán a migrar en el futuro). Para deshabilitar el almacén de contactos unificado para usuarios individuales, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="e7883-123">(Perform this step only if you want to make sure that users will not remigrate in the future.) To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="e7883-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7883-124">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="e7883-125">Antes de mover un usuario de Lync Server 2013 a Lync Server 2010, revertir la lista de conocidos para los usuarios especificados en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7883-125">Before moving a user from Lync Server 2013 to Lync Server 2010, roll back the Buddy List for the specified users on Lync Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7883-126">Si se omite este paso, se perderá la lista de conocidos.</span><span class="sxs-lookup"><span data-stu-id="e7883-126">If this step is omitted, the Buddy List will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="e7883-127">Revertir a los usuarios especificados.</span><span class="sxs-lookup"><span data-stu-id="e7883-127">Roll back the specified users.</span></span> <span data-ttu-id="e7883-128">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7883-128">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="e7883-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7883-129">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7883-130">No se recomienda usar la opción – Force para forzar la reversión.</span><span class="sxs-lookup"><span data-stu-id="e7883-130">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="e7883-131">Si usa esta opción, los contactos de los usuarios se perderán.</span><span class="sxs-lookup"><span data-stu-id="e7883-131">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a><span data-ttu-id="e7883-132">Para deshacer los contactos de almacén de contactos unificados de Exchange 2013 a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7883-132">To roll back unified contact store contacts from Exchange 2013 to Lync Server 2013</span></span>

1.  <span data-ttu-id="e7883-133">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e7883-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e7883-134">Deshabilite el almacén de contactos unificado para que los usuarios se deshagan para que no se vuelvan a migrar después de la reversión.</span><span class="sxs-lookup"><span data-stu-id="e7883-134">Disable unified contact store for the users to be rolled back so that they will not be remigrated after rollback.</span></span> <span data-ttu-id="e7883-135">Para deshabilitar el almacén de contactos unificado para usuarios individuales, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="e7883-135">To disable unified contact store for individual users, at the command line, type:</span></span>
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    <span data-ttu-id="e7883-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7883-136">For example:</span></span>
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  <span data-ttu-id="e7883-137">Revertir a los usuarios especificados.</span><span class="sxs-lookup"><span data-stu-id="e7883-137">Roll back the specified users.</span></span> <span data-ttu-id="e7883-138">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7883-138">At the command line, type:</span></span>
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    <span data-ttu-id="e7883-139">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e7883-139">For example:</span></span>
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e7883-140">Primero debe revertir al usuario de Lync Server y, a continuación, mover el buzón de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e7883-140">You must first roll back the Lync Server user, and then move the Exchange 2013 mailbox.</span></span> <span data-ttu-id="e7883-141">El administrador de Exchange no pudo revertir a Exchange hasta que se complete la reversión de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e7883-141">The Exchange administrator is blocked from rolling back Exchange until the Lync Server rollback is complete.</span></span> <span data-ttu-id="e7883-142">No se recomienda usar la opción – Force para forzar la reversión.</span><span class="sxs-lookup"><span data-stu-id="e7883-142">We do not recommend using the –Force option to force the rollback.</span></span> <span data-ttu-id="e7883-143">Si usa esta opción, los contactos de los usuarios se perderán.</span><span class="sxs-lookup"><span data-stu-id="e7883-143">If you use this option, the users' contacts will be lost.</span></span>

    
    </div>

4.  <span data-ttu-id="e7883-144">Después de revertir al usuario a Lync Server, el administrador de Exchange puede revertir al usuario de Exchange de Exchange 2013 a Exchange 2010.</span><span class="sxs-lookup"><span data-stu-id="e7883-144">After you roll back the user to Lync Server, the Exchange administrator can roll back the Exchange user from Exchange 2013 to Exchange 2010.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

