---
title: 'Lync Server 2013: configuración de Lync Server para usar el almacén de contactos unificado'
description: 'Lync Server 2013: configurar Lync Server para usar el almacén de contactos unificado.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6905d2e393fec36fe5db3e40ee20087c0cca0991
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570796"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a><span data-ttu-id="c3c5b-103">Configuración de Microsoft Lync Server 2013 para usar el almacén de contactos unificados</span><span class="sxs-lookup"><span data-stu-id="c3c5b-103">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3c5b-104">_**Última modificación del tema:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c3c5b-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c3c5b-105">El almacén de contactos unificados permite a los usuarios mantener una única lista de contactos y hacer que dichos contactos estén disponibles en varias aplicaciones, como Microsoft Lync 2013, Microsoft Outlook 2013 y Microsoft Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-105">The unified contact store enables users to maintain a single contacts list and then have those contacts available in multiple applications, including Microsoft Lync 2013, Microsoft Outlook 2013, and Microsoft Outlook Web App 2013.</span></span> <span data-ttu-id="c3c5b-106">Cuando habilita el almacén de contactos unificado para un usuario, los contactos de ese usuario no se almacenan en Microsoft Lync Server 2013 y, a continuación, se recuperan mediante el protocolo SIP.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-106">When you enable the unified contact store for a user that user's contacts are not stored in Microsoft Lync Server 2013 and then retrieved using the SIP protocol.</span></span> <span data-ttu-id="c3c5b-107">En su lugar, sus contactos se almacenan en Microsoft Exchange Server 2013 y se recuperan mediante los servicios Web de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-107">Instead, his or her contacts are stored in Microsoft Exchange Server 2013 and are retrieved by using Exchange Web Services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3c5b-108">Técnicamente, la información de contacto se almacena en un par de carpetas que se encuentran en el buzón de Exchange 2013 del usuario.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-108">Technically, contact information is stored in a pair of folders found in the user's Exchange 2013 mailbox.</span></span> <span data-ttu-id="c3c5b-109">Los propios contactos se almacenan en una carpeta llamada contactos de Lync que es visible para los usuarios finales; los metadatos de los contactos se almacenan en una subcarpeta que no es visible para los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-109">The contacts themselves are stored in a folder named Lync Contacts which is visible to end users; metadata about the contacts are stored in a subfolder that is not visible to end users.</span></span>



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a><span data-ttu-id="c3c5b-110">Habilitar el almacén de contactos unificados de un usuario</span><span class="sxs-lookup"><span data-stu-id="c3c5b-110">Enabling the Unified Contact Store for a User</span></span>

<span data-ttu-id="c3c5b-111">Si ya ha configurado la autenticación de servidor a servidor entre Lync Server 2013 y Exchange 2013, también habrá habilitado el uso del almacén de contactos unificados; no se necesita ninguna configuración adicional del servidor.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-111">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you have also enabled the use of the unified contact store; no additional server configuration is required.</span></span> <span data-ttu-id="c3c5b-112">Sin embargo, se requiere la configuración de cuentas de usuario adicionales para mover los contactos de un usuario al almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-112">However, additional user account configuration is required in order to move a user's contacts into the unified contact store.</span></span> <span data-ttu-id="c3c5b-113">De forma predeterminada, los contactos de usuario se conservan en Lync Server y no en el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-113">By default, user contacts are kept in Lync Server and not in the unified contact store.</span></span>

<span data-ttu-id="c3c5b-114">El acceso al almacén de contactos unificado se administra mediante las directivas de servicios de usuario de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-114">Access to the unified contact store is managed by using Lync Server user services policies.</span></span> <span data-ttu-id="c3c5b-115">Las directivas de servidor de usuario solo tienen una propiedad (Ucsallowed configurado); Esta propiedad se usa para determinar la ubicación en la que se almacenan los contactos de un usuario.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-115">User server policies have only a single property (UcsAllowed); this property is used to determine the location where a user's contacts are stored.</span></span> <span data-ttu-id="c3c5b-116">Si un usuario se administra mediante una directiva de servicios de usuario donde Ucsallowed configurado se ha establecido en true ($True), los contactos del usuario se almacenarán en el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-116">If a user is managed by a user services policy where UcsAllowed has been set to True ($True) then the user's contacts will be stored in the unified contact store.</span></span> <span data-ttu-id="c3c5b-117">Si el usuario se administra mediante una directiva de servicios de usuario donde Ucsallowed configurado se ha establecido en false ($False), sus contactos se almacenarán en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-117">If the user is managed by a user services policy where UcsAllowed has been set to False ($False) then his or her contacts will be stored in Lync Server.</span></span>

