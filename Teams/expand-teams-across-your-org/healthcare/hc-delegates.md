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
description: Obtenga información sobre cómo un usuario con el estado No molestar o con el estado No molestar puede establecer explícitamente a otro usuario como delegado en su mensaje de estado.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac23afbea7f452967718a8c2d86fd4d36584492d
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790472"
---
# <a name="message-delegation"></a><span data-ttu-id="ad774-103">Delegación de mensajes</span><span class="sxs-lookup"><span data-stu-id="ad774-103">Message delegation</span></span>

<span data-ttu-id="ad774-104">Un usuario ya puede establecer explícitamente su estado en "No molestar" o "No molestar" y proporcionar texto personalizado.</span><span class="sxs-lookup"><span data-stu-id="ad774-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="ad774-105">La característica de delegación de mensajes funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ad774-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="ad774-106">Un usuario @username menciona a otro usuario en parte de un mensaje de estado de texto, lo que sugiere que, aunque no estén disponibles, los usuarios que deban ponerse en contacto con él en su lugar se pondrán en contacto con el @username mencionado.</span><span class="sxs-lookup"><span data-stu-id="ad774-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="ad774-107">A la persona que se le ha asignado como delegado se le notifica que se le ha nominado para ser delegado.</span><span class="sxs-lookup"><span data-stu-id="ad774-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="ad774-108">Alguien que está intentando ponerse en contacto con el primer usuario puede mantener el puntero sobre el delegado nominado y, en su lugar, enviar mensajes fácilmente al delegado.</span><span class="sxs-lookup"><span data-stu-id="ad774-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="ad774-109">Se trata de un proceso iniciado por el usuario en el cliente y no es necesaria la participación del administrador para habilitar la característica.</span><span class="sxs-lookup"><span data-stu-id="ad774-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="ad774-110">Escenario de uso de la delegación en el sector sanitario</span><span class="sxs-lookup"><span data-stu-id="ad774-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="ad774-111">*Ejemplo de uso sin configurar delegados:*  El Dr. Franco Piccio está en llamada en el departamento de radioactividad.</span><span class="sxs-lookup"><span data-stu-id="ad774-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="ad774-112">Recibe una llamada personal urgente y debe alejerse durante las próximas horas.</span><span class="sxs-lookup"><span data-stu-id="ad774-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="ad774-113">Le pide a uno de sus compañeros del departamento de radiología, el Dr. Lena Ehrle, que lo cubra mientras está desaparecido.</span><span class="sxs-lookup"><span data-stu-id="ad774-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="ad774-114">Informalmente, entrega su página al Dr. Ehrle, que escucha mensajes urgentes y hace ping al pager y los responde en nombre del Dr. Piccio, además de sus responsabilidades actuales.</span><span class="sxs-lookup"><span data-stu-id="ad774-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="ad774-115">Es posible que otros miembros del equipo no se percatan de que ha sucedido una delegación informal y se está confusión en la atención de un paciente.</span><span class="sxs-lookup"><span data-stu-id="ad774-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="ad774-116">*Ejemplo de uso con la configuración de delegados:* El Dr. Franco Piccio está en llamada en el departamento de radioactividad.</span><span class="sxs-lookup"><span data-stu-id="ad774-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="ad774-117">Recibe una llamada personal urgente y debe alejerse durante las próximas horas.</span><span class="sxs-lookup"><span data-stu-id="ad774-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="ad774-118">Le pide a uno de sus compañeros del departamento de radiología, el Dr. Lena Ehrle que lo cubra mientras está desaparecido.</span><span class="sxs-lookup"><span data-stu-id="ad774-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="ad774-119">Cambia su mensaje de estado personalizado para decir algo similar a "No estoy disponible para las próximas horas.</span><span class="sxs-lookup"><span data-stu-id="ad774-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="ad774-120">Póngase en contacto @DrEhrle emergencia".</span><span class="sxs-lookup"><span data-stu-id="ad774-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="ad774-121">Los demás miembros del equipo se percatan de que la delegación se ha producido al intentar ponerse en contacto con el Dr. Piccio, para que ahora sepan que se debe comunicar con el Dr. Ehrle mientras tanto.</span><span class="sxs-lookup"><span data-stu-id="ad774-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="ad774-122">Poco o ninguna confusión se ve con la atención de un paciente.</span><span class="sxs-lookup"><span data-stu-id="ad774-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="ad774-123">Impacto de los modos de coexistencia en el estado del usuario en el cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="ad774-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="ad774-124">Los administradores deben tener en cuenta que las notas de estado y los comportamientos de las menciones de delegación dependerán en parte del modo coexistencia de un usuario.</span><span class="sxs-lookup"><span data-stu-id="ad774-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user's co-existence mode.</span></span> <span data-ttu-id="ad774-125">Esta matriz le muestra las posibilidades:</span><span class="sxs-lookup"><span data-stu-id="ad774-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="ad774-126">Co-Existence privado</span><span class="sxs-lookup"><span data-stu-id="ad774-126">Co-Existence Mode</span></span> | <span data-ttu-id="ad774-127">Comportamiento esperado</span><span class="sxs-lookup"><span data-stu-id="ad774-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="ad774-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="ad774-128">TeamsOnly</span></span> |<span data-ttu-id="ad774-129">Los usuarios solo pueden establecer una nota desde Teams.</span><span class="sxs-lookup"><span data-stu-id="ad774-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="ad774-130">La nota de Teams del usuario está visible en Teams & SfB.</span><span class="sxs-lookup"><span data-stu-id="ad774-130">User's Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="ad774-131">Aplicaciones aisladas</span><span class="sxs-lookup"><span data-stu-id="ad774-131">Islands</span></span> | <span data-ttu-id="ad774-132">El conjunto de notas del usuario en Teams solo se puede ver en Teams.</span><span class="sxs-lookup"><span data-stu-id="ad774-132">User's note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="ad774-133">El conjunto de notas del usuario en SfB solo visible en SfB</span><span class="sxs-lookup"><span data-stu-id="ad774-133">User's note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="ad774-134">Modos sfB\*</span><span class="sxs-lookup"><span data-stu-id="ad774-134">SfB\* modes</span></span> | <span data-ttu-id="ad774-135">Los usuarios pueden establecer una nota solo desde SfB.</span><span class="sxs-lookup"><span data-stu-id="ad774-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="ad774-136">La nota de SfB del usuario está visible en SfB & Teams.</span><span class="sxs-lookup"><span data-stu-id="ad774-136">User's SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="ad774-137">Un usuario solo puede establecer una nota en Teams si su modo es TeamsOnly o Islas.</span><span class="sxs-lookup"><span data-stu-id="ad774-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="ad774-138">Mostrar notas configuradas en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ad774-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="ad774-139">No hay ninguna indicación visual de que skype empresarial haya establecido una nota.</span><span class="sxs-lookup"><span data-stu-id="ad774-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="ad774-140">Skype Empresarial no aplica un límite de caracteres a las notas de estado.</span><span class="sxs-lookup"><span data-stu-id="ad774-140">Skype for Business doesn't enforce a character limit on status notes.</span></span> <span data-ttu-id="ad774-141">Microsoft Teams solo mostrará los primeros 280 caracteres de un conjunto de notas de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ad774-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="ad774-142">Los puntos suspensivos (...) al final de una nota indican truncamiento.</span><span class="sxs-lookup"><span data-stu-id="ad774-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="ad774-143">Skype Empresarial no admite la caducidad de las notas.</span><span class="sxs-lookup"><span data-stu-id="ad774-143">Skype for Business doesn't support expiry times for notes.</span></span>

<span data-ttu-id="ad774-144">La migración de notas de Skype Empresarial a Teams no se admite cuando un usuario se actualiza al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ad774-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ad774-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="ad774-145">Related topics</span></span>

[<span data-ttu-id="ad774-146">Coexistencia con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="ad774-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
