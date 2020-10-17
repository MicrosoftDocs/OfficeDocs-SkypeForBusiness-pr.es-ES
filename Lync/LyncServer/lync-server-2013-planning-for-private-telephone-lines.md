---
title: 'Lync Server 2013: Planeación de líneas telefónicas privadas'
description: 'Lync Server 2013: Planeación de líneas telefónicas privadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 120c1804bc3ce58e8746f68cbda9c66f02568ccb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549316"
---
# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="eb88a-103">Planeación de líneas telefónicas privadas con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb88a-103">Planning for private telephone lines with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb88a-104">_**Última modificación del tema:** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="eb88a-104">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="eb88a-105">Lync Server 2013 introduce la capacidad de proporcionar a los usuarios una segunda línea de teléfono privada además de la línea de teléfono principal.</span><span class="sxs-lookup"><span data-stu-id="eb88a-105">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="eb88a-106">Las líneas de teléfono privadas suelen asignarse a ejecutivos y a otros usuarios que desean un número de teléfono privado en el que se les pueda contactar directamente.</span><span class="sxs-lookup"><span data-stu-id="eb88a-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="eb88a-107">Las líneas de teléfono privadas solo pueden configurarse con el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eb88a-107">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="eb88a-108">No puede configurar líneas telefónicas privadas con el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eb88a-108">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="eb88a-109">Las líneas de teléfono privadas solo deben configurarse en implementaciones de Lync Server y no en implementaciones mixtas.</span><span class="sxs-lookup"><span data-stu-id="eb88a-109">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="eb88a-110">Características de las líneas de teléfono privadas</span><span class="sxs-lookup"><span data-stu-id="eb88a-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="eb88a-111">A pesar de que el concepto de poseer una segunda línea de teléfono privada es bastante sencillo, es importante conocer las características de las líneas privadas, así como las similitudes y las diferencias con respecto a las líneas de teléfono principales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="eb88a-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="eb88a-112">Características generales de las líneas de teléfono privadas</span><span class="sxs-lookup"><span data-stu-id="eb88a-112">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="eb88a-113">Un usuario solo puede tener una línea de teléfono privada.</span><span class="sxs-lookup"><span data-stu-id="eb88a-113">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="eb88a-114">Los usuarios con una línea de teléfono privada solo disponen de un buzón de correo de voz y reciben notificaciones de llamadas perdidas en una única dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="eb88a-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="eb88a-115">Los usuarios con una línea de teléfono privada no disponen de una segunda dirección SIP y una segunda línea de teléfono privada no proporciona al usuario una segunda presencia en la red (como una segunda identidad de mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="eb88a-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="eb88a-116">Las líneas de teléfono privadas solo están disponibles para implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="eb88a-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="eb88a-117">No están disponibles en las implementaciones hospedadas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eb88a-117">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="eb88a-118">Diferencias entre las líneas de teléfono privadas y las líneas de teléfono principales</span><span class="sxs-lookup"><span data-stu-id="eb88a-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="eb88a-119">Los números de teléfono de las líneas de teléfono privadas no aparecen en los directorios de teléfonos ni en las listas de contactos que se obtienen de Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eb88a-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="eb88a-120">Ninguna de las siguientes características está disponible con una línea de teléfono privada: desvío de llamadas, llamada de equipo, delegación, anillo de equipo, recogida de llamada de grupo y aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="eb88a-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="eb88a-121">Las llamadas realizadas a una línea de teléfono privada suenan de una forma especial y la notificación del sistema para la llamada indica al usuario que la llamada entrante proviene de su línea privada.</span><span class="sxs-lookup"><span data-stu-id="eb88a-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="eb88a-p104">Las llamadas realizadas a la línea de teléfono privada siempre suenan. No siguen las reglas de "no molestar".</span><span class="sxs-lookup"><span data-stu-id="eb88a-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="eb88a-p105">Las líneas de teléfono privadas son solo entrantes y no pueden usarse para realizar llamadas salientes. Cuando un usuario con una línea de teléfono privada realiza una llamada, esta se realiza desde la línea de teléfono principal del usuario y no se oculta el nombre del usuario ni el número teléfono principal del usuario a la persona que recibe la llamada.</span><span class="sxs-lookup"><span data-stu-id="eb88a-p105">Private telephone lines are inbound only and cannot be used to make outgoing calls. When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="eb88a-126">Similitudes entre las líneas de teléfono privadas y las líneas de teléfono principales</span><span class="sxs-lookup"><span data-stu-id="eb88a-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="eb88a-127">Las llamadas no respondidas realizas a una línea de teléfono privada se enrutan a la misma bandeja de entrada de correo de voz de la línea telefónica principal (si el correo de voz está habilitado).</span><span class="sxs-lookup"><span data-stu-id="eb88a-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="eb88a-128">El estacionamiento de llamadas y la atención de llamadas funcionan con las líneas de teléfono privadas exactamente de la misma forma que con la línea de teléfono principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="eb88a-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="eb88a-129">Cuando las llamadas simultáneas se habilitan en una línea de teléfono principal del usuario, también se habilitan en la línea de teléfono privada.</span><span class="sxs-lookup"><span data-stu-id="eb88a-129">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="eb88a-130">El número de teléfono de una línea de teléfono privada se conserva en el registro de detalles de llamadas de la misma forma que el número de teléfono de una línea de teléfono principal del usuario, pero con una indicación para advertir que se trata de un número de teléfono privado.</span><span class="sxs-lookup"><span data-stu-id="eb88a-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="eb88a-131">Después de que un usuario responda a una llamada en una línea de teléfono privada, la llamada se trata de la misma forma que una llamada en la línea de teléfono principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="eb88a-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="eb88a-132">Por ejemplo, si un usuario que recibe una llamada en una línea de teléfono privada reenvía la llamada o invita a otros a una llamada de conferencia, el nombre del usuario aparece en Lync 2013 y el número de teléfono de la línea de teléfono principal del usuario aparece en identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="eb88a-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="eb88a-133">Los usuarios pueden desviar una llamada de la línea de teléfono privada (redirigir la llamada a otro destino, como un teléfono móvil o un teléfono particular, antes de responder) de la misma forma que con una línea de teléfono principal.</span><span class="sxs-lookup"><span data-stu-id="eb88a-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb88a-134">Cuando una llamada a una línea privada se enruta a un número de teléfono alternativo, el número de teléfono de la línea de teléfono privada se pone a disposición del número de teléfono alternativo y puede mostrarse en los registros de dicho número.</span><span class="sxs-lookup"><span data-stu-id="eb88a-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="eb88a-135">Las llamadas realizadas desde una conferencia a la línea de teléfono privada no tendrán la indicación <EM>línea privada</EM> en la notificación entrante del sistema.</span><span class="sxs-lookup"><span data-stu-id="eb88a-135">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="eb88a-136">Administración de líneas de teléfono privadas</span><span class="sxs-lookup"><span data-stu-id="eb88a-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="eb88a-p107">Además de los aspectos técnicos de la creación y administración de líneas de teléfono privadas, tendrá que establecer procedimientos administrativos. Entre estos, se incluye la determinación de directivas para indicar qué personas de la organización pueden obtener una línea privada, la creación y administración de listas de personas y sus líneas de teléfono (porque los números de teléfono de líneas privadas no se almacenan en Active Directory), la posible creación de un directorio de teléfonos privados para ejecutivos, la preparación de formación para usuarios y otras tareas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="eb88a-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eb88a-p108">La línea telefónica privada se almacena en Active Directory como un atributo msRTCSIP-PrivateLine en el objeto de usuario. De forma predeterminada los miembros del grupo Usuarios autenticados tiene acceso de lectura para este atributo.</span><span class="sxs-lookup"><span data-stu-id="eb88a-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="eb88a-141">Asignación de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="eb88a-141">Assigning Telephone Numbers</span></span>

