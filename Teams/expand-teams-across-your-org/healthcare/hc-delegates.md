---
title: Delegación de mensajes
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: acolonna
description: Un usuario puede establecer explícitamente otro usuario como delegado en su mensaje de estado.
ms.openlocfilehash: ec1f590cad4ada605b4a487d982b3a2459ecb5f2
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827788"
---
# <a name="message-delegation"></a><span data-ttu-id="995a7-103">Delegación de mensajes</span><span class="sxs-lookup"><span data-stu-id="995a7-103">Message delegation</span></span>

<span data-ttu-id="995a7-104">Un usuario ya puede definir de forma explícita su estado como ausente o no molestar, y proporcionar texto personalizado.</span><span class="sxs-lookup"><span data-stu-id="995a7-104">A user can already explicitly set their status to Away or Do not Disturb, and provide custom text.</span></span> <span data-ttu-id="995a7-105">La característica de delegación de mensajes funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="995a7-105">The message delegation feature works as follows:</span></span>

1. <span data-ttu-id="995a7-106">Un usuario @username mencione a otro usuario en un mensaje de estado de texto, lo que sugiere que no se les puede comunicar con ellos en su lugar, póngase en contacto con el @username Usuario mencionado.</span><span class="sxs-lookup"><span data-stu-id="995a7-106">A user @username mentions another user in part of a text status message, suggesting that while they are unavailable people who want to contact them instead contact the @username mentioned user.</span></span>
2. <span data-ttu-id="995a7-107">La persona a la que se le ha asignado como delegado recibe la notificación de que se ha designado como delegado.</span><span class="sxs-lookup"><span data-stu-id="995a7-107">The person who has been assigned as a delegate is notified that they were nominated to be a delegate.</span></span>
3. <span data-ttu-id="995a7-108">Alguien que está intentando ponerse en contacto con el primer usuario puede desplazar el puntero sobre el delegado nominado y enviarle fácilmente un mensaje al delegado.</span><span class="sxs-lookup"><span data-stu-id="995a7-108">Someone trying to contact the first user can then hover over the nominated delegate and easily message the delegate instead.</span></span>  

<span data-ttu-id="995a7-109">Este es un proceso iniciado por el usuario en el cliente, y no es necesario que intervenga el administrador para habilitar la característica.</span><span class="sxs-lookup"><span data-stu-id="995a7-109">This is a user-initiated process in the client, and no Admin involvement is required to enable the feature.</span></span> 

## <a name="delegation-use-scenario-in-healthcare"></a><span data-ttu-id="995a7-110">Escenario de uso de delegación en el cuidado de la salud</span><span class="sxs-lookup"><span data-stu-id="995a7-110">Delegation use scenario in Healthcare</span></span>

<span data-ttu-id="995a7-111">*Ejemplo de uso sin establecer delegados:*  Dr. Franco Piccio es una llamada en el Departamento de radiología.</span><span class="sxs-lookup"><span data-stu-id="995a7-111">*Usage example without setting delegates:*  Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="995a7-112">Recibe una llamada personal urgente y tiene que desplazarse por las próximas horas.</span><span class="sxs-lookup"><span data-stu-id="995a7-112">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="995a7-113">Usted pide a uno de sus colegas en el Departamento de radiología, Dr. Lena Ehrle, que lo cubre mientras está fuera.</span><span class="sxs-lookup"><span data-stu-id="995a7-113">He asks one of his peers in the radiology department, Dr. Lena Ehrle, to cover for him while he is gone.</span></span> <span data-ttu-id="995a7-114">Informando a su buscapersonas a Dr. Ehrle, que está escuchando mensajes urgentes y pings en el buscapersonas y responde a ellos en nombre de Dr. Piccio además de sus responsabilidades actuales.</span><span class="sxs-lookup"><span data-stu-id="995a7-114">He informally hands over his pager to Dr. Ehrle, who is listening for urgent messages and pings on the pager and responds to them on behalf of Dr. Piccio in addition to her current responsibilities.</span></span> <span data-ttu-id="995a7-115">Es posible que otros miembros del equipo no se den cuenta de que la delegación informal se produjo, y confusiones se comparan con el cuidado de un paciente.</span><span class="sxs-lookup"><span data-stu-id="995a7-115">Others on the team may not realize the informal delegation happened, and confusion ensues with a patient's care.</span></span>

