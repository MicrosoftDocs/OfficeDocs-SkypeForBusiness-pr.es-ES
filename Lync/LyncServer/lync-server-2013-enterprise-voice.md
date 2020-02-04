---
title: 'Lync Server 2013: Telefonía IP empresarial'
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
ms.openlocfilehash: e62224a7187c54222364045d0ac7b1aa70bccb9c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="45c5d-102">Telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45c5d-102">Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45c5d-103">_**Última modificación del tema:** 2015-04-08_</span><span class="sxs-lookup"><span data-stu-id="45c5d-103">_**Topic Last Modified:** 2015-04-08_</span></span>

<span data-ttu-id="45c5d-104">Con la telefonía IP empresarial, Lync Server ofrece una oferta independiente de protocolo de voz a través de Internet (VoIP) para mejorar o reemplazar sistemas de central de conmutación (PBX) tradicionales.</span><span class="sxs-lookup"><span data-stu-id="45c5d-104">With Enterprise Voice, Lync Server delivers a stand-alone Voice over Internet Protocol (VoIP) offering to enhance or replace traditional private branch exchange (PBX) systems.</span></span> <span data-ttu-id="45c5d-105">Los usuarios de la telefonía IP empresarial pueden llamar a colegas de la red de VoIP o PBX de su organización, y pueden llamar a números de teléfono tradicionales fuera de su organización.</span><span class="sxs-lookup"><span data-stu-id="45c5d-105">Enterprise Voice users can call colleagues on your organization’s VoIP network or PBX, and they can call traditional phone numbers outside your organization.</span></span> <span data-ttu-id="45c5d-106">La solución de voz para empresas incluye características comunes de llamadas, como responder, desviar, transferir, suspender, desviar, soltar y detener, y las llamadas de 9-1-1 (E9-1-1) (E9-1-1 solo está disponible en los Estados Unidos). Enterprise Voice también admite una amplia variedad de dispositivos IP y USB actuales y anteriores.</span><span class="sxs-lookup"><span data-stu-id="45c5d-106">The Enterprise Voice solution includes common calling features such as answer, forward, transfer, hold, divert, release and park, and Enhanced 9-1-1 (E9-1-1) calling (E9-1-1 is available only in the United States.) Enterprise Voice also supports a broad range of current and older IP and USB devices.</span></span>

<div>

## <a name="placing-and-receiving-calls"></a><span data-ttu-id="45c5d-107">Realizar y recibir llamadas</span><span class="sxs-lookup"><span data-stu-id="45c5d-107">Placing and Receiving Calls</span></span>

<span data-ttu-id="45c5d-108">Con Lync, los usuarios pueden realizar llamadas escribiendo un nombre o número de teléfono en el teclado o usando un teclado de marcado que se muestra en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="45c5d-108">Using Lync, users can place calls by typing a name or phone number on their keyboard, or using a dial pad displayed on their screen.</span></span> <span data-ttu-id="45c5d-109">Los usuarios también pueden iniciar llamadas directamente desde su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="45c5d-109">Users can also initiate calls directly from their Contacts list.</span></span> <span data-ttu-id="45c5d-110">También puede implementar dispositivos de Lync Phone Edition, que son dispositivos telefónicos de telefonía IP independientes proporcionados por socios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="45c5d-110">You can also deploy Lync Phone Edition devices, which are stand-alone IP phone devices provided by Microsoft partners.</span></span>

<span data-ttu-id="45c5d-111">Los usuarios pueden tener varios dispositivos de telefonía registrados en Lync Server y cambiar de uno a otro.</span><span class="sxs-lookup"><span data-stu-id="45c5d-111">Users can have multiple phone devices registered with Lync Server, and can switch between them easily.</span></span>

<span data-ttu-id="45c5d-112">Los usuarios reciben alertas de llamadas entrantes en todos sus dispositivos de forma simultánea, con tonos de timbre personalizables en dispositivos telefónicos IP y una notificación similar a la de un mensaje instantáneo en su equipo informático.</span><span class="sxs-lookup"><span data-stu-id="45c5d-112">Users are alerted to incoming calls on all their devices simultaneously, with customizable ringtones on IP phone devices and a notification similar to an instant message on their PC.</span></span>

<span data-ttu-id="45c5d-113">Los usuarios también pueden establecer un único número de teléfono que se conecte a su teléfono de escritorio, equipo informático y teléfono móvil, de modo que se pueda llegar sin importar dónde estén.</span><span class="sxs-lookup"><span data-stu-id="45c5d-113">Users can also set a single telephone number that connects to their desk phone, PC and mobile phone, so they can be reached no matter where they are.</span></span>

</div>

<div>

## <a name="basic-call-features"></a><span data-ttu-id="45c5d-114">Características de llamadas básicas</span><span class="sxs-lookup"><span data-stu-id="45c5d-114">Basic Call Features</span></span>

