---
title: 'Lync Server 2013: características y funciones de los servidores front-end, la mensajería instantánea y la presencia'
description: 'Lync Server 2013: características y funciones de los servidores front-end, la mensajería instantánea y la presencia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c8bc3db255228da3366eb5aa142cd5adc233d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543416"
---
# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="b3e81-103">Características y funciones de los servidores front-end, la mensajería instantánea y la presencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3e81-103">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3e81-104">_**Última modificación del tema:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="b3e81-104">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="b3e81-105">Los servidores front-end proporcionan la funcionalidad de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3e81-105">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="b3e81-106">Hay dos ediciones disponibles: Lync Server Enterprise Edition, que está diseñado principalmente para organizaciones más grandes y Lync Server Standard Edition, diseñado principalmente para organizaciones más pequeñas que quieren una Investement de hardware más pequeña y no requieren alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b3e81-106">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="b3e81-107">Ambas ediciones admiten todas las cargas de trabajo de Lync Server, incluidas la mensajería instantánea, la presencia, la Conferencia y la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="b3e81-107">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="b3e81-p102">La mensajería instantánea (MI) permite a los usuarios comunicarse entre sí en tiempo real desde sus equipos y mediante mensajes basados en texto. Se admiten sesiones de mensajería instantánea con dos participantes y con varios participantes. Un participante de una conversación de mensajería instantánea entre dos participantes puede agregar a la conversación a un tercer participante en cualquier momento. Cuando esto ocurre, la ventana Conversación cambia para admitir características de conferencia.</span><span class="sxs-lookup"><span data-stu-id="b3e81-p102">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b3e81-112">Los clientes de Lync y Communicator cuando participan en una comunicación de una a una, a menudo se denominan de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="b3e81-112">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="b3e81-113">Técnicamente, los dos clientes se comunican en una conversación de una a una, con la unidad de control multipunto (IMMCU) de mensajería instantánea en la parte central.</span><span class="sxs-lookup"><span data-stu-id="b3e81-113">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="b3e81-114">IMMCU es un componente del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b3e81-114">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="b3e81-115">La colocación de IMMCU en el flujo de trabajo de comunicación necesario permite el registro detallado de llamadas y otras características que permite el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="b3e81-115">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="b3e81-116">La comunicación es desde un puerto de origen dinámico en el cliente al puerto del servidor front-end TLS/TCP/5061 (asumiendo el uso de la seguridad de la capa de transporte recomendada).</span><span class="sxs-lookup"><span data-stu-id="b3e81-116">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="b3e81-117">Por diseño, la comunicación punto a punto (así como la mensajería instantánea de varios participantes) solo es posible cuando Lync Server y el IMMCU está activo y disponible.</span><span class="sxs-lookup"><span data-stu-id="b3e81-117">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="b3e81-118">*Presencia* proporciona información a los usuarios acerca del estado de los otros usuarios en la red.</span><span class="sxs-lookup"><span data-stu-id="b3e81-118">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="b3e81-119">El estado de presencia de un usuario proporciona información que ayuda a los demás usuarios a decidir si deben intentar ponerse en contacto con él y si deben usar la mensajería instantánea, el teléfono o el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="b3e81-119">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="b3e81-120">El estado de presencia fomenta la comunicación instantánea cada vez que sea posible, pero también proporciona información sobre si un usuario está en una reunión o fuera de la oficina, indicando que la comunicación instantánea no es posible.</span><span class="sxs-lookup"><span data-stu-id="b3e81-120">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="b3e81-121">Este estado de presencia se muestra como un icono de presencia en Lync y en otras aplicaciones para la presencia, incluido el cliente de mensajería y colaboración de Microsoft Outlook, las tecnologías de Microsoft SharePoint, Microsoft Word y el software de hoja de cálculo de Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b3e81-121">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="b3e81-122">El icono del estado de presencia representa la disponibilidad y la disposición de comunicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="b3e81-122">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