<span data-ttu-id="995a7-116">*Ejemplo de uso con la configuración de delegados:* Dr. Franco Piccio es una llamada en el Departamento de radiología.</span><span class="sxs-lookup"><span data-stu-id="995a7-116">*Usage example with setting delegates:* Dr. Franco Piccio is on-call at the radiology department.</span></span> <span data-ttu-id="995a7-117">Recibe una llamada personal urgente y tiene que desplazarse por las próximas horas.</span><span class="sxs-lookup"><span data-stu-id="995a7-117">He receives an urgent personal call and has to step away for the next couple of hours.</span></span> <span data-ttu-id="995a7-118">Usted pide a uno de sus colegas en el Departamento de radiología, Dr. Lena Ehrle que lo cubra mientras está fuera.</span><span class="sxs-lookup"><span data-stu-id="995a7-118">He asks one of his peers in the radiology department, Dr. Lena Ehrle to cover for him while he is gone.</span></span> <span data-ttu-id="995a7-119">Cambia su mensaje de estado personalizado para que diga algo similar a "no estoy disponible durante las próximas horas.</span><span class="sxs-lookup"><span data-stu-id="995a7-119">He changes his custom status message to say something similar to "I am unavailable for the next few hours.</span></span> <span data-ttu-id="995a7-120">Comunícate @DrEhrle cualquier emergencia.</span><span class="sxs-lookup"><span data-stu-id="995a7-120">Please contact @DrEhrle for any emergencies."</span></span>  <span data-ttu-id="995a7-121">Otros miembros del equipo se dan cuenta de que la delegación se produjo porque está intentando ponerse en contacto con Dr. Piccio, por lo que ahora saben comunicarse con Dr. Ehrle mientras tanto.</span><span class="sxs-lookup"><span data-stu-id="995a7-121">Others on the team realize the delegation happened as they're attempting to contact Dr. Piccio, so they now know to contact Dr. Ehrle in the meantime.</span></span> <span data-ttu-id="995a7-122">El cuidado de un paciente tiene poca o ninguna confusión.</span><span class="sxs-lookup"><span data-stu-id="995a7-122">Little to no confusion ensues with a patient's care.</span></span>

## <a name="impact-of-co-existence-modes-on-user-status-in-the-teams-client"></a><span data-ttu-id="995a7-123">Impacto de los modos de coexistencia en el estado del usuario en el cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="995a7-123">Impact of co-existence modes on user status in the Teams client</span></span>

<span data-ttu-id="995a7-124">Los administradores deben tener en cuenta que los comportamientos de notas de estado y de la delegación dependen en parte del modo de coexistencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="995a7-124">Admins should be aware that status notes and delegation mention behaviors will depend partly on a user’s co-existence mode.</span></span> <span data-ttu-id="995a7-125">Esta matriz muestra las posibilidades:</span><span class="sxs-lookup"><span data-stu-id="995a7-125">This matrix shows the possibilities:</span></span>