<span data-ttu-id="45c5d-115">Mientras se encuentra en una llamada, un usuario puede contestar llamadas entrantes adicionales o iniciar llamadas salientes, y la llamada activa existente se coloca automáticamente en espera.</span><span class="sxs-lookup"><span data-stu-id="45c5d-115">While on a call, a user can answer additional incoming calls or initiate outgoing calls, and the existing active call is automatically put on hold.</span></span> <span data-ttu-id="45c5d-116">Las llamadas se pueden transferir de un usuario a otro, ya sea directamente o después de que el primer usuario hable en privado con el segundo usuario.</span><span class="sxs-lookup"><span data-stu-id="45c5d-116">Calls can be transferred from one user to another, either directly or after the first user speaks privately with the second user.</span></span> <span data-ttu-id="45c5d-117">Los usuarios también pueden transferir llamadas a otro dispositivo. por ejemplo, pueden transferir una llamada activa a su teléfono móvil mientras salen de la puerta de su oficina.</span><span class="sxs-lookup"><span data-stu-id="45c5d-117">Users can also transfer calls to another device; for example, they could transfer an active call to their mobile phone as they walk out the door of their office.</span></span>

</div>

<div>

## <a name="richer-communications"></a><span data-ttu-id="45c5d-118">Comunicaciones más ricas</span><span class="sxs-lookup"><span data-stu-id="45c5d-118">Richer Communications</span></span>

<span data-ttu-id="45c5d-119">Al hablar con otro usuario con Lync, los usuarios pueden agregar fácilmente texto, vídeo o uso compartido de escritorio a la llamada.</span><span class="sxs-lookup"><span data-stu-id="45c5d-119">When talking to another user with Lync, users can easily add text, video, or desktop sharing to the call.</span></span> <span data-ttu-id="45c5d-120">La característica do-not-molestar se integra con la configuración de presencia en Lync.</span><span class="sxs-lookup"><span data-stu-id="45c5d-120">The Do-Not-Disturb feature is integrated with the presence settings in Lync.</span></span>

<span data-ttu-id="45c5d-121">Con mensajería unificada (UM) de Exchange, Lync y Lync Server se integran con Microsoft Exchange Server 2013 y Microsoft Outlook 2013.</span><span class="sxs-lookup"><span data-stu-id="45c5d-121">With Exchange Unified Messaging (UM), Lync and Lync Server integrate with Microsoft Exchange Server 2013 and Microsoft Outlook 2013.</span></span> <span data-ttu-id="45c5d-122">Los usuarios pueden ver si tienen el correo de voz nuevo tanto en la ventana de Lync como en el correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="45c5d-122">Users can see if they have new voice mail both in their Lync window and in email.</span></span> <span data-ttu-id="45c5d-123">En el correo electrónico, pueden hacer clic en para reproducir el audio del correo de voz en un mensaje de correo electrónico o ver una transcripción del mensaje de correo de voz.</span><span class="sxs-lookup"><span data-stu-id="45c5d-123">While in email they can click to play the voice mail audio in an email message, or view a transcript of the voice mail message.</span></span>

</div>

<div>

## <a name="advanced-calling-features"></a><span data-ttu-id="45c5d-124">Características avanzadas de llamadas</span><span class="sxs-lookup"><span data-stu-id="45c5d-124">Advanced Calling Features</span></span>

<span data-ttu-id="45c5d-125">La telefonía IP empresarial también incluye varias características de llamadas avanzadas, como la delegación de llamadas de Lync, las llamadas de equipo, la recogida de llamadas grupales y los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="45c5d-125">Enterprise Voice includes several advanced calling features as well, such as Lync call delegation, team calling, Group Call Pickup, and Response Groups.</span></span>

<span data-ttu-id="45c5d-126">La delegación de llamadas de Lync permite a los usuarios delegar el control de llamadas en uno o varios asistentes, yendo a **herramientas** \> **Opciones** \> de **desvío de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="45c5d-126">Lync call delegation enables users to delegate call handling to one or more assistants, by going to **Tools** \> **Options** \> **Call Forwarding Settings**.</span></span> <span data-ttu-id="45c5d-127">El delegado puede realizar varias tareas de llamada en nombre del usuario, entre las que se incluyen las llamadas de filtrado, la realización de llamadas y la apertura de conferencias.</span><span class="sxs-lookup"><span data-stu-id="45c5d-127">The delegate can perform multiple calling tasks on behalf of the user, including screening calls, placing calls, and initiating conferences.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="45c5d-128">Es posible que esté buscando otra característica con un nombre similar, Delegación de calendarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="45c5d-128">You may be looking for another similarly named feature, Lync calendar delegation.</span></span> <span data-ttu-id="45c5d-129">No requiere la característica de telefonía IP empresarial y permite a los usuarios programar reuniones de Lync en línea desde Outlook.</span><span class="sxs-lookup"><span data-stu-id="45c5d-129">It doesn't require the Enterprise Voice feature and does allow users to schedule online Lync meetings from Outlook.</span></span> <span data-ttu-id="45c5d-130">Si ha llegado para esa información, le recomendamos que consulte <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-ClientPolicy</A> para obtener información sobre cómo habilitar la sincronización de delegados de Exchange.</span><span class="sxs-lookup"><span data-stu-id="45c5d-130">If you've come here looking for that info, we recommend checking out <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A> for information on enabling Exchange delegate sync.</span></span>



