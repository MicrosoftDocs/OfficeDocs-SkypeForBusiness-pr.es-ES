---
title: 'Lync Server 2013: Planeación del control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2faff08d5517809d4cfb11d00711a146accc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="7e4d6-102">Planeación del control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e4d6-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e4d6-103">_**Última modificación del tema:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="7e4d6-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="7e4d6-104">En Lync Server 2013, la compatibilidad con escenarios de control remoto de llamadas permite a los usuarios controlar sus teléfonos de central de conmutación (PBX) con Lync 2013 en sus equipos de escritorio.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="7e4d6-105">En esta sección se describen las características del control remoto de llamadas y los requisitos necesarios para implementar el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="7e4d6-106">La integración entre una PBX y Lync Server 2013 permite que los usuarios habilitados para el control remoto de llamadas usen la interfaz de usuario (UI) de Lync 2013 para controlar las llamadas en sus teléfonos PBX de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="7e4d6-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7e4d6-107">Las funcionalidades de la PBX que hospeda el teléfono PBX de un usuario son las que determinan en última instancia las características de control remoto de llamadas disponibles para el usuario.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="7e4d6-108">Efectuar una llamada realizada</span><span class="sxs-lookup"><span data-stu-id="7e4d6-108">Make an outgoing call</span></span>

  - <span data-ttu-id="7e4d6-109">Responder a una llamada entrante</span><span class="sxs-lookup"><span data-stu-id="7e4d6-109">Answer an incoming call</span></span>

  - <span data-ttu-id="7e4d6-110">Responder a una llamada entrante con un mensaje instantáneo</span><span class="sxs-lookup"><span data-stu-id="7e4d6-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e4d6-111">Es decir, cuando el número de teléfono del autor de la llamada puede asociarse con una dirección de mensaje instantáneo en la lista global de direcciones (GAL) de la organización, en la lista de contactos de Lync del destinatario de la llamada o en la organización de un socio federado.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="7e4d6-112">Transferir una llamada</span><span class="sxs-lookup"><span data-stu-id="7e4d6-112">Transfer a call</span></span>

  - <span data-ttu-id="7e4d6-113">Desviar una llamada entrante</span><span class="sxs-lookup"><span data-stu-id="7e4d6-113">Forward an incoming call</span></span>

  - <span data-ttu-id="7e4d6-114">Poner llamadas en espera</span><span class="sxs-lookup"><span data-stu-id="7e4d6-114">Place calls on hold</span></span>

  - <span data-ttu-id="7e4d6-115">Alternar entre varias llamadas simultáneas</span><span class="sxs-lookup"><span data-stu-id="7e4d6-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="7e4d6-116">Responder a una segunda llamada mientras se está participando en una llamada (es decir, poner llamadas en espera)</span><span class="sxs-lookup"><span data-stu-id="7e4d6-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="7e4d6-117">Marcar dígitos de tono de marcado de frecuencia múltiple (DTMF)</span><span class="sxs-lookup"><span data-stu-id="7e4d6-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="7e4d6-118">En la ventana Conversación, escribir notas en el programa Microsoft Office OneNote</span><span class="sxs-lookup"><span data-stu-id="7e4d6-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="7e4d6-119">Además, cuando un usuario está habilitado para el control remoto de llamadas, Lync 2013 proporciona al usuario la siguiente información de llamada:</span><span class="sxs-lookup"><span data-stu-id="7e4d6-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="7e4d6-120">Identificación de un llamador por nombre cuando existe el número de teléfono del autor de la llamada en la lista de contactos de un cliente de mensajería y colaboración de Microsoft Office Outlook habilitado para el control de llamadas remotos, la lista de contactos de Lync o la GAL de la organización.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="7e4d6-121">Últimas llamadas entrantes y realizadas, que se guardan en la carpeta Historial de conversaciones de Outlook.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="7e4d6-122">Las notificaciones de llamadas perdidas, que se envían a la carpeta Bandeja de entrada de Outlook del usuario, pero se generan solo si Lync se ejecuta cuando se recibe la llamada entrante.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="7e4d6-123">Control remoto de llamadas y Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="7e4d6-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="7e4d6-124">Aunque las características de control remoto de llamadas son independientes de las características de Enterprise Voice y los usuarios no se pueden habilitar para ambas, la telefonía IP empresarial proporciona un subconjunto de características que también están disponibles para los usuarios que están habilitados para el control remoto de llamadas.</span><span class="sxs-lookup"><span data-stu-id="7e4d6-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="7e4d6-125">Si se implementa la telefonía IP empresarial, los usuarios habilitados para el control remoto de llamadas pueden usar Lync para acceder a las siguientes características de telefonía IP empresarial:</span><span class="sxs-lookup"><span data-stu-id="7e4d6-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="7e4d6-126">Realizar y recibir llamadas de audio a otro cliente de Lync</span><span class="sxs-lookup"><span data-stu-id="7e4d6-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="7e4d6-127">Unirse a la parte de audio de una conferencia creada por un usuario que está habilitado para telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="7e4d6-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7e4d6-128">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7e4d6-128">In This Section</span></span>

  - [<span data-ttu-id="7e4d6-129">Tareas de implementación para el control remoto de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e4d6-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