|<span data-ttu-id="995a7-126">Modo de coexistencia</span><span class="sxs-lookup"><span data-stu-id="995a7-126">Co-Existence Mode</span></span> | <span data-ttu-id="995a7-127">Comportamiento esperado</span><span class="sxs-lookup"><span data-stu-id="995a7-127">Expected Behavior</span></span>|
|---|---|
|<span data-ttu-id="995a7-128">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="995a7-128">TeamsOnly</span></span> |<span data-ttu-id="995a7-129">Los usuarios solo pueden establecer una nota desde Teams.</span><span class="sxs-lookup"><span data-stu-id="995a7-129">Users can set a note only from Teams.</span></span> <br> <span data-ttu-id="995a7-130">La nota de Teams del usuario está visible en Teams & SfB.</span><span class="sxs-lookup"><span data-stu-id="995a7-130">User’s Teams note is visible in Teams & SfB.</span></span> |
|<span data-ttu-id="995a7-131">Aplicaciones aisladas</span><span class="sxs-lookup"><span data-stu-id="995a7-131">Islands</span></span> | <span data-ttu-id="995a7-132">La nota del usuario se establece en Teams visible solo en Teams.</span><span class="sxs-lookup"><span data-stu-id="995a7-132">User’s note set in Teams visible only in Teams.</span></span> <br> <span data-ttu-id="995a7-133">La nota del usuario se establece en SfB visible solo en SfB</span><span class="sxs-lookup"><span data-stu-id="995a7-133">User’s note set in SfB visible only in SfB</span></span> |
|<span data-ttu-id="995a7-134">Modos SfB \*</span><span class="sxs-lookup"><span data-stu-id="995a7-134">SfB\* modes</span></span> | <span data-ttu-id="995a7-135">Los usuarios solo pueden establecer una nota desde SfB.</span><span class="sxs-lookup"><span data-stu-id="995a7-135">Users can set a note only from SfB.</span></span> <br> <span data-ttu-id="995a7-136">La nota de SfB del usuario está visible en los equipos de SfB &.</span><span class="sxs-lookup"><span data-stu-id="995a7-136">User’s SfB note is visible in SfB & Teams.</span></span>  |
|||

<span data-ttu-id="995a7-137">Un usuario solo puede establecer una nota en Teams si su modo es TeamsOnly o islas.</span><span class="sxs-lookup"><span data-stu-id="995a7-137">A user can only set a note in Teams if their mode is TeamsOnly or Islands.</span></span>  

### <a name="displaying-notes-set-in-skype-for-business"></a><span data-ttu-id="995a7-138">Mostrar notas establecidas en Skype empresarial</span><span class="sxs-lookup"><span data-stu-id="995a7-138">Displaying notes set in Skype for Business</span></span>
  
<span data-ttu-id="995a7-139">No hay ninguna indicación visual de que una nota se haya establecido desde Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="995a7-139">There is no visual indication that a note was set from Skype for Business.</span></span>

<span data-ttu-id="995a7-140">Skype empresarial no impone un límite de caracteres en las notas de estado.</span><span class="sxs-lookup"><span data-stu-id="995a7-140">Skype for Business doesn’t enforce a character limit on status notes.</span></span> <span data-ttu-id="995a7-141">Microsoft Teams solo mostrará los primeros 280 caracteres de una nota establecida desde Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="995a7-141">Microsoft Teams will only display the first 280 characters of a note set from Skype for Business.</span></span> <span data-ttu-id="995a7-142">Una elipse (...) al final de una nota indica que se ha truncado.</span><span class="sxs-lookup"><span data-stu-id="995a7-142">An ellipse (…) at the end of a note indicates truncation.</span></span>
  
<span data-ttu-id="995a7-143">Skype empresarial no admite tiempos de caducidad para las notas.</span><span class="sxs-lookup"><span data-stu-id="995a7-143">Skype for Business doesn’t support expiry times for notes.</span></span>

<span data-ttu-id="995a7-144">La migración de notas de Skype empresarial a teams no es compatible cuando un usuario se actualiza al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="995a7-144">Migration of notes from Skype for Business to Teams is not supported when a user is upgraded to TeamsOnly mode.</span></span>

## <a name="related-topics"></a><span data-ttu-id="995a7-145">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="995a7-145">Related topics</span></span>

[<span data-ttu-id="995a7-146">Coexistencia con Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="995a7-146">Coexistence with Skype for Business</span></span>](../../coexistence-chat-calls-presence.md)
