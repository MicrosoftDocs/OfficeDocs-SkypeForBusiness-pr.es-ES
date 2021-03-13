---
title: Delegación de mensajes
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Obtenga información sobre cómo un usuario con el estado Ausente o No molestar puede establecer explícitamente a otro usuario como delegado en su mensaje de estado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790472"
---
# <a name="message-delegation"></a><span data-ttu-id="cdf87-103">Delegación de mensajes</span><span class="sxs-lookup"><span data-stu-id="cdf87-103">Message delegation</span></span>

<span data-ttu-id="cdf87-104">Un usuario ya puede establecer explícitamente su estado en "Ausente" o "No molestar" y proporcionar texto personalizado.</span><span class="sxs-lookup"><span data-stu-id="cdf87-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="cdf87-105">La característica de delegación de mensajes funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="cdf87-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="cdf87-106">Un usuario @username menciona a otro usuario en parte de un mensaje de estado de texto, lo que indica que, aunque no estén disponibles, los usuarios que quieran ponerse en contacto con él, en su lugar se pondrán en contacto con el @username mencionado.</span><span class="sxs-lookup"><span data-stu-id="cdf87-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="cdf87-107">A la persona que ha sido designada como delegado será notificada de su nominación como delegado.</span><span class="sxs-lookup"><span data-stu-id="cdf87-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="cdf87-108">Alguien que intente ponerse en contacto con el primer usuario puede pasar el ratón por encima del delegado nominado y enviarle un mensaje fácilmente.</span><span class="sxs-lookup"><span data-stu-id="cdf87-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="cdf87-109">Este es un proceso iniciado por el usuario en el cliente y no se requiere participación del administrador para habilitar la característica.</span><span class="sxs-lookup"><span data-stu-id="cdf87-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="cdf87-110">Escenario de uso de delegación en los cuidados de la salud</span><span class="sxs-lookup"><span data-stu-id="cdf87-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="cdf87-111">*Ejemplo de uso sin configurar delegados:*  el Dr. Franco Piccio está de llamadas en el departamento de rayos X.</span><span class="sxs-lookup"><span data-stu-id="cdf87-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="cdf87-112">Recibe una llamada personal urgente y tiene que ausentarse durante las próximas dos horas.</span><span class="sxs-lookup"><span data-stu-id="cdf87-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="cdf87-113">Le pide a uno de sus colegas del departamento de radioactividad, la Dra. Lena Ehrle, que lo cubra mientras está ausente.</span><span class="sxs-lookup"><span data-stu-id="cdf87-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="cdf87-114">Le entrega de forma informal su localizador a la Dra. Ehrle, quien escucha mensajes urgentes y pings en el localizador y responde en nombre del Dr. Piccio, además cumplir con sus responsabilidades actuales.</span><span class="sxs-lookup"><span data-stu-id="cdf87-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="cdf87-115">Es posible que otros miembros del equipo no se den cuenta de que ha sucedido una delegación informal y es seguro que habrá confusiones en el cuidado de un paciente,</span><span class="sxs-lookup"><span data-stu-id="cdf87-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="cdf87-116">*Ejemplo de uso con la configuración de delegados:* el Dr. Franco Piccio está de llamadas en el departamento de rayos X.</span><span class="sxs-lookup"><span data-stu-id="cdf87-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="cdf87-117">Recibe una llamada personal urgente y tiene que ausentarse durante las próximas dos horas.</span><span class="sxs-lookup"><span data-stu-id="cdf87-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="cdf87-118">Le pide a uno de sus compañeros del departamento de rayos X, la Dra. Lena Ehrle, que lo cubra mientras está ausente.</span><span class="sxs-lookup"><span data-stu-id="cdf87-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="cdf87-119">Cambia su mensaje de estado personalizado para decir algo como: "No estoy disponible durante las próximas horas.</span><span class="sxs-lookup"><span data-stu-id="cdf87-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="cdf87-120">Comuníquese con la @DrEhrle para cualquier emergencia".</span><span class="sxs-lookup"><span data-stu-id="cdf87-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="cdf87-121">Otros miembros del equipo se dan cuenta de que la delegación ocurrió cuando intentan ponerse en contacto con el Dr. Piccio, así que ahora saben que tienen que ponerse en contacto con la Dra. Ehrle durante este periodo.</span><span class="sxs-lookup"><span data-stu-id="cdf87-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="cdf87-122">Prácticamente no hay confusiones en cuanto a cuidados del paciente.</span><span class="sxs-lookup"><span data-stu-id="cdf87-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="cdf87-123">Impacto de los modos de coexistencia en el estado del usuario en el cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="cdf87-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="cdf87-124">Los administradores deben tener en cuenta que los comportamientos de las notas de estado y las menciones de delegación dependerán en parte del modo de coexistencia de un usuario.</span><span class="sxs-lookup"><span data-stu-id="cdf87-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="cdf87-125">Esta matriz presenta las posibilidades siguientes:</span><span class="sxs-lookup"><span data-stu-id="cdf87-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="cdf87-126">Modo de coexistencia</span><span class="sxs-lookup"><span data-stu-id="cdf87-126">Co-Existence Mode</span></span> | <span data-ttu-id="cdf87-127">Comportamiento esperado</span><span class="sxs-lookup"><span data-stu-id="cdf87-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="cdf87-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="cdf87-128">TeamsOnly</span></span> |<span data-ttu-id="cdf87-129">Los usuarios solo pueden establecer una nota desde Teams.</span><span class="sxs-lookup"><span data-stu-id="cdf87-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="cdf87-130">La nota de Equipos del usuario está visible en Teams y SfB.</span><span class="sxs-lookup"><span data-stu-id="cdf87-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="cdf87-131">Aplicaciones aisladas</span><span class="sxs-lookup"><span data-stu-id="cdf87-131">Islands</span></span> | <span data-ttu-id="cdf87-132">Conjunto de notas del usuario establecido en Teams visible solo en Teams.</span><span class="sxs-lookup"><span data-stu-id="cdf87-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="cdf87-133">Conjunto de notas del usuario en SesB visible solo en Seb</span><span class="sxs-lookup"><span data-stu-id="cdf87-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="cdf87-134">Modos Sesb\*</span><span class="sxs-lookup"><span data-stu-id="cdf87-134">SfB\* modes</span></span> | <span data-ttu-id="cdf87-135">Los usuarios solo pueden establecer una nota desde SebaB.</span><span class="sxs-lookup"><span data-stu-id="cdf87-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="cdf87-136">La nota de SeB del usuario es visible en Sebab y Equipos.</span><span class="sxs-lookup"><span data-stu-id="cdf87-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="cdf87-137">Un usuario solo puede establecer una nota en Teams si su modo es TeamsOnly o Aplicaciones aisladas.</span><span class="sxs-lookup"><span data-stu-id="cdf87-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="cdf87-138">Mostrar notas establecidas en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="cdf87-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="cdf87-139">No hay nada visual que indica que una nota se ha establecido desde Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="cdf87-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="cdf87-140">Skype Empresarial no exige un límite de caracteres en las notas de estado.</span><span class="sxs-lookup"><span data-stu-id="cdf87-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="cdf87-141">Microsoft Teams solo mostrará los primeros 280 caracteres de un conjunto de notas de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="cdf87-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="cdf87-142">Unos puntos suspensivos (...) al final de una nota indican truncamiento.</span><span class="sxs-lookup"><span data-stu-id="cdf87-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="cdf87-143">Skype Empresarial no admite los tiempos de expiración para las notas.</span><span class="sxs-lookup"><span data-stu-id="cdf87-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="cdf87-144">La migración de notas de Skype Empresarial a Teams no se admite cuando un usuario se actualiza al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="cdf87-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cdf87-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cdf87-145">Related topics</span></span>

[<span data-ttu-id="cdf87-146">Coexistencia con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="cdf87-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
