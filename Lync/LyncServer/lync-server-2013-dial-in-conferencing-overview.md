---
title: Introducción a las conferencias de acceso telefónico local de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing overview
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398524(v=OCS.15)
ms:contentKeyID: 48184436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a126e7e1ee61f48ff8857553b7677abf813a25e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="fa091-102">Información general sobre las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fa091-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa091-103">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="fa091-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="fa091-104">Si su organización tiene usuarios que necesitan asistir a conferencias locales de Lync Server 2013 cuando están fuera de la oficina o no tienen acceso a un equipo, puede implementar la Conferencia de acceso telefónico local para que puedan unirse a la Conferencia mediante un teléfono público con conmutación teléfono de red (RTC).</span><span class="sxs-lookup"><span data-stu-id="fa091-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="fa091-105">Las conferencias de acceso telefónico local son una característica opcional que puede configurar al implementar conferencias de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa091-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="fa091-106">Aunque las conferencias de acceso telefónico local usan algunos de los mismos componentes de Lync Server 2013 que usa Enterprise Voice, puede implementar la Conferencia de acceso telefónico local incluso si no implementa la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="fa091-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa091-107">Si implementa una conferencia de acceso telefónico local, debe implementarla en todos los grupos donde implementará la Conferencia de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fa091-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="fa091-108">No es necesario asignar números de acceso en todos los grupos, pero debe implementar la característica de acceso telefónico en cada grupo.</span><span class="sxs-lookup"><span data-stu-id="fa091-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="fa091-109">Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso desde un grupo para unirse a una conferencia de 2013 de Lync Server en un grupo diferente.</span><span class="sxs-lookup"><span data-stu-id="fa091-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="fa091-110">Las conferencias deben estar habilitadas para el acceso telefónico en la Directiva de reunión.</span><span class="sxs-lookup"><span data-stu-id="fa091-110">Conferences must be enabled for dial-in access in meeting policy.</span></span> <span data-ttu-id="fa091-111">De forma predeterminada, las conferencias habilitadas para el acceso telefónico local incluyen la siguiente información en la invitación a la conferencia:</span><span class="sxs-lookup"><span data-stu-id="fa091-111">By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="fa091-112">Un identificador numérico de conferencia que identifica la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="fa091-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="fa091-113">Uno o más números de acceso de la RTC.</span><span class="sxs-lookup"><span data-stu-id="fa091-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="fa091-114">Un vínculo a una página de configuración de conferencias de acceso telefónico local, que contiene una lista completa de números de acceso con sus idiomas asociados; un lugar para crear, restablecer o desbloquear números de identificación personal (PIN); y otra información, como controles de multifrecuencia de tono dual (DTMF).</span><span class="sxs-lookup"><span data-stu-id="fa091-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="fa091-115">Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="fa091-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="fa091-116">Los usuarios empresariales tienen credenciales de servicios de dominio de Active Directory y cuentas de Lync Server 2013 dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="fa091-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="fa091-117">Los usuarios anónimos no tienen credenciales de empresa en la organización.</span><span class="sxs-lookup"><span data-stu-id="fa091-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="fa091-118">En el contexto de una conferencia de acceso telefónico local, un usuario de una organización asociada externa que usa la RTC para conectarse a una conferencia se considera usuario anónimo.</span><span class="sxs-lookup"><span data-stu-id="fa091-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="fa091-119">A diferencia de lo que ocurre en otros contextos, los usuarios federados no se autentican para la conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="fa091-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="fa091-p105">Los usuarios de empresa o coordinadores de la conferencia que se unen a una conferencia habilitada para el acceso telefónico local, marcan uno de los números de acceso a la conferencia y, luego, se les pide que escriban el identificador de la conferencia. Si todavía no se ha unido a la reunión ningún coordinador, los usuarios pueden escribir su extensión (o número de teléfono completo) de comunicaciones unificadas (UC) y el PIN, o bien esperar a que un coordinador les admita. El organizador de la reunión puede unirse a la reunión como coordinador escribiendo solo el PIN. El servidor front-end usa la combinación de la extensión o número de teléfono completo y el PIN para asignar únicamente usuarios de empresa a sus credenciales de Active Directory. Como resultado, los usuarios de empresa se pueden autenticar e identificar por su nombre en la conferencia. Los usuarios de empresa también pueden asumir un rol de conferencia definido previamente por el organizador.</span><span class="sxs-lookup"><span data-stu-id="fa091-p105">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID. If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader. The Meeting organizer can join the meeting as a leader by entering just their PIN. The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials. As a result, enterprise users are authenticated and identified by name in the conference. Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa091-126">Los usuarios de la empresa que llamen desde un teléfono de Office IP o desde el operador de Lync Server 2013 o de Lync 2010 no se les pedirá su número de teléfono porque ya están autenticados.</span><span class="sxs-lookup"><span data-stu-id="fa091-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="fa091-p106">Los usuarios anónimos que deseen unirse a una conferencia de acceso telefónico local, necesitan marcar uno de los números de acceso a la conferencia y, luego, se les pedirá que escriban el identificador de la conferencia. A los usuarios anónimos sin autenticar también se les pide que registren su nombre. El nombre grabado identifica a los usuarios sin autenticar en la conferencia. No se admiten usuarios anónimos en la conferencia hasta que se haya unido a ella al menos un coordinador o un usuario autenticado, y no se les puede asignar un rol definido previamente.</span><span class="sxs-lookup"><span data-stu-id="fa091-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa091-p107">Los usuarios de empresa que elijan no escribir su número de teléfono y su PIN no se autenticarán. Se les pedirá que registren su nombre y se les considerará usuarios anónimos en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="fa091-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="fa091-133">En el momento de la programación, el organizador de la reunión puede elegir restringir el acceso a la reunión haciendo que la reunión se cierre o se bloquee.</span><span class="sxs-lookup"><span data-stu-id="fa091-133">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked.</span></span> <span data-ttu-id="fa091-134">En este caso, se solicitará a los usuarios de acceso telefónico local que se autentiquen.</span><span class="sxs-lookup"><span data-stu-id="fa091-134">In this case, dial-in users are requested to authenticate.</span></span> <span data-ttu-id="fa091-135">Si los usuarios de acceso telefónico no tienen éxito o elige no autenticar, se transfieren a la sala de recepción.</span><span class="sxs-lookup"><span data-stu-id="fa091-135">If dial-in users fail or choose not to authenticate, they are transferred to the lobby.</span></span> <span data-ttu-id="fa091-136">Esperan en la sala de espera hasta que un líder los acepta o rechaza, o el tiempo de espera y se desconectan.</span><span class="sxs-lookup"><span data-stu-id="fa091-136">They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected.</span></span> <span data-ttu-id="fa091-137">Los usuarios de acceso telefónico escuchan música si están esperando ser admitidos en la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="fa091-137">Dial-in users hear music if they are waiting to be admitted to the conference.</span></span> <span data-ttu-id="fa091-138">Una vez admitidos en una conferencia, los usuarios de acceso telefónico local pueden participar en la parte de audio de la conferencia y usar los comandos de tono de marcado de frecuencia múltiple (DTMF) por medio de las teclas del teléfono.</span><span class="sxs-lookup"><span data-stu-id="fa091-138">After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad.</span></span> <span data-ttu-id="fa091-139">Los coordinadores de acceso telefónico pueden usar comandos DTMF para activar o desactivar el audio de los participantes, bloquear o desbloquear la conferencia, admitir a personas de la sala de espera y activar o desactivar los anuncios de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="fa091-139">Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off.</span></span> <span data-ttu-id="fa091-140">Los coordinadores también pueden usar un comando DTMF para admitir a todas las personas de la sala de espera, lo que modifica los permisos de la reunión para habilitar a todos los que se unan más tarde.</span><span class="sxs-lookup"><span data-stu-id="fa091-140">Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins.</span></span> <span data-ttu-id="fa091-141">Todos los participantes de acceso telefónico pueden usar comandos DTMF para escuchar la Ayuda, escuchar la lista de conferencias y silenciarse.</span><span class="sxs-lookup"><span data-stu-id="fa091-141">All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="fa091-142">Los participantes de acceso telefónico (es decir, si llaman o no desde la RTC) escuchan anuncios personales durante la Conferencia, por ejemplo, si se han silenciado o reactivado, si la reunión se está grabando o si alguien está en espera en la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="fa091-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fa091-143">Los participantes que se unan a la conferencia haciendo clic en un vínculo, en lugar de acceder por medio del marcado telefónico, no oirán anuncios personales.</span><span class="sxs-lookup"><span data-stu-id="fa091-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