<span data-ttu-id="c3c5b-118">Al instalar Lync Server 2013, también se instala una única directiva de servicios de usuario (configurada en el ámbito global).</span><span class="sxs-lookup"><span data-stu-id="c3c5b-118">When you install Lync Server 2013 a single user services policy (configured at the global scope) is installed as well.</span></span> <span data-ttu-id="c3c5b-119">El valor Ucsallowed configurado de esta Directiva se establece en true, lo que significa que, de forma predeterminada, los contactos de usuario se almacenarán en el almacén de contactos unificados (suponiendo que se ha implementado y configurado).</span><span class="sxs-lookup"><span data-stu-id="c3c5b-119">The UcsAllowed value in this policy is set to True, meaning that, by default, user contacts will be stored in the unified contact store (assuming this has been deployed and configured).</span></span> <span data-ttu-id="c3c5b-120">Si desea migrar todos los contactos de los usuarios al almacén de contactos unificado, no tiene que hacer nada.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-120">If you want to migrate all of your user contacts to the unified contact store you do not have to do anything at all.</span></span>

<span data-ttu-id="c3c5b-121">Si prefiere no migrar todos los contactos al almacén de contactos unificado, puede deshabilitar el almacén de contactos unificados para todos los usuarios si establece la propiedad Ucsallowed configurado de la directiva global en false:</span><span class="sxs-lookup"><span data-stu-id="c3c5b-121">If you would prefer not to migrate all your contacts to the unified contact store you can disable the unified contact store for all users by setting the UcsAllowed property in the global policy to False:</span></span>

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

<span data-ttu-id="c3c5b-122">Después de deshabilitar el almacén de contactos unificados en la directiva global, puede crear una directiva por usuario que permita el uso del almacén de contactos unificados; Esto le permite a algunos usuarios mantener sus contactos en el almacén de contactos unificado mientras otros usuarios continúan manteniendo sus contactos en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-122">After you have disabled the unified contact store in the global policy you can then create a per-user policy that enables the use of the unified contact store; this allows you to have some users keep their contacts in the unified contact store while other users continue to keep their contacts in Lync Server.</span></span> <span data-ttu-id="c3c5b-123">Para crear una directiva de servicios de usuario por usuario se usa un comando parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3c5b-123">You can create a per-user user services policy by using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

<span data-ttu-id="c3c5b-p107">Una vez creada la directiva, hay que asignarla a los usuarios que deban tener acceso al almacén de contactos unificados. Para ello, se usan comandos parecidos a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="c3c5b-p107">After you have created the new policy you must then assign that policy to any user who should have access to the unified contact store. Per-user policies can be assigned to users by using commands similar to this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

<span data-ttu-id="c3c5b-126">Una vez que se ha asignado la Directiva, Lync Server comenzará a migrar los contactos del usuario al almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-126">After the policy has been assigned Lync Server will begin to migrate the user's contacts to the unified contact store.</span></span> <span data-ttu-id="c3c5b-127">Una vez completada la migración, el usuario tendrá sus contactos almacenados en Exchange en lugar de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-127">After migration is complete, the user will then have his or her contacts stored in Exchange rather than Lync Server.</span></span> <span data-ttu-id="c3c5b-128">Si el usuario ha iniciado sesión en Lync 2013 en el momento de completar la migración, aparecerá un cuadro de mensaje y se le pedirá que cierre sesión en Lync y que vuelva a iniciarla para finalizar el proceso.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-128">If the user happens to be logged on to Lync 2013 at the time migration completes, a message box will appear and he or she will be asked to log off of Lync and then log back on in order to finalize the process.</span></span> <span data-ttu-id="c3c5b-129">Los usuarios a los que no se haya asignado esta Directiva por usuario no tendrán sus contactos migrados al almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-129">Users who have not been assigned this per-user policy will not have their contacts migrated to the unified contact store.</span></span> <span data-ttu-id="c3c5b-130">Esto se debe a que los usuarios están siendo administrados por la directiva global y el uso del almacén de contactos unificado se ha deshabilitado en la directiva global.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-130">That’s because those users are being managed by the global policy, and use of the unified contact store has been disabled in the global policy.</span></span>

