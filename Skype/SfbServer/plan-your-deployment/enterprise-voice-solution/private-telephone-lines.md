---
title: Planificar líneas de teléfono privadas con Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planificación de líneas de teléfono privadas (secundarias) en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 0ae62c4ee56a16583106c89b5ca1b190ee242e2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813600"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="00ff6-103">Planificar líneas de teléfono privadas con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="00ff6-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="00ff6-104">Planificación de líneas de teléfono privadas (secundarias) en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="00ff6-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="00ff6-105">Skype Empresarial Server le permite proporcionar a los usuarios una segunda línea de teléfono privada además de su línea de teléfono principal.</span><span class="sxs-lookup"><span data-stu-id="00ff6-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="00ff6-106">Las líneas de teléfono privadas suelen asignarse a ejecutivos y a otros usuarios que desean un número de teléfono privado en el que se les pueda contactar directamente.</span><span class="sxs-lookup"><span data-stu-id="00ff6-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="00ff6-107">Las líneas de teléfono privadas solo se pueden configurar con el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="00ff6-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="00ff6-108">No puede configurar líneas de teléfono privadas con el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="00ff6-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="00ff6-109">Las líneas de teléfono privadas solo deben configurarse en implementaciones de Skype Empresarial Server y no en implementaciones mixtas.</span><span class="sxs-lookup"><span data-stu-id="00ff6-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="00ff6-110">Características de las líneas de teléfono privadas</span><span class="sxs-lookup"><span data-stu-id="00ff6-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="00ff6-111">Aunque el concepto de una segunda línea de teléfono privada es fundamentalmente sencillo, es importante comprender las características de las líneas privadas y las formas en que son similares y diferentes de las líneas de teléfono principales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="00ff6-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="00ff6-112">Características generales de las líneas de teléfono privadas</span><span class="sxs-lookup"><span data-stu-id="00ff6-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="00ff6-113">Un usuario solo puede tener una línea de teléfono privada.</span><span class="sxs-lookup"><span data-stu-id="00ff6-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="00ff6-114">Los usuarios con una línea de teléfono privada solo disponen de un buzón de correo de voz y reciben notificaciones de llamadas perdidas en una única dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="00ff6-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="00ff6-115">Los usuarios con una línea de teléfono privada no disponen de una segunda dirección SIP y una segunda línea de teléfono privada no proporciona al usuario una segunda presencia en la red (como una segunda identidad de mensajería instantánea).</span><span class="sxs-lookup"><span data-stu-id="00ff6-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="00ff6-116">Las líneas de teléfono privadas solo están disponibles para implementaciones locales.</span><span class="sxs-lookup"><span data-stu-id="00ff6-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="00ff6-117">No están disponibles con implementaciones hospedadas de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="00ff6-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="00ff6-118">Diferencias entre las líneas de teléfono privadas y las líneas de teléfono principales</span><span class="sxs-lookup"><span data-stu-id="00ff6-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="00ff6-119">Los números de teléfono de las líneas de teléfono privadas no aparecen en los directorios de teléfonos ni en las listas de contactos que se obtienen de Servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="00ff6-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="00ff6-120">Ninguna de las siguientes características está disponible con una línea de teléfono privada: reenvío de llamadas, llamada de equipo, delegación, anillo de equipo, atención de llamadas grupales y aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="00ff6-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="00ff6-121">Las llamadas realizadas a una línea de teléfono privada suenan de una forma especial y la notificación del sistema para la llamada indica al usuario que la llamada entrante proviene de su línea privada.</span><span class="sxs-lookup"><span data-stu-id="00ff6-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="00ff6-p104">Las llamadas realizadas a la línea de teléfono privada siempre suenan. No siguen las reglas de "no molestar".</span><span class="sxs-lookup"><span data-stu-id="00ff6-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="00ff6-124">Las líneas de teléfono privadas son solo entrantes y no pueden usarse para realizar llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="00ff6-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="00ff6-125">Cuando un usuario con una línea de teléfono privada realiza una llamada, la llamada se origina en la línea de teléfono principal del usuario y no oculta el nombre del usuario ni el número de teléfono principal del usuario a la persona a la que se llama.</span><span class="sxs-lookup"><span data-stu-id="00ff6-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="00ff6-126">Similitudes entre las líneas de teléfono privadas y las líneas de teléfono principales</span><span class="sxs-lookup"><span data-stu-id="00ff6-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="00ff6-127">Las llamadas no respondidas realizas a una línea de teléfono privada se enrutan a la misma bandeja de entrada de correo de voz de la línea telefónica principal (si el correo de voz está habilitado).</span><span class="sxs-lookup"><span data-stu-id="00ff6-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="00ff6-128">El estacionamiento de llamadas y la atención de llamadas funcionan con líneas de teléfono privadas exactamente de la misma manera que con la línea de teléfono principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="00ff6-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="00ff6-129">Cuando se habilitan las llamadas simultáneas en la línea de teléfono principal de un usuario, también se habilita en la línea de teléfono privada.</span><span class="sxs-lookup"><span data-stu-id="00ff6-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="00ff6-130">El número de teléfono de una línea de teléfono privada se registra en el registro detallado de llamadas de la misma manera que el número de teléfono de la línea de teléfono principal de un usuario, pero con una indicación de que se trata de un número de teléfono privado.</span><span class="sxs-lookup"><span data-stu-id="00ff6-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="00ff6-131">Después de que un usuario responda a una llamada en una línea de teléfono privada, la llamada se trata igual que una llamada en la línea de teléfono principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="00ff6-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="00ff6-132">Por ejemplo, si un usuario que recibe una llamada en una línea de teléfono privada reenvía la llamada o invita a otras personas a una llamada de conferencia, el nombre del usuario aparece en Skype Empresarial y el número de teléfono de la línea de teléfono principal del usuario aparece en el identificador de llamada.</span><span class="sxs-lookup"><span data-stu-id="00ff6-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="00ff6-133">Los usuarios pueden desviar una llamada de la línea de teléfono privada (redirigir la llamada a otro destino, como un teléfono móvil o un teléfono particular, antes de responder) de la misma forma que con una línea de teléfono principal.</span><span class="sxs-lookup"><span data-stu-id="00ff6-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="00ff6-134">Cuando una llamada a una línea privada se enruta a un número de teléfono alternativo, el número de teléfono de la línea de teléfono privada se pone a disposición del número de teléfono alternativo y puede mostrarse en los registros de dicho número.</span><span class="sxs-lookup"><span data-stu-id="00ff6-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="00ff6-135">Las llamadas desde una conferencia a la línea de teléfono privada no tendrán una indicación de  *línea*  privada en la notificación del sistema entrante.</span><span class="sxs-lookup"><span data-stu-id="00ff6-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="00ff6-136">Administración de líneas de teléfono privadas</span><span class="sxs-lookup"><span data-stu-id="00ff6-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="00ff6-p107">Además de los aspectos técnicos de la creación y administración de líneas de teléfono privadas, tendrá que establecer procedimientos administrativos. Entre estos, se incluye la determinación de directivas para indicar qué personas de la organización pueden obtener una línea privada, la creación y administración de listas de personas y sus líneas de teléfono (porque los números de teléfono de líneas privadas no se almacenan en Active Directory), la posible creación de un directorio de teléfonos privados para ejecutivos, la preparación de formación para usuarios y otras tareas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="00ff6-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="00ff6-p108">La línea telefónica privada se almacena en Active Directory como un atributo msRTCSIP-PrivateLine en el objeto de usuario. De forma predeterminada los miembros del grupo Usuarios autenticados tiene acceso de lectura para este atributo.</span><span class="sxs-lookup"><span data-stu-id="00ff6-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="00ff6-141">Asignación de números de teléfono</span><span class="sxs-lookup"><span data-stu-id="00ff6-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="00ff6-142">Las cuentas para los nuevos usuarios que necesitan líneas de teléfono privadas se crean de la misma manera que las cuentas sin líneas de teléfono privadas, mediante el Panel de control de Skype Empresarial Server o el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="00ff6-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="00ff6-143">Use el cmdlet **Set-CsUser** en el Shell de administración de Skype Empresarial Server para asignar un número de teléfono a una línea de teléfono privada para un usuario, por ejemplo, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="00ff6-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="00ff6-144">Los números de teléfono de las líneas de teléfono privadas pueden tener entre 3 y 15 números de longitud y deben ir precedidos del prefijo "TEL:".</span><span class="sxs-lookup"><span data-stu-id="00ff6-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="00ff6-145">Pueden tener cualquier código de área y de país, siempre que la organización disponga de llamada directa a la extensión para dicho código de área y de país/región.</span><span class="sxs-lookup"><span data-stu-id="00ff6-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="00ff6-146">Para obtener más información sobre los cmdlets y el Shell de administración de Skype Empresarial Server, consulte la documentación del Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="00ff6-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="00ff6-147">Líneas de teléfono privadas en implementaciones mezcladas</span><span class="sxs-lookup"><span data-stu-id="00ff6-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="00ff6-148">Las líneas de teléfono privadas solo deben configurarse para las implementaciones de Skype Empresarial Server o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00ff6-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="00ff6-149">En una implementación en la que hay servidores que ejecutan versiones anteriores de Lync Server, cuando un usuario de una versión anterior intenta llamar a una línea de teléfono privada, se produce un error en el enrutamiento de la llamada porque el servidor no puede realizar una búsqueda inversa de números en una línea de teléfono privada.</span><span class="sxs-lookup"><span data-stu-id="00ff6-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

