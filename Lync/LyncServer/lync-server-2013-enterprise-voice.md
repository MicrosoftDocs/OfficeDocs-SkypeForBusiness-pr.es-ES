---
title: Lync Server 2013 Enterprise Voice
description: Lync Server 2013 Enterprise Voice.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enterprise Voice
ms:assetid: c9da8099-6f4f-4346-ac67-f041bb96072c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg417163(v=OCS.15)
ms:contentKeyID: 48185404
ms.date: 04/08/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11f2497cf99319317a75b81f02ed0d8ca797fbf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574236"
---
# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="199e4-103">Telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="199e4-103">Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="199e4-104">_**Última modificación del tema:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="199e4-104">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="199e4-105">Con la telefonía IP empresarial, Lync Server ofrece una oferta de protocolo de voz sobre IP (VoIP) independiente para mejorar o reemplazar sistemas tradicionales de central de conmutación (PBX).</span><span class="sxs-lookup"><span data-stu-id="199e4-105">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="199e4-106">Los usuarios de Telefonía IP empresarial pueden llamar a compañeros de la red de VoIP o PBX de la organización y pueden llamar a números de teléfono convencionales fuera de la organización.</span><span class="sxs-lookup"><span data-stu-id="199e4-106">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="199e4-107">La solución de telefonía IP empresarial incluye características de llamada comunes como Answer, Forward, transfer, Hold, desvía, Release and Park y la llamada mejorada de 9-1-1 (E9-1-1) (E9-1-1 solo está disponible en Estados Unidos). La telefonía IP empresarial también admite una amplia gama de dispositivos IP y USB actuales y antiguos.</span><span class="sxs-lookup"><span data-stu-id="199e4-107">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="199e4-108">Enviar y recibir llamadas</span><span class="sxs-lookup"><span data-stu-id="199e4-108">Placing and Receiving Calls</span></span>

<span data-ttu-id="199e4-109">Con Lync, los usuarios pueden realizar llamadas escribiendo un nombre o número de teléfono en el teclado o usando un teclado de marcado que se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="199e4-109">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="199e4-110">Asimismo, los usuarios pueden iniciar llamadas directamente desde su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="199e4-110">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="199e4-111">También puede implementar dispositivos de Lync Phone Edition, que son dispositivos de telefonía IP independientes proporcionados por los socios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="199e4-111">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="199e4-112">Los usuarios pueden tener varios dispositivos telefónicos registrados en Lync Server y cambiar entre ellos fácilmente.</span><span class="sxs-lookup"><span data-stu-id="199e4-112">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="199e4-113">Los usuarios reciben una alerta en todos sus dispositivos de forma simultánea cuando se recibe una llamada, con tonos de llamada personalizables en los dispositivos telefónicos IP y una notificación similar de mensaje instantáneo en sus equipos.</span><span class="sxs-lookup"><span data-stu-id="199e4-113">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="199e4-114">Los usuarios también pueden establecer un único número de teléfono que conecta con su teléfono de escritorio, equipo y teléfono móvil, de forma que pueden responder allí donde estén.</span><span class="sxs-lookup"><span data-stu-id="199e4-114">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="199e4-115">Características básicas de llamada</span><span class="sxs-lookup"><span data-stu-id="199e4-115">Basic Call Features</span></span>

<span data-ttu-id="199e4-p103">Mientras atiende una llamada, un usuario puede responder a llamadas entrantes adicionales o realizar llamadas y la llamada activa en esos momentos pasa a estar en espera de forma automática. Las llamadas se pueden transferir de un usuario a otro, bien de forma directa o después de que el primer usuario hable en privado con el segundo. Además, los usuarios pueden transferir llamadas a otro dispositivo; por ejemplo, podrían transferir una llamada activa a su teléfono móvil si necesitan salir de la oficina.</span><span class="sxs-lookup"><span data-stu-id="199e4-p103">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold. Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user. Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="199e4-119">Comunicaciones enriquecidas</span><span class="sxs-lookup"><span data-stu-id="199e4-119">Richer Communications</span></span>

<span data-ttu-id="199e4-120">Al hablar con otro usuario con Lync, los usuarios pueden agregar fácilmente texto, vídeo o uso compartido de escritorio a la llamada.</span><span class="sxs-lookup"><span data-stu-id="199e4-120">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="199e4-121">La característica do-not-molestar se integra con la configuración de presencia en Lync.</span><span class="sxs-lookup"><span data-stu-id="199e4-121">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="199e4-122">Con mensajería unificada (MU) de Exchange, Lync y Lync Server se integran con Microsoft Exchange Server 2013 y Microsoft Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="199e4-122">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="199e4-123">Los usuarios pueden ver si tienen correo de voz nuevo tanto en la ventana de Lync como en el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="199e4-123">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="199e4-124">Si están en el correo electrónico, pueden hacer clic en un mensaje de correo electrónico para reproducir el audio del correo de voz o ver una transcripción del mensaje del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="199e4-124">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="199e4-125">Características avanzadas de llamada</span><span class="sxs-lookup"><span data-stu-id="199e4-125">Advanced Calling Features</span></span>

