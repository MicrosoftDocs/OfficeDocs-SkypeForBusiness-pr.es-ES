---
title: 'Lync Server 2013: consideraciones de migración para las reuniones'
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
ms.openlocfilehash: 9ec650c62b26775aeddf9f01ff8d455a6f6a7667
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-considerations-for-meetings-in-lync-server-2013"></a><span data-ttu-id="9c98e-102">Consideraciones sobre la migración para las reuniones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c98e-102">Migration considerations for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c98e-103">_**Última modificación del tema:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="9c98e-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="9c98e-104">En esta sección se describen los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9c98e-104">The following topics are discussed in this section:</span></span>

  - <span data-ttu-id="9c98e-105">Cambios en las reuniones en Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c98e-105">Changes to meetings in Microsoft Lync Server 2013</span></span>

  - <span data-ttu-id="9c98e-106">Migrar usuarios según sus necesidades de conferencia</span><span class="sxs-lookup"><span data-stu-id="9c98e-106">Migrating users based on their conferencing needs</span></span>

  - <span data-ttu-id="9c98e-107">Migrar reuniones existentes y contenidos de reuniones</span><span class="sxs-lookup"><span data-stu-id="9c98e-107">Migrating existing meetings and meeting content</span></span>

  - <span data-ttu-id="9c98e-108">Experiencia del usuario durante la migración de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9c98e-108">User experience during Lync Server 2010 migration</span></span>

  - <span data-ttu-id="9c98e-109">Experiencia del usuario durante la migración de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9c98e-109">User Experience during Office Communications Server 2007 R2 migration</span></span>

  - <span data-ttu-id="9c98e-110">Compatibilidad de Microsoft Lync 2013 con reuniones en versiones anteriores del servidor</span><span class="sxs-lookup"><span data-stu-id="9c98e-110">Microsoft Lync 2013 compatibility with meetings on earlier server versions</span></span>

<div>

## <a name="changes-to-meetings-in-lync-server-2013"></a><span data-ttu-id="9c98e-111">Cambios en las reuniones en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c98e-111">Changes to Meetings in Lync Server 2013</span></span>

<span data-ttu-id="9c98e-112">**Características de Lync Server 2013.**    Lync Server 2013 proporciona nuevas características de conferencia que se ponen a disposición de los usuarios después de que sus cuentas se muevan a Lync Server 2013 y inician sesión con el cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9c98e-112">**Lync Server 2013 features.**   Lync Server 2013 provides new conferencing features that become available to users after their accounts are moved to Lync Server 2013 and they sign in with the Lync 2013 client.</span></span> <span data-ttu-id="9c98e-113">Las nuevas características se describen en [nuevas características de conferencia en Lync server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [para clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9c98e-113">New features are outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="9c98e-114">**Dirección URL de la reunión.**    Al igual que en lync Server 2010, todas las reuniones recientemente programadas en lync Server 2013 tienen un prefijo de dirección URL de https://y las reuniones existentes se migran junto con las cuentas de usuario.</span><span class="sxs-lookup"><span data-stu-id="9c98e-114">**Meeting URL.**   As in Lync Server 2010, all newly scheduled meetings in Lync Server 2013 have a URL prefix of https:// and existing meetings migrate along with user accounts.</span></span> <span data-ttu-id="9c98e-115">Sin embargo, Lync Server 2013 no admite la llamada de conferencia de Office Communications Server 2007 R2 (Prefijo de dirección URL de conf://) ni la conferencia web (Prefijo de dirección URL meet://).</span><span class="sxs-lookup"><span data-stu-id="9c98e-115">However, Lync Server 2013 does not support the Office Communications Server 2007 R2 conference call (conf:// URL prefix) or web conference (meet:// URL prefix).</span></span> <span data-ttu-id="9c98e-116">Para obtener más información, vea "migrar reuniones de Office Communications Server 2007 R2" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="9c98e-116">See “Migrating Meetings from Office Communications Server 2007 R2” later in this topic for more information.</span></span>