<span data-ttu-id="eb88a-142">Las cuentas para nuevos usuarios que necesitan líneas de teléfono privadas se crean de la misma forma que las cuentas sin líneas de teléfono privadas, mediante el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eb88a-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="eb88a-143">Use el cmdlet **set-CsUser** en el shell de administración de Lync Server para asignar un número de teléfono a una línea de teléfono privada para un usuario, por ejemplo, **set-CsUser-Identity "SIP:Joe@contoso.com"-PrivateLine "Tel: + 14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="eb88a-143">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="eb88a-144">Los números de teléfono de las líneas de teléfono privadas pueden tener entre 3 y 15 números de longitud y deben ir precedidos del prefijo "TEL:".</span><span class="sxs-lookup"><span data-stu-id="eb88a-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="eb88a-145">Pueden tener cualquier código de área y de país, siempre que la organización disponga de llamada directa a la extensión para dicho código de área y de país/región.</span><span class="sxs-lookup"><span data-stu-id="eb88a-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="eb88a-146">Para obtener más información acerca de los cmdlets y el shell de administración de Lync Server, consulte la documentación del [Shell de administración de Lync server 2013](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="eb88a-146">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="eb88a-147">Líneas de teléfono privadas en implementaciones mezcladas</span><span class="sxs-lookup"><span data-stu-id="eb88a-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="eb88a-148">Las líneas de teléfono privadas solo deben configurarse para implementaciones de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eb88a-148">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="eb88a-149">En una implementación en la que hay servidores de Lync Server y Office Communications Server 2007 o de Office Communications Server 2007 R2, cuando un usuario de una versión anterior intenta llamar a una línea de teléfono privada, el enrutamiento de la llamada produce un error porque el servidor no puede realizar una búsqueda inversa de números en una línea de teléfono privada.</span><span class="sxs-lookup"><span data-stu-id="eb88a-149">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