</div>

<span data-ttu-id="45c5d-131">Las llamadas de equipo permiten a un usuario hacer llamadas entrantes simultáneamente en los teléfonos de los compañeros de equipo para que cualquier persona del equipo pueda responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="45c5d-131">Team calling enables a user to have incoming calls simultaneously ring the phones of teammates so that anyone on the team can answer the call.</span></span>

<span data-ttu-id="45c5d-132">Recogida de la llamada grupal, una nueva característica de las actualizaciones acumulativas para Lync Server 2013: el 2013 de febrero, permite a los usuarios contestar las llamadas entrantes a sus colegas desde sus propios teléfonos.</span><span class="sxs-lookup"><span data-stu-id="45c5d-132">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="45c5d-133">La recogida de llamadas grupales difiere de las llamadas de equipo principalmente en que las llamadas entrantes solo suenan en el teléfono del destinatario deseado, pero cualquier otro usuario puede contestarla marcando un número de grupo de recogida de llamadas.</span><span class="sxs-lookup"><span data-stu-id="45c5d-133">Group Call Pickup differs from team calling primarily in that an incoming call rings only at the intended recipient's phone, but any other user can choose to answer it by dialing a call pickup group number.</span></span>

<span data-ttu-id="45c5d-134">Los grupos de respuesta se pueden configurar para la cola y enrutar de forma inteligente las llamadas a agentes designados.</span><span class="sxs-lookup"><span data-stu-id="45c5d-134">Response Groups can be set up for queuing and intelligently routing calls to designated agents.</span></span> <span data-ttu-id="45c5d-135">Los usos más comunes incluyen el servicio de asistencia al usuario de ti, las líneas directas de recursos humanos y otros centros internos de contacto.</span><span class="sxs-lookup"><span data-stu-id="45c5d-135">Common uses include IT helpdesks, human resources hotlines, and other internal contact centers.</span></span>

</div>

<div>

## <a name="enterprise-voice-administration"></a><span data-ttu-id="45c5d-136">Administración de telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="45c5d-136">Enterprise Voice Administration</span></span>

<span data-ttu-id="45c5d-137">Lync Server usa estándares e interfaces publicadas para interoperar con la infraestructura existente.</span><span class="sxs-lookup"><span data-stu-id="45c5d-137">Lync Server uses standards and published interfaces to interoperate with existing infrastructure.</span></span> <span data-ttu-id="45c5d-138">Es compatible con las opciones de puerta de enlace y de SIP (como la Troncalización SIP) para la interconexión con sistemas PBX IP y las redes RTC, de modo que pueda migrar los usuarios a Enterprise Voice a través del tiempo, a la vez que minimiza las interrupciones.</span><span class="sxs-lookup"><span data-stu-id="45c5d-138">It supports both gateway and SIP options (such as SIP trunking) for interconnection to IP PBX systems and the PSTN networks, so that you can migrate users to Enterprise Voice over time, while minimizing disruption.</span></span> <span data-ttu-id="45c5d-139">Lync Server admite los códecs tradicionales, como G. 711, G. 722 y G. 723.1 para la interoperabilidad con las soluciones de VoIP tradicionales.</span><span class="sxs-lookup"><span data-stu-id="45c5d-139">Lync Server supports traditional codecs such as G.711, G.722, and G.723.1 for interoperability with traditional VoIP solutions.</span></span>

<span data-ttu-id="45c5d-140">Con control de admisión de llamadas (CAC), los administradores pueden establecer límites en la cantidad de tráfico de voz y vídeo de Lync Server que se transporta en los vínculos de red restringidos y especificar la acción que se debe realizar si una nueva llamada supera el límite.</span><span class="sxs-lookup"><span data-stu-id="45c5d-140">With call admission control (CAC), administrators can set limits on the amount of Lync Server voice and video traffic carried on constrained network links, and specify the action to be taken if a new call would exceed the limit.</span></span> <span data-ttu-id="45c5d-141">Las acciones pueden incluir el enrutamiento mediante una ruta de acceso alternativa o la negación de la llamada.</span><span class="sxs-lookup"><span data-stu-id="45c5d-141">The actions could include routing by an alternate path, or refusing the call.</span></span>

<span data-ttu-id="45c5d-142">Lync Server funciona con equipos de sucursales de terceros que permiten ofrecer servicios de llamadas locales y una conexión a PSTN en sucursales, en caso de que se produzcan errores de WAN en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="45c5d-142">Lync Server works with third-party Survivable Branch Appliances to provide local calling services and connection to PSTN at branch offices, in case of WAN failure at the central site.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

