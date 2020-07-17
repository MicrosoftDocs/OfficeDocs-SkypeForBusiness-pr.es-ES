---
title: Identidades, ámbitos e inquilinos en Skype empresarial online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e5217c4214e6e86ca4c1dff62410c247cf7f8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="bc741-102">Identidades, ámbitos e inquilinos en Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="bc741-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc741-103">_**Última modificación del tema:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="bc741-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="bc741-104">Muchos de los cmdlets de Windows PowerShell que se usan para administrar Skype empresarial online requieren que sea muy específico sobre el elemento que está tratando de administrar.</span><span class="sxs-lookup"><span data-stu-id="bc741-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="bc741-105">Por ejemplo, al ejecutar el cmdlet [set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , debe indicar qué usuario está tratando de administrar.</span><span class="sxs-lookup"><span data-stu-id="bc741-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="bc741-106">Esto tiene sentido.</span><span class="sxs-lookup"><span data-stu-id="bc741-106">This makes sense.</span></span> <span data-ttu-id="bc741-107">A menos que indique específicamente al cmdlet qué cuenta de usuario va a administrar, el cmdlet **set-CsUserAcp** no tiene idea de qué información de audioconferencia del usuario debe modificarse.</span><span class="sxs-lookup"><span data-stu-id="bc741-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="bc741-108">Por este motivo, cada vez que ejecute el cmdlet **set-CsUserAcp** , deberá incluir el parámetro Identity, seguido de la identidad de la cuenta de usuario que se va a modificar:</span><span class="sxs-lookup"><span data-stu-id="bc741-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="bc741-109">Si el término *identidad* siempre hacía referencia a la identidad de una cuenta de usuario, habría poca causa de confusión.</span><span class="sxs-lookup"><span data-stu-id="bc741-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="bc741-110">Cuando se trabaja con personas (usuarios, contactos, etc.), las identidades se refieren a los usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="bc741-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="bc741-111">Sin embargo, los elementos que no son cuentas de usuario también tienen identidades.</span><span class="sxs-lookup"><span data-stu-id="bc741-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="bc741-112">Cuando trabaja con componentes del servicio Skype empresarial online (directivas, opciones de configuración, etc.), el término identidad significa algo ligeramente diferente.</span><span class="sxs-lookup"><span data-stu-id="bc741-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="bc741-113">Por ejemplo, considere este comando:</span><span class="sxs-lookup"><span data-stu-id="bc741-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="bc741-114">En este caso, la identidad "global" se refiere al ámbito de las opciones de configuración de reunión.</span><span class="sxs-lookup"><span data-stu-id="bc741-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="bc741-115">*Ámbito* es un término que se usa en Skype empresarial online (y en Lync Server) para designar esferas de administración.</span><span class="sxs-lookup"><span data-stu-id="bc741-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="bc741-116">De forma predeterminada, las directivas y la configuración siempre tienen un ámbito global.</span><span class="sxs-lookup"><span data-stu-id="bc741-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="bc741-117">La primera vez que configure la cuenta de Skype empresarial online tendrá, de forma predeterminada, una colección de directivas y opciones de configuración globales: opciones de configuración de reuniones globales, una directiva de acceso externo global, un plan de marcado global, etc.</span><span class="sxs-lookup"><span data-stu-id="bc741-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="bc741-118">Estas directivas y configuraciones globales se introdujeron en Microsoft Lync Server 2010 para ayudar a garantizar que todos los usuarios y todos los componentes siempre se administrarían de alguna manera.</span><span class="sxs-lookup"><span data-stu-id="bc741-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="bc741-119">Esto no era necesariamente cierto en Microsoft Office Communicator 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="bc741-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="bc741-120">En función de cómo obtuvo acceso al sistema, es posible que acabe en un estado no administrado en gran medida (normalmente, porque no se pudo aplicar la Directiva de grupo a su cuenta de usuario).</span><span class="sxs-lookup"><span data-stu-id="bc741-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="bc741-121">Por el contrario, en Lync Server y en Skype empresarial online, no se deja nada sin administrar.</span><span class="sxs-lookup"><span data-stu-id="bc741-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="bc741-122">Esto se debe a que, en lugar de nada más, siempre se aplicará la configuración y las directivas globales.</span><span class="sxs-lookup"><span data-stu-id="bc741-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="bc741-123">¿Qué queremos decir con "en lugar de cualquier otro elemento?".</span><span class="sxs-lookup"><span data-stu-id="bc741-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="bc741-124">Bueno, en el caso de Skype empresarial online, es posible crear directivas en el ámbito de la *etiqueta*o en una esfera de administración.</span><span class="sxs-lookup"><span data-stu-id="bc741-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="bc741-125">Las directivas creadas en el ámbito de la etiqueta (también conocido como *ámbito por usuario*) tienen prioridad sobre las directivas creadas en el ámbito global.</span><span class="sxs-lookup"><span data-stu-id="bc741-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="bc741-126">Es decir, una directiva por usuario siempre tendrá prioridad sobre una directiva global.</span><span class="sxs-lookup"><span data-stu-id="bc741-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="bc741-127">Por ejemplo, puede tener dos directivas de acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="bc741-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="bc741-128">La directiva global prohíbe a los usuarios comunicarse con personas que tienen cuentas en proveedores de mensajería instantánea pública (mi), como Windows Live.</span><span class="sxs-lookup"><span data-stu-id="bc741-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="bc741-129">La Directiva por usuario, AllowPublicIMCommunication, permite la comunicación con proveedores de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="bc741-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="bc741-130">También es posible que tenga dos usuarios: Ken Myer y Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="bc741-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="bc741-131">Se ha asignado a Ken Myer la Directiva por usuario.</span><span class="sxs-lookup"><span data-stu-id="bc741-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="bc741-132">Pilar Ackerman no tiene asignada una directiva por usuario; es decir, se administra mediante la directiva global de acceso externo.</span><span class="sxs-lookup"><span data-stu-id="bc741-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="bc741-133">En la tabla siguiente se muestra qué usuario (si lo hay) se puede comunicar con los proveedores de mensajería instantánea pública:</span><span class="sxs-lookup"><span data-stu-id="bc741-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc741-134">Configuración de Directiva</span><span class="sxs-lookup"><span data-stu-id="bc741-134">Policy Settings</span></span></th>
<th><span data-ttu-id="bc741-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="bc741-135">Ken Myer</span></span></th>
<th><span data-ttu-id="bc741-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="bc741-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc741-137">Configuración de directiva global para proveedores de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="bc741-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="bc741-138">No</span><span class="sxs-lookup"><span data-stu-id="bc741-138">No</span></span></p></td>
<td><p><span data-ttu-id="bc741-139">No</span><span class="sxs-lookup"><span data-stu-id="bc741-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc741-140">Configuración de Directiva por usuario para proveedores de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="bc741-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="bc741-141">Sí</span><span class="sxs-lookup"><span data-stu-id="bc741-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="bc741-142">No</span><span class="sxs-lookup"><span data-stu-id="bc741-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc741-143">El usuario puede comunicarse con proveedores de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="bc741-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="bc741-144">Sí</span><span class="sxs-lookup"><span data-stu-id="bc741-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="bc741-145">No</span><span class="sxs-lookup"><span data-stu-id="bc741-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bc741-146">Como puede ver, Ken Myer tiene permiso para comunicarse con proveedores de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="bc741-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="bc741-147">Esto se debe a que la configuración de la Directiva por usuario que se le ha asignado reemplaza la configuración de la directiva global.</span><span class="sxs-lookup"><span data-stu-id="bc741-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="bc741-148">Pilar Ackerman no puede comunicarse con proveedores de mensajería instantánea pública.</span><span class="sxs-lookup"><span data-stu-id="bc741-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="bc741-149">Esto se debe a que está administrado por la directiva global y la directiva global prohíbe dicha comunicación.</span><span class="sxs-lookup"><span data-stu-id="bc741-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="bc741-150">El soporte técnico de Microsoft debe crear directivas por usuario.</span><span class="sxs-lookup"><span data-stu-id="bc741-150">Per-user policies must be created for you by Microsoft Support.</span></span> <span data-ttu-id="bc741-151">Una vez creadas las directivas, puede asignarlas a los usuarios mediante el cmdlet **Grant-CS** correspondiente (por ejemplo, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span><span class="sxs-lookup"><span data-stu-id="bc741-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="bc741-152">Las directivas por usuario son fáciles de identificar porque la identidad de la Directiva siempre comienza con el **prefijo**de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bc741-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="bc741-153">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bc741-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="bc741-154">Las fechas del <STRONG>prefijo</STRONG> de etiqueta de vuelta a los primeros días de desarrollo de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bc741-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="bc741-155">En esos días, las directivas por usuario se denominaban <EM>directivas de etiquetas</EM> y se identificaron con el <STRONG>prefijo</STRONG>de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="bc741-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="bc741-156">Estas directivas se denominan ahora con más precisión como <EM>directivas por usuario</EM>y el ámbito de la etiqueta se conoce con más precisión como <EM>ámbito por usuario</EM>.</span><span class="sxs-lookup"><span data-stu-id="bc741-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="bc741-157">Sin embargo, por motivos técnicos, el <STRONG>prefijo</STRONG> de etiqueta nunca se cambió.</span><span class="sxs-lookup"><span data-stu-id="bc741-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="bc741-158">Otro término clave que se usa al trabajar con Skype empresarial online y Windows PowerShell es el *espacio empresarial*.</span><span class="sxs-lookup"><span data-stu-id="bc741-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="bc741-159">Cuando se configura una cuenta de Skype empresarial online, a la nueva implementación se le asigna un número de identificador de inquilino, que es un identificador único global (GUID) similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="bc741-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="bc741-160">Algunos de los cmdlets de Skype empresarial online requieren que escriba el identificador de inquilino cada vez que ejecute el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bc741-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="bc741-161">Debe especificar el identificador de inquilino incluso si ha iniciado sesión y solo tiene un inquilino.</span><span class="sxs-lookup"><span data-stu-id="bc741-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="bc741-162">Afortunadamente, no es necesario memorizar el identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="bc741-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="bc741-163">Puede recuperar el identificador de inquilino en cualquier momento ejecutando el siguiente comando de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bc741-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="bc741-164">Por supuesto, saber cosas como la diferencia entre el ámbito global y el ámbito por usuario (o el ámbito de la etiqueta) es sólo la mitad de la batalla.</span><span class="sxs-lookup"><span data-stu-id="bc741-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="bc741-165">También es importante saber cuándo (o incluso si) puede usar estos ámbitos.</span><span class="sxs-lookup"><span data-stu-id="bc741-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="bc741-166">Lo mismo se aplica a las identidades y al parámetro tenant.</span><span class="sxs-lookup"><span data-stu-id="bc741-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="bc741-167">En los siguientes temas se describe cómo los diferentes cmdlets de Skype empresarial online usan identidades, ámbitos y el parámetro tenant:</span><span class="sxs-lookup"><span data-stu-id="bc741-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="bc741-168">Cmdlets de Skype empresarial online que solo usan el ámbito global</span><span class="sxs-lookup"><span data-stu-id="bc741-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="bc741-169">Cmdlets de Skype empresarial online que usan el ámbito global y el ámbito de etiqueta</span><span class="sxs-lookup"><span data-stu-id="bc741-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="bc741-170">Cmdlets de Skype empresarial online que usan una identidad de usuario</span><span class="sxs-lookup"><span data-stu-id="bc741-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="bc741-171">Cmdlets de Skype empresarial online que usan una identidad de usuario y el ámbito de etiqueta</span><span class="sxs-lookup"><span data-stu-id="bc741-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="bc741-172">Cmdlets en Skype empresarial online que usan el parámetro tenant</span><span class="sxs-lookup"><span data-stu-id="bc741-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="bc741-173">Cmdlets de Skype empresarial online que usan una identidad de proveedor de conferencias</span><span class="sxs-lookup"><span data-stu-id="bc741-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="bc741-174">Cmdlets de Skype empresarial online que no usan un ámbito ni una identidad</span><span class="sxs-lookup"><span data-stu-id="bc741-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