<span data-ttu-id="199e4-126">La telefonía IP empresarial también incluye varias características avanzadas de llamada, como la delegación de llamadas de Lync, las llamadas de equipo, la recogida de llamadas de grupo y los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="199e4-126">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="199e4-127">La delegación de llamadas de Lync permite a los usuarios delegar el control de la llamada a uno **Tools** o más asistentes; para ello, vaya a \> **Opciones** de \> **reenvío de llamadas**de herramientas.</span><span class="sxs-lookup"><span data-stu-id="199e4-127">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="199e4-128">El delegado puede llevar a cabo múltiples tareas de llamada en nombre del usuario, lo cual incluye la selección de llamadas, envío de llamadas e inicio de conferencias.</span><span class="sxs-lookup"><span data-stu-id="199e4-128">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="199e4-129">Es posible que quiera buscar otra característica con nombre similar, Delegación de calendarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="199e4-129">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="199e4-130">No requiere la característica Enterprise Voice y permite a los usuarios programar reuniones de Lync en línea desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="199e4-130">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="199e4-131">Si ha llegado a esta información, le recomendamos que consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A> para obtener información sobre cómo habilitar la sincronización de delegados de Exchange.</span><span class="sxs-lookup"><span data-stu-id="199e4-131">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="199e4-132">Las llamadas de equipo permiten que un usuario tenga que llamar simultáneamente a los teléfonos de los compañeros de equipo para que cualquier persona del equipo pueda responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="199e4-132">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="199e4-133">Recogida de llamadas grupales, una nueva característica de las actualizaciones acumulativas de Lync Server 2013: febrero de 2013, permite a los usuarios responder llamadas entrantes a sus colegas desde sus propios teléfonos.</span><span class="sxs-lookup"><span data-stu-id="199e4-133">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="199e4-134">La recogida de llamadas de grupo difiere de las llamadas de equipo principalmente en que una llamada entrante suena solo en el teléfono del destinatario previsto, pero cualquier otro usuario puede contestarla marcando un número de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="199e4-134">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="199e4-p109">Los grupos de respuesta pueden establecer el envío a cola y enrutamiento inteligente de llamadas para agentes designados. Entre los usos habituales se incluyen la asistencia técnica de TI, línea directa a recursos humanos y otros centros de contacto internos.</span><span class="sxs-lookup"><span data-stu-id="199e4-p109">Response Groups can be set up for queuing and intelligently routing calls to designated agents. Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="199e4-137">Administración de la Telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="199e4-137">Enterprise Voice Administration</span></span>

<span data-ttu-id="199e4-138">Lync Server usa estándares y interfaces publicadas para interoperar con la infraestructura existente.</span><span class="sxs-lookup"><span data-stu-id="199e4-138">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="199e4-139">Admite las opciones de puerta de enlace y SIP (como la conexión basada en troncos SIP) para la interconexión a sistemas PBX IP y las redes RTC, de forma que se pueden migrar usuarios a Telefonía IP empresarial de forma continuada, a la vez que se minimiza el riesgo de interrupción.</span><span class="sxs-lookup"><span data-stu-id="199e4-139">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="199e4-140">Lync Server admite códecs tradicionales como G. 711, G. 722 y G. 723.1 para la interoperabilidad con las soluciones VoIP tradicionales.</span><span class="sxs-lookup"><span data-stu-id="199e4-140">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="199e4-141">Con el control de admisión de llamadas (CAC), los administradores pueden establecer límites en la cantidad de tráfico de voz y vídeo de Lync Server que se transporta en vínculos de red restringidos y especificar la acción que se realizará si una nueva llamada superará el límite.</span><span class="sxs-lookup"><span data-stu-id="199e4-141">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="199e4-142">Las acciones pueden incluir el enrutamiento hacia una ruta alternativa o rechazar la llamada.</span><span class="sxs-lookup"><span data-stu-id="199e4-142">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="199e4-143">Lync Server funciona con aplicaciones de sucursal con funciones de supervivencia de terceros para proporcionar servicios de llamadas locales y conexiones a RTC en las sucursales, en caso de que se produzca un error de WAN en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="199e4-143">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