<span data-ttu-id="9c98e-117">**Compatibilidad con clientes.**    A diferencia de lync Server 2010, lync Server 2013 no es compatible con los clientes de Office Communicator para conferencias.</span><span class="sxs-lookup"><span data-stu-id="9c98e-117">**Client support.**   Unlike Lync Server 2010, Lync Server 2013 does not support Office Communicator clients for conferencing.</span></span> <span data-ttu-id="9c98e-118">No puede usar los siguientes clientes para unirse a reuniones programadas mediante el complemento de reunión en línea para Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="9c98e-118">You cannot use the following clients to join meetings scheduled through the Online Meeting Add-in for Lync 2013:</span></span>

  - <span data-ttu-id="9c98e-119">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9c98e-119">Office Communicator 2007 R2</span></span>

  - <span data-ttu-id="9c98e-120">Operador de Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9c98e-120">Microsoft Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="9c98e-121">Office Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="9c98e-121">Office Communicator 2007</span></span>

  - <span data-ttu-id="9c98e-122">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="9c98e-122">Office Live Meeting 2007</span></span>

<span data-ttu-id="9c98e-123">Durante la migración, los usuarios de Office Communicator 2007 R2 deben usar Lync Web App 2013 para unirse a las reuniones de Lync Server 2013 hasta que se actualicen sus clientes.</span><span class="sxs-lookup"><span data-stu-id="9c98e-123">During migration, Office Communicator 2007 R2 users should use Lync Web App 2013 to join Lync Server 2013 meetings until their clients are upgraded.</span></span> <span data-ttu-id="9c98e-124">Tenga en cuenta que los usuarios de 2007 R2 de Office Communicator pueden seguir usando su cliente existente en Lync Server 2013 para las características de presencia y mensajería instantánea, pero no se admiten las características de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9c98e-124">Note that Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

<div>


</div>

</div>

<div>

## <a name="migrating-users-based-on-their-conferencing-needs"></a><span data-ttu-id="9c98e-125">Migrar usuarios según sus necesidades de conferencia</span><span class="sxs-lookup"><span data-stu-id="9c98e-125">Migrating Users Based on Their Conferencing Needs</span></span>

