---
title: 'Lync Server 2013: consideraciones de migración para reuniones'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration considerations for meetings
ms:assetid: a9807d58-99a3-4cff-b4c6-74950d106a2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412800(v=OCS.15)
ms:contentKeyID: 61097556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6af94514360509d4f608a21228b2fecf9a522007
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="91ab7-102">Consideraciones de migración para las reuniones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91ab7-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91ab7-103">_**Última modificación del tema:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="91ab7-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="91ab7-104">En esta sección se tratan los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="91ab7-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="91ab7-105">Cambios en las reuniones de Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91ab7-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="91ab7-106">Migrar usuarios en función de sus necesidades de conferencia</span><span class="sxs-lookup"><span data-stu-id="91ab7-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="91ab7-107">Migrar reuniones y contenido de reuniones existentes</span><span class="sxs-lookup"><span data-stu-id="91ab7-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="91ab7-108">Experiencia del usuario durante la migración de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="91ab7-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="91ab7-109">Experiencia del usuario durante la migración de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="91ab7-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="91ab7-110">Compatibilidad de Microsoft Lync 2013 con reuniones en versiones anteriores de un servidor</span><span class="sxs-lookup"><span data-stu-id="91ab7-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="91ab7-111">Cambios en las reuniones de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91ab7-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="91ab7-112">**Características de Lync Server 2013.**    Lync Server 2013 proporciona nuevas características de conferencia que estarán disponibles para los usuarios después de que sus cuentas se muevan a Lync Server 2013 y que inicien sesión con el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="91ab7-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="91ab7-113">Las nuevas características se describen en [las nuevas características de conferencia de Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="91ab7-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="91ab7-114">**Dirección URL de la reunión.**    Al igual que en lync Server 2010, todas las reuniones recién programadas en lync Server 2013 tienen un prefijo de dirección URL de https://y las reuniones existentes se migran con las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="91ab7-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="91ab7-115">Sin embargo, Lync Server 2013 no admite la llamada de conferencia de Office Communications Server 2007 R2 (Prefijo de URL de conf://) o la conferencia web (Prefijo de dirección URL de meet://).</span><span class="sxs-lookup"><span data-stu-id="91ab7-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="91ab7-116">Para obtener más información, vea "migrar reuniones de Office Communications Server 2007 R2" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="91ab7-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="91ab7-117">**Compatibilidad con clientes.**    A diferencia de lync Server 2010, lync Server 2013 no es compatible con los clientes de Office Communicator para conferencias.</span><span class="sxs-lookup"><span data-stu-id="91ab7-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="91ab7-118">No puede usar los siguientes clientes para unirse a reuniones programadas a través del complemento de reuniones en línea para Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="91ab7-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="91ab7-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="91ab7-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="91ab7-120">Operador de Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="91ab7-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="91ab7-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="91ab7-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="91ab7-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="91ab7-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="91ab7-123">Durante la migración, los usuarios de Office Communicator 2007 R2 deben usar Lync Web App 2013 para unirse a las reuniones de Lync Server 2013 hasta que sus clientes se actualicen.</span><span class="sxs-lookup"><span data-stu-id="91ab7-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="91ab7-124">Tenga en cuenta que los usuarios de Office Communicator 2007 R2 pueden continuar usando su cliente existente en Lync Server 2013 para las características de presencia y mensajería instantánea, pero no son compatibles con las características de conferencia.</span><span class="sxs-lookup"><span data-stu-id="91ab7-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="91ab7-125">Migrar usuarios en función de sus necesidades de conferencia</span><span class="sxs-lookup"><span data-stu-id="91ab7-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="91ab7-126">**Organizadores de reuniones frecuentes.**    Considere migrar con frecuencia los organizadores de reuniones al principio del proceso para poder aprovechar las nuevas características de lync Server 2013 y Lync 2013 descritas en [las nuevas características de conferencia de Lync Server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="91ab7-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="91ab7-127">**Usuarios de Live Meeting.**    Si va a migrar desde Office Communications Server 2007 R2 y tiene usuarios que necesitan características de conferencias web específicas de Live Meeting, especialmente en el caso de reuniones y salas de despiece de gran tamaño, tiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="91ab7-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="91ab7-128">Aconseje a los organizadores que usen el servicio de Live Meeting, si está disponible en su organización.</span><span class="sxs-lookup"><span data-stu-id="91ab7-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="91ab7-129">Deje los organizadores alojados en la versión anterior de Office Communications Server para que puedan continuar con la programación de conferencias web de Live Meeting basadas en servidor.</span><span class="sxs-lookup"><span data-stu-id="91ab7-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="91ab7-130">Migrar reuniones y contenido de reuniones existentes</span><span class="sxs-lookup"><span data-stu-id="91ab7-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="91ab7-131">Migrar reuniones desde Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="91ab7-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="91ab7-132">Al mover un usuario de Lync Server 2010 a Lync Server 2013, la siguiente información se mueve con la cuenta del usuario:</span><span class="sxs-lookup"><span data-stu-id="91ab7-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="91ab7-133">Reuniones ya programadas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="91ab7-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="91ab7-134">Esto incluye los directorios de conferencias y los datos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="91ab7-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="91ab7-135">Número de identificación personal (PIN) del usuario.</span><span class="sxs-lookup"><span data-stu-id="91ab7-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="91ab7-136">El PIN actual del usuario sigue funcionando hasta que venza o cuando el usuario solicite un nuevo PIN.</span><span class="sxs-lookup"><span data-stu-id="91ab7-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="91ab7-137">Sin embargo, la siguiente información de la cuenta de usuario no se mueve al nuevo servidor:</span><span class="sxs-lookup"><span data-stu-id="91ab7-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="91ab7-138">Contenido de la reunión, por ejemplo, presentaciones de PowerPoint, contenido de pizarra y datos de sondeos</span><span class="sxs-lookup"><span data-stu-id="91ab7-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="91ab7-139">Para mover el contenido que se ha compartido en las reuniones, use el parámetro MoveMeetingContent del cmdlet Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="91ab7-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="91ab7-140">Para obtener más información sobre el uso de este cmdlet, consulte [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) en la documentación de cmdlets de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="91ab7-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="91ab7-141">Migrar reuniones desde Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="91ab7-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="91ab7-142">Las reuniones de Office Communications Server 2007 R2 son llamadas en conferencia (prefijos de dirección URL conf://) o conferencias web (prefijo meet://URL).</span><span class="sxs-lookup"><span data-stu-id="91ab7-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="91ab7-143">Lync Server 2013 no admite estas conferencias de conf://y meet://anteriores, y no se migran junto con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="91ab7-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="91ab7-144">Después de la migración, debe indicar a los usuarios que actualicen los vínculos de las reuniones en línea que hayan programado.</span><span class="sxs-lookup"><span data-stu-id="91ab7-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="91ab7-145">Pueden hacerlo después de instalar el cliente de Lync 2013 abriendo una invitación de reunión programada (que actualiza la dirección URL de la reunión) y reenviando la invitación a los participantes.</span><span class="sxs-lookup"><span data-stu-id="91ab7-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="91ab7-146">Experiencia del usuario durante la migración de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="91ab7-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="91ab7-147">Esta sección proporciona un resumen de la experiencia de conferencia de los usuarios al migrar desde Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="91ab7-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="91ab7-148">Para obtener más información sobre cómo pueden coexistir los clientes de Lync Server 2013 e interactuar con versiones de cliente y servidor anteriores, consulte [interoperabilidad de cliente en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="91ab7-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="91ab7-149">Unirse a reuniones de Lync Server 2010 con un cliente de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="91ab7-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="91ab7-150">Durante la migración desde Lync Server 2010, es posible que haya un período de coexistencia cuando los usuarios se unan a reuniones de Lync Server 2010 con un cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="91ab7-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="91ab7-151">Estos usuarios tienen acceso a las características de cliente de Lync 2013 con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="91ab7-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="91ab7-152">En las opciones de administración de **participantes** , a las que se puede acceder seleccionando el icono de personas en la ventana de la reunión, la opción **sin mensajería instantánea** no funciona.</span><span class="sxs-lookup"><span data-stu-id="91ab7-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="91ab7-153">La vista de Galería no funciona en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="91ab7-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="91ab7-154">El usuario solo ve el orador activo en lugar de todos los altavoces.</span><span class="sxs-lookup"><span data-stu-id="91ab7-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="91ab7-155">En la lista de opciones de **diseño** , la **vista de Galería** no está disponible</span><span class="sxs-lookup"><span data-stu-id="91ab7-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="91ab7-156">La lista de participantes se muestra de forma predeterminada en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="91ab7-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="91ab7-157">Al hacer clic con el botón derecho en un usuario de la lista participantes, las opciones **bloquear las imágenes destacadas** y **anclar a la Galería** no estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="91ab7-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="91ab7-158">Experiencia del usuario durante la migración de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="91ab7-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="91ab7-159">Esta sección proporciona un resumen de la experiencia de conferencia de los usuarios al migrar desde Office Communications Server 2007 R2, tanto antes como después de instalar Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="91ab7-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="91ab7-160">Para obtener más información sobre cómo pueden coexistir los clientes de Lync Server 2013 e interactuar con versiones de cliente y servidor anteriores, consulte [interoperabilidad de cliente en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="91ab7-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="91ab7-161">Después de migrar la cuenta de usuario, antes de instalar Lync 2013</span><span class="sxs-lookup"><span data-stu-id="91ab7-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="91ab7-162">Después de que un usuario se migra al servidor de Lync Server 2013, pero antes de que se instalen nuevos clientes, los usuarios de Office Communicator 2007 R2 pueden continuar usando su cliente existente en Lync Server 2013 para las características de presencia y mensajería instantánea, pero las características de conferencia no se posible.</span><span class="sxs-lookup"><span data-stu-id="91ab7-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="91ab7-163">Después de migrar la cuenta de usuario, después de instalar Lync 2013</span><span class="sxs-lookup"><span data-stu-id="91ab7-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="91ab7-164">Cuando un usuario migrado instala Lync 2013, también se instala el complemento de reunión en línea para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="91ab7-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="91ab7-165">Esto tiene los siguientes efectos:</span><span class="sxs-lookup"><span data-stu-id="91ab7-165">This has the following effects:</span></span>

  - <span data-ttu-id="91ab7-166">Todas las reuniones programadas posteriormente usan el nuevo formato de reunión, que usa una dirección de https://en lugar de la dirección heredada de meet://Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="91ab7-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="91ab7-167">En una implementación administrada por ti de Lync 2013, el administrador tiene la opción de desinstalar el complemento de conferencias para Microsoft Office Outlook, que se usa para programar Live Meeting Server y las reuniones basadas en servicios.</span><span class="sxs-lookup"><span data-stu-id="91ab7-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="91ab7-168">Sin embargo, es posible que tenga usuarios que necesiten continuar programando reuniones de servicio de Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="91ab7-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="91ab7-169">En este caso, puede permitir que ambos complementos coexistan.</span><span class="sxs-lookup"><span data-stu-id="91ab7-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="91ab7-170">Reuniones con organizaciones federadas que usan clientes anteriores</span><span class="sxs-lookup"><span data-stu-id="91ab7-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="91ab7-171">Los usuarios de organizaciones federadas que usan Microsoft Office Communicator 2007 no pueden unirse a reuniones de Lync Server 2013 de su organización si dichas reuniones están bloqueadas por el organizador.</span><span class="sxs-lookup"><span data-stu-id="91ab7-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="91ab7-172">Debe reprogramar estas reuniones en Lync Server 2013 de modo que cuando los participantes federados se unan a la reunión con la nueva dirección URL de la reunión de https://, pueden usar Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="91ab7-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