<span data-ttu-id="c3c5b-131">Puede comprobar que los contactos de un usuario se han migrado correctamente al almacén de contactos unificado ejecutando el cmdlet [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="c3c5b-131">You can verify that a user's contacts have successfully been migrated to the unified contact store by running the [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) cmdlet from within the Lync Server Management Shell:</span></span>

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="c3c5b-132">Si Test-CsUnifiedContactStore finaliza correctamente, querrá decir que los contactos del usuario sip:kenmyer@litwareinc.com se han migrado correctamente al almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-132">If Test-CsUnifiedContactStore succeeds that means that the contacts for the user sip:kenmyer@litwareinc.com have been migrated to the unified contact store.</span></span>

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a><span data-ttu-id="c3c5b-133">Revertir el almacén de datos unificados</span><span class="sxs-lookup"><span data-stu-id="c3c5b-133">Rolling Back the Unified Contact Store</span></span>

<span data-ttu-id="c3c5b-134">Si necesita quitar los contactos de un usuario del almacén de contactos unificados (por ejemplo, si el usuario necesita volver a alojarse en Microsoft Lync Server 2010 y, por lo tanto, ya no puede usar el almacén de contactos unificado), debe hacer dos cosas.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-134">If you need to remove a user's contacts from the unified contact store (for example, if the user needs to be rehomed on Microsoft Lync Server 2010 and thus can no longer use the unified contact store) you must do two things.</span></span> <span data-ttu-id="c3c5b-135">En primer lugar, debe asignar al usuario una nueva Directiva de servicios de usuario, que prohíbe almacenar contactos en el almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-135">First, you must assign the user a new user services policy, one that prohibits storing contacts in the unified contact store.</span></span> <span data-ttu-id="c3c5b-136">(Es decir, una directiva en la que la propiedad Ucsallowed configurado se ha establecido en $False). Si no tiene dicha Directiva, puede crear una con un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="c3c5b-136">(That is, a policy where the UcsAllowed property has been set to $False.) If you do not have such a policy you can create one using a command similar to this:</span></span>

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

<span data-ttu-id="c3c5b-137">Después, puede usar un comando como el siguiente para asignar esta nueva directiva por usuario (NoUnifiedContactStore):</span><span class="sxs-lookup"><span data-stu-id="c3c5b-137">You can then assign this new per-user policy (NoUnifiedContactStore) by using a command like this:</span></span>

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

<span data-ttu-id="c3c5b-138">Con el comando anterior la nueva directiva se asigna al usuario Ken Myer y, asimismo, se impide que los contactos de Ken migren al almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-138">The preceding command assigns the new policy to the user Ken Myer, and also prevents Ken's contacts from being migrated to the unified contact store.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3c5b-p110">Algunas veces, se puede lograr el mismo efecto con tan solo quitar la directiva de servicios de usuario actual que el usuario tiene asignada. Imaginemos, por ejemplo, que Ken Myer tiene una directiva de servicios de usuario por usuario que permite el uso del almacén de contactos unificados, pero la directiva global prohíbe usarlo. En tal caso, se podría quitar la directiva de servicios de usuario que Ken tiene asignada. Al hacerlo, Ken pasará automáticamente a estar administrado por la directiva global y, en consecuencia, dejará de tener acceso al almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-p110">In some cases you can achieve the same net effect by simply unassigning the user's current user services policy. For example, suppose Ken Myer has a per-user user services policy the enables the unified contact store, but your global policy prohibits the use of the unified contact store. In that case, you could unassign Ken's per-user services policy. When you do that, Ken will automatically be managed by the global policy, and thus will no longer have access to the unified contact store.</span></span><BR><span data-ttu-id="c3c5b-143">Para quitar la asignación de la directiva por usuario previamente asignada, utilice el mismo comando que antes, pero establezca el parámetro PolicyName esta vez en un valor nulo:</span><span class="sxs-lookup"><span data-stu-id="c3c5b-143">To unassign a previously-assigned per-user policy, use the same command as shown before, but this time set the PolicyName parameter to a null value:</span></span><BR><span data-ttu-id="c3c5b-144">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="c3c5b-144">Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



</div>

<span data-ttu-id="c3c5b-145">La terminología "impide que los contactos de Ken se migren al almacén de contactos unificados" es importante tener en cuenta al trabajar con el almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-145">The terminology "prevents Ken's contacts from being migrated to the unified contact store" is important to keep in mind when working with the unified contact store.</span></span> <span data-ttu-id="c3c5b-146">Simplemente asignar a Ken una nueva Directiva de servicios de usuario no moverá a sus contactos del almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-146">Simply assigning Ken a new user services policy will not move his contacts out of the unified contact store.</span></span> <span data-ttu-id="c3c5b-147">Cuando un usuario inicia sesión en Lync Server 2013, el sistema comprueba la Directiva de servicios de usuario del usuario para ver si sus contactos deben conservarse en el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-147">When a user logs on to Lync Server 2013, the system checks the user's user services policy to see whether his or her contacts should be kept in the unified contact store.</span></span> <span data-ttu-id="c3c5b-148">Si la respuesta es afirmativa (es decir, si la propiedad Ucsallowed configurado está establecida en $True), esos contactos se migrarán al almacén de contactos unificado (suponiendo que dichos contactos no se encuentren en el almacén de contactos unificado).</span><span class="sxs-lookup"><span data-stu-id="c3c5b-148">If the answer is yes (that is, if the UcsAllowed property is set to $True) then those contacts will be migrated to the unified contact store (assuming that those contacts are not already in the unified contact store).</span></span> <span data-ttu-id="c3c5b-149">Si la respuesta es no, Lync Server simplemente ignora los contactos del usuario y pasa a la siguiente tarea.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-149">If the answer is no, then Lync Server simply ignores the user's contacts and moves on to its next task.</span></span> <span data-ttu-id="c3c5b-150">Esto significa que Lync Server no moverá automáticamente los contactos de un usuario de fuera del almacén de contactos unificado, independientemente del valor de la propiedad Ucsallowed configurado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-150">That means that Lync Server will not automatically move a user's contacts from out of the unified contact store, regardless of the value of the UcsAllowed property.</span></span>

<span data-ttu-id="c3c5b-151">Eso también significa que, después de asignar al usuario una nueva Directiva de servicios de usuario, debe ejecutar el cmdlet [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) para mover los contactos del usuario fuera de Exchange 2013 y volver a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-151">That also means that, after assigning the user a new user services policy, you must then run the [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) cmdlet in order to move the user's contacts out of Exchange 2013 and back to Lync Server 2013.</span></span> <span data-ttu-id="c3c5b-152">Por ejemplo, después de asignar a Ken Myer una nueva directiva de servicios de usuario, sus contactos se pueden sacar del almacén de contactos unificados con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c3c5b-152">For example, after assigning Ken Myer a new user services policy you can then move his contacts out of the unified contact store by using the following command:</span></span>

    Invoke-CsUcsRollback -Identity "Ken Myer"

<span data-ttu-id="c3c5b-153">Si se cambia la directiva de servicios de usuario, pero no se ejecuta el cmdlet Invoke-CsUcsRollback, los contactos de Ken no se eliminarán del almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-153">If you change the user services policy but do not run the Invoke-CsUcsRollback cmdlet Ken's contacts will not be removed from the unified contact store.</span></span> <span data-ttu-id="c3c5b-154">¿Qué ocurriría si se ejecutara Invoke-CsUcsRollback sin modificar la directiva de servicios de usuario de Ken Myer?</span><span class="sxs-lookup"><span data-stu-id="c3c5b-154">What if you run Invoke-CsUcsRollback but do not change Ken Myer's user services policy?</span></span> <span data-ttu-id="c3c5b-155">Pues que los contactos de Ken se eliminarán de manera temporal del almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-155">In that case, Ken's contacts will be temporarily removed from the unified contact store.</span></span> <span data-ttu-id="c3c5b-156">El hecho de que esta eliminación sea temporal es importante.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-156">The fact that this removal is temporary is important to keep in mind.</span></span> <span data-ttu-id="c3c5b-157">Una vez que los contactos de Ken se han quitado del almacén de contactos unificado, Lync Server 2013 esperará 7 días y, a continuación, comprobará qué directiva de servicios de usuario se ha asignado a Ken.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-157">After Ken's contacts have been removed from the unified contact store, Lync Server 2013 will wait 7 days and then check to see which user services policy has been assigned to Ken.</span></span> <span data-ttu-id="c3c5b-158">Si Ken sigue teniendo asignada una directiva que permite usar el almacén de contactos unificados, sus contactos se colocarán de nuevo en dicho almacén.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-158">If Ken is still assigned a policy that enables the user of the unified contact store, then his contacts will automatically be moved back to into the contact store.</span></span> <span data-ttu-id="c3c5b-159">Para eliminar contactos del almacén de contactos unificados de manera permanente, debe cambiar la directiva de servicios de usuario y, además, ejecutar el cmdlet Invoke-CsUcsRollback.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-159">To permanently remove contacts from the unified contact store you must change the user services policy in addition to running the Invoke-CsUcsRollback cmdlet.</span></span>

<span data-ttu-id="c3c5b-160">Debido al gran número de variables que pueden afectar a la migración, es difícil calcular cuánto tiempo tardará antes de que las cuentas se migren completamente al almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-160">Due to the large number of variables that can affect migration, it is difficult to estimate how long it will take before accounts are fully migrated to the unified contact store.</span></span> <span data-ttu-id="c3c5b-161">Como regla general, sin embargo, la migración no surte efecto inmediatamente: incluso cuando se migra un número reducido de contactos, puede tardar 10 minutos o más antes de que se complete el traslado.</span><span class="sxs-lookup"><span data-stu-id="c3c5b-161">As a general rule, however, migration does not take effect immediately: even when migrating a small number of contacts it might take 10 minutes or more before the move is complete.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