<span data-ttu-id="9c98e-126">**Organizadores de reuniones frecuentes.**    Considere la posibilidad de migrar los organizadores de reuniones frecuentes al principio del proceso para que puedan aprovechar las nuevas características de lync Server 2013 y Lync 2013 descritas en [nuevas características de conferencia en Lync Server 2013](lync-server-2013-new-conferencing-features.md) y las novedades [de los clientes en Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="9c98e-126">**Frequent meeting organizers.**   Consider migrating frequent meeting organizers early in the process so that they can take advantage of the new Lync Server 2013 and Lync 2013 features outlined in [New conferencing features in Lync Server 2013](lync-server-2013-new-conferencing-features.md) and [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).</span></span>

<span data-ttu-id="9c98e-127">**Usuarios de Live Meeting.**    Si va a migrar desde Office Communications Server 2007 R2 y tiene usuarios que necesitan características de conferencia Web específicas para Live Meeting (en particular, para reuniones de gran tamaño y salas de salida), tiene las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="9c98e-127">**Live Meeting users.**   If you are migrating from Office Communications Server 2007 R2 and you have users who need web conferencing features specific to Live Meeting—particularly support for large meetings and break-out rooms—you have the following options:</span></span>

  - <span data-ttu-id="9c98e-128">Aconseje a los organizadores que usen el servicio de Live Meeting, en caso de que esté disponible en su organización.</span><span class="sxs-lookup"><span data-stu-id="9c98e-128">Advise organizers to use the Live Meeting service, if available in your organization.</span></span>

  - <span data-ttu-id="9c98e-129">Deje los organizadores hospedados en la versión anterior de Office Communications Server, para que puedan seguir programando conferencias web de Live Meeting basadas en servidor.</span><span class="sxs-lookup"><span data-stu-id="9c98e-129">Leave the organizers homed on the earlier version of Office Communications Server, so they can continue to schedule server-based Live Meeting web conferences.</span></span>

</div>

<div>

## <a name="migrating-existing-meetings-and-meeting-content"></a><span data-ttu-id="9c98e-130">Migrar reuniones existentes y contenidos de reuniones</span><span class="sxs-lookup"><span data-stu-id="9c98e-130">Migrating Existing Meetings and Meeting Content</span></span>

<div>

## <a name="migrating-meetings-from-lync-server-2010"></a><span data-ttu-id="9c98e-131">Migrar reuniones desde Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9c98e-131">Migrating Meetings from Lync Server 2010</span></span>

<span data-ttu-id="9c98e-132">Cuando mueve un usuario de Lync Server 2010 a Lync Server 2013, la siguiente información se mueve con la cuenta del usuario:</span><span class="sxs-lookup"><span data-stu-id="9c98e-132">When you move a user from Lync Server 2010 to Lync Server 2013, the following information moves with the user’s account:</span></span>

  - <span data-ttu-id="9c98e-133">Las reuniones ya programadas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="9c98e-133">Meetings already scheduled by the user.</span></span> <span data-ttu-id="9c98e-134">Esto incluye los directorios de conferencias y los datos de conferencia.</span><span class="sxs-lookup"><span data-stu-id="9c98e-134">This includes conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="9c98e-135">El número de identificación personal (PIN) del usuario.</span><span class="sxs-lookup"><span data-stu-id="9c98e-135">The user’s personal identification number (PIN).</span></span> <span data-ttu-id="9c98e-136">El PIN actual del usuario seguirá funcionando hasta que caduque o hasta que el usuario solicite un PIN nuevo.</span><span class="sxs-lookup"><span data-stu-id="9c98e-136">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="9c98e-137">Sin embargo, la siguiente información de la cuenta de usuario no se mueve al nuevo servidor:</span><span class="sxs-lookup"><span data-stu-id="9c98e-137">However, the following user account information does not move to the new server:</span></span>

  - <span data-ttu-id="9c98e-138">Contenido de la reunión, por ejemplo, presentaciones de PowerPoint, contenido de la pizarra y datos de sondeo</span><span class="sxs-lookup"><span data-stu-id="9c98e-138">Meeting content, for example PowerPoint presentations, whiteboard content, and poll data</span></span>

<span data-ttu-id="9c98e-139">Para mover el contenido que se ha compartido en las reuniones, use el parámetro MoveMeetingContent del cmdlet Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="9c98e-139">To move the content that has been shared in meetings, use the MoveMeetingContent parameter of the Move-CsUser cmdlet.</span></span> <span data-ttu-id="9c98e-140">Para obtener más información sobre el uso de este cmdlet, consulte [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) en la documentación de cmdlets de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c98e-140">For details about using this cmdlet, see [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) in the Lync Server 2013 cmdlets documentation.</span></span>

</div>

<div>

## <a name="migrating-meetings-from-office-communications-server-2007-r2"></a><span data-ttu-id="9c98e-141">Migrar reuniones desde Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9c98e-141">Migrating Meetings from Office Communications Server 2007 R2</span></span>

<span data-ttu-id="9c98e-142">Las reuniones de Office Communications Server 2007 R2 son llamadas de conferencia (prefijos de dirección URL de conf://) o conferencias web (Prefijo de dirección URL de meet://).</span><span class="sxs-lookup"><span data-stu-id="9c98e-142">Office Communications Server 2007 R2 meetings are either conference calls (conf:// URL prefix) or web conferences (meet:// URL prefix).</span></span> <span data-ttu-id="9c98e-143">Lync Server 2013 no es compatible con estas conferencias anteriores de conf://y meet://, y no se migran junto con la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="9c98e-143">Lync Server 2013 does not support these earlier conf:// and meet:// conferences, and they are not migrated along with the user account.</span></span> <span data-ttu-id="9c98e-144">Después de la migración, debe indicar a los usuarios que actualicen los vínculos de las reuniones en línea que hayan programado.</span><span class="sxs-lookup"><span data-stu-id="9c98e-144">After migration, you should instruct users to update the links for any online meetings they have scheduled.</span></span> <span data-ttu-id="9c98e-145">Pueden hacerlo después de instalar el cliente Lync 2013 abriendo una invitación de reunión programada (que actualiza la dirección URL de la reunión) y reenviando la invitación a los participantes.</span><span class="sxs-lookup"><span data-stu-id="9c98e-145">They can do this after installing the Lync 2013 client by opening a scheduled meeting invitation—which updates the meeting URL—and resending the invitation to participants.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-lync-server-2010-migration"></a><span data-ttu-id="9c98e-146">Experiencia del usuario durante la migración de Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="9c98e-146">User Experience during Lync Server 2010 Migration</span></span>

<span data-ttu-id="9c98e-147">En esta sección se proporciona un resumen de la experiencia de conferencia de los usuarios al migrar desde Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="9c98e-147">This section provides a summary of users’ conferencing experience when migrating from Lync 2010.</span></span> <span data-ttu-id="9c98e-148">Para obtener más información sobre cómo pueden coexistir los clientes de Lync Server 2013 e interactuar con versiones de cliente y servidor anteriores, vea [interoperabilidad de cliente en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9c98e-148">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="joining-lync-server-2010-meetings-with-a-lync-2013-client"></a><span data-ttu-id="9c98e-149">Unirse a reuniones de Lync Server 2010 con un cliente de Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9c98e-149">Joining Lync Server 2010 Meetings with a Lync 2013 Client</span></span>

<span data-ttu-id="9c98e-150">Durante la migración desde Lync Server 2010, puede haber un período de coexistencia cuando los usuarios se unen a reuniones de Lync Server 2010 con un cliente de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9c98e-150">During migration from Lync Server 2010, there may be a period of coexistence when users join Lync Server 2010 meetings with a Lync 2013 client.</span></span> <span data-ttu-id="9c98e-151">Estos usuarios tienen acceso a las características de cliente de Lync 2013 con las siguientes excepciones:</span><span class="sxs-lookup"><span data-stu-id="9c98e-151">These users have access to Lync 2013 client features with the following exceptions:</span></span>

  - <span data-ttu-id="9c98e-152">En las opciones de administración de **participantes** , a las que se puede tener acceso seleccionando el icono de personas en la ventana de la reunión, la opción de **mensajería instantánea sin reunión** no funciona.</span><span class="sxs-lookup"><span data-stu-id="9c98e-152">In the **Participants** management options, which are accessible by pointing to the people icon in the meeting window, the **No Meeting IM** option does not function.</span></span>

  - <span data-ttu-id="9c98e-153">La vista de Galería no funciona en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="9c98e-153">Gallery View does not function in video conferences.</span></span> <span data-ttu-id="9c98e-154">El usuario solo ve el participante activo en lugar de todos los altavoces.</span><span class="sxs-lookup"><span data-stu-id="9c98e-154">The user sees only the active speaker instead of all speakers.</span></span> <span data-ttu-id="9c98e-155">En la lista de opciones de **selección de un diseño** , la **vista de Galería** no está disponible</span><span class="sxs-lookup"><span data-stu-id="9c98e-155">In the list of **Pick a Layout** options, **Gallery View** is unavailable</span></span>

  - <span data-ttu-id="9c98e-156">La lista de participantes se muestra de forma predeterminada en las videoconferencias.</span><span class="sxs-lookup"><span data-stu-id="9c98e-156">The participant list displays by default in video conferences.</span></span>

  - <span data-ttu-id="9c98e-157">Al hacer clic con el botón derecho en un usuario de la lista participantes, las opciones **bloquear la luz de vídeo** y **anclar al** participante de la galería no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="9c98e-157">When right-clicking a user in the participants list, the **Lock the Video Spotlight** and **Pin to Gallery** participant management options are unavailable.</span></span>

</div>

</div>

<div>

## <a name="user-experience-during-office-communications-server-2007-r2-migration"></a><span data-ttu-id="9c98e-158">Experiencia del usuario durante la migración de Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="9c98e-158">User Experience during Office Communications Server 2007 R2 Migration</span></span>

<span data-ttu-id="9c98e-159">En esta sección se proporciona un resumen de la experiencia de conferencia de los usuarios al realizar la migración desde Office Communications Server 2007 R2, tanto antes como después de instalar Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9c98e-159">This section provides a summary of users’ conferencing experience when migrating from Office Communications Server 2007 R2, both before and after Lync 2013 is installed.</span></span> <span data-ttu-id="9c98e-160">Para obtener más información sobre cómo pueden coexistir los clientes de Lync Server 2013 e interactuar con versiones de cliente y servidor anteriores, vea [interoperabilidad de cliente en Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span><span class="sxs-lookup"><span data-stu-id="9c98e-160">For more details about how Lync Server 2013 clients can coexist and interact with previous client and server versions, see [Client interoperability in Lync 2013](lync-server-2013-client-interoperability-in-lync-2013.md).</span></span>

<div>

## <a name="after-user-account-is-migrated-before-lync-2013-is-installed"></a><span data-ttu-id="9c98e-161">Después de migrar la cuenta de usuario, antes de instalar Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9c98e-161">After User Account is Migrated, Before Lync 2013 Is Installed</span></span>

<span data-ttu-id="9c98e-162">Una vez que se ha migrado un usuario al servidor de Lync Server 2013, pero antes de que se instalen nuevos clientes, los usuarios de Office Communicator 2007 R2 pueden seguir usando su cliente existente en Lync Server 2013 para las características de presencia y mensajería instantánea, pero las características de conferencia no admitir.</span><span class="sxs-lookup"><span data-stu-id="9c98e-162">After a user is migrated to the Lync Server 2013 server, but before new clients are installed, Office Communicator 2007 R2 users can continue to use their existing client against Lync Server 2013 for presence and IM features, but conferencing features are not supported.</span></span>

</div>

<div>

## <a name="after-user-account-is-migrated-after-lync-2013-is-installed"></a><span data-ttu-id="9c98e-163">Después de migrar la cuenta de usuario, después de instalar Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9c98e-163">After User Account is Migrated, After Lync 2013 Is Installed</span></span>

<span data-ttu-id="9c98e-164">Cuando un usuario migrado instala Lync 2013, también se instala el complemento de reunión en línea para Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="9c98e-164">When a migrated user installs Lync 2013, the Online Meeting Add-in for Lync 2013 is installed too.</span></span> <span data-ttu-id="9c98e-165">Esto tiene las siguientes repercusiones:</span><span class="sxs-lookup"><span data-stu-id="9c98e-165">This has the following effects:</span></span>

  - <span data-ttu-id="9c98e-166">Todas las reuniones programadas posteriormente usarán el formato nuevo de reunión, que utiliza una dirección https:// en lugar de la dirección heredada de Live Meeting meet://.</span><span class="sxs-lookup"><span data-stu-id="9c98e-166">All subsequently scheduled meetings use the new meeting format, which uses an https:// address instead of the legacy meet:// Live Meeting address.</span></span>

  - <span data-ttu-id="9c98e-167">En una implementación administrada de TI de Lync 2013, el administrador tiene la opción de desinstalar el complemento de conferencia para Microsoft Office Outlook, que se usa para programar las reuniones basadas en servicios y el servidor de Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="9c98e-167">In an IT-managed deployment of Lync 2013, the administrator has the option of uninstalling the Conferencing Add-in for Microsoft Office Outlook, which is used to schedule Live Meeting server and service-based meetings.</span></span> <span data-ttu-id="9c98e-168">Sin embargo, puede tener usuarios que necesiten seguir programando reuniones del servicio de Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="9c98e-168">However, you may have users who need to continue to schedule Live Meeting service meetings.</span></span> <span data-ttu-id="9c98e-169">En este caso, puede permitir que los dos complementos coexistan.</span><span class="sxs-lookup"><span data-stu-id="9c98e-169">In this case, you can allow both add-ins to coexist.</span></span>

</div>

<div>

## <a name="meetings-with-federated-organizations-that-use-previous-clients"></a><span data-ttu-id="9c98e-170">Reuniones con organizaciones federadas que usen clientes anteriores</span><span class="sxs-lookup"><span data-stu-id="9c98e-170">Meetings with Federated Organizations that Use Previous Clients</span></span>

<span data-ttu-id="9c98e-171">Los usuarios de organizaciones federadas que usen Microsoft Office Communicator 2007 no pueden unirse a reuniones de Lync Server 2013 en su organización si esas reuniones están bloqueadas por el organizador.</span><span class="sxs-lookup"><span data-stu-id="9c98e-171">Users in federated organizations who are using Microsoft Office Communicator 2007 cannot join Lync Server 2013 meetings in your organization if those meetings are locked by the organizer.</span></span> <span data-ttu-id="9c98e-172">Debe reprogramar estas reuniones en Lync Server 2013 de modo que, cuando los participantes federados se unan a la reunión con la nueva dirección URL de reunión de https://, puedan usar Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="9c98e-172">You have to reschedule these meetings in Lync Server 2013 so when federated participants join the meeting by using the new https:// meeting URL, they can use Lync Web App.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

