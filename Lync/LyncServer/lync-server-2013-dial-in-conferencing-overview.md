---
title: Información general sobre las conferencias de acceso telefónico local de Lync Server 2013
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
ms.openlocfilehash: 71d6717f183066688fdf94d0fc83e0e662c9a6b3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="043ad-102">Información general sobre las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="043ad-102">Overview of dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="043ad-103">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="043ad-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="043ad-104">Si su organización tiene usuarios que necesitan asistir a conferencias locales de Lync Server 2013 cuando están fuera de la oficina o no tienen acceso a un equipo, puede implementar la Conferencia de acceso telefónico local para que puedan unirse a la Conferencia mediante un teléfono conmutado público. teléfono de red (RTC).</span><span class="sxs-lookup"><span data-stu-id="043ad-104">If your organization has users who need to attend Lync Server 2013 on-premises conferences when they are out of the office or do not have access to a computer, you can deploy dial-in conferencing so that they can join the conference by using a public switched telephone network (PSTN) phone.</span></span>

<span data-ttu-id="043ad-105">La Conferencia de acceso telefónico local es una característica opcional que puede configurar al implementar la Conferencia de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="043ad-105">Dial-in conferencing is an optional feature that you can configure when you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="043ad-106">Aunque la Conferencia de acceso telefónico local usa algunos de los mismos componentes de Lync Server 2013 que usa la telefonía IP empresarial, puede implementar la Conferencia de acceso telefónico local aunque no implemente la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="043ad-106">Although dial-in conferencing uses some of the same Lync Server 2013 components that Enterprise Voice uses, you can deploy dial-in conferencing even if you do not deploy Enterprise Voice.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="043ad-107">Si implementa la Conferencia de acceso telefónico local, debe implementarla en todos los grupos de servidores en los que implemente Lync Server 2013 conferencias.</span><span class="sxs-lookup"><span data-stu-id="043ad-107">If you deploy dial-in conferencing, you must deploy it in every pool where you deploy Lync Server 2013 conferencing.</span></span> <span data-ttu-id="043ad-108">No es necesario que asigne números de acceso en cada uno de los grupos de servidores, pero deberá implementar la característica de acceso telefónico local en todos ellos.</span><span class="sxs-lookup"><span data-stu-id="043ad-108">You do not need to assign access numbers in every pool, but you must deploy the dial-in feature in every pool.</span></span> <span data-ttu-id="043ad-109">Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso de un grupo de servidores para unirse a una conferencia de 2013 de Lync Server en un grupo de servidores diferente.</span><span class="sxs-lookup"><span data-stu-id="043ad-109">This requirement supports the recorded name feature when a user calls an access number from one pool to join a Lync Server 2013 conference in a different pool.</span></span>



</div>

<span data-ttu-id="043ad-p103">Las conferencias deben estar habilitadas para el acceso telefónico local en la directiva de reunión. De forma predeterminada, las conferencias habilitadas para el acceso telefónico local incluyen la siguiente información en la invitación a la conferencia:</span><span class="sxs-lookup"><span data-stu-id="043ad-p103">Conferences must be enabled for dial-in access in meeting policy. By default, conferences that are enabled for dial-in access include the following information in the conference invitation:</span></span>

  - <span data-ttu-id="043ad-112">Un identificador de conferencia numérico que identifica la conferencia.</span><span class="sxs-lookup"><span data-stu-id="043ad-112">A numeric conference ID that identifies the conference.</span></span>

  - <span data-ttu-id="043ad-113">Uno o más números de acceso de RTC.</span><span class="sxs-lookup"><span data-stu-id="043ad-113">One or more PSTN access numbers.</span></span>

  - <span data-ttu-id="043ad-114">Un vínculo a una página de configuración de conferencia de acceso telefónico local, que contiene una lista completa de números de acceso con sus idiomas asociados; un espacio para crear, restablecer o desbloquear números de identificación personal (PIN); y otra información, como controles de tono de marcado de frecuencia múltiple (DTMF).</span><span class="sxs-lookup"><span data-stu-id="043ad-114">A link to a Dial-in Conferencing Settings page, which contains a complete list of access numbers with their associated languages; a place to create, reset, or unblock personal identification numbers (PINs); and other information, such as dual-tone multi-frequency (DTMF) controls.</span></span>

<span data-ttu-id="043ad-115">Las conferencias de acceso telefónico local admiten tanto a usuarios de empresa como a usuarios anónimos.</span><span class="sxs-lookup"><span data-stu-id="043ad-115">Dial-in conferencing supports both enterprise and anonymous users.</span></span> <span data-ttu-id="043ad-116">Los usuarios empresariales tienen credenciales de servicios de dominio de Active Directory y cuentas de Lync Server 2013 dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="043ad-116">Enterprise users have Active Directory Domain Services credentials and Lync Server 2013 accounts within their organization.</span></span> <span data-ttu-id="043ad-117">Los usuarios anónimos no tienen credenciales de empresa en la organización.</span><span class="sxs-lookup"><span data-stu-id="043ad-117">Anonymous users do not have enterprise credentials within your organization.</span></span> <span data-ttu-id="043ad-118">En el contexto de una conferencia de acceso telefónico local, un usuario de una organización asociada federada que usa la RTC para conectarse a una conferencia se considera usuario anónimo.</span><span class="sxs-lookup"><span data-stu-id="043ad-118">In the dial-in conferencing context, a user in a federated partner’s organization who uses the PSTN to connect to a conference is treated like an anonymous user.</span></span> <span data-ttu-id="043ad-119">A diferencia de lo que ocurre en otros contextos, los usuarios federados no se autentican para la conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="043ad-119">For dial-in conferencing, unlike other contexts, federated users are not authenticated.</span></span>

<span data-ttu-id="043ad-120">Los usuarios de empresa o coordinadores de la conferencia que se unen a una conferencia habilitada para el acceso telefónico local marcan uno de los números de acceso a la conferencia y, a continuación, se les pide que escriban el identificador de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="043ad-120">Enterprise users or conference leaders who join a conference that is enabled for dial-in access dial one of the conference access numbers and then are prompted to enter the conference ID.</span></span> <span data-ttu-id="043ad-121">Si todavía no se ha unido a la reunión ningún coordinador, los usuarios pueden escribir su extensión (o número de teléfono completo) de comunicaciones unificadas (UC) y el PIN, o bien esperar a que un coordinador les admita.</span><span class="sxs-lookup"><span data-stu-id="043ad-121">If a leader has not yet joined the meeting, users can either enter their unified communications (UC) extension (or full phone number) and PIN or wait to be admitted by a leader.</span></span> <span data-ttu-id="043ad-122">El organizador de la reunión puede unirse a la reunión como coordinador escribiendo solo el PIN.</span><span class="sxs-lookup"><span data-stu-id="043ad-122">The Meeting organizer can join the meeting as a leader by entering just their PIN.</span></span> <span data-ttu-id="043ad-123">El servidor front-end usa la combinación de número de teléfono completo o extensión, y PIN, para asignar exclusivamente a los usuarios de la empresa a sus credenciales de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="043ad-123">The Front End Server uses the combination of full phone number or extension, and PIN, to uniquely map enterprise users to their Active Directory credentials.</span></span> <span data-ttu-id="043ad-124">Como resultado, los usuarios de empresa se pueden autenticar e identificar por su nombre en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="043ad-124">As a result, enterprise users are authenticated and identified by name in the conference.</span></span> <span data-ttu-id="043ad-125">Los usuarios de empresa también pueden asumir un rol de conferencia definido previamente por el organizador.</span><span class="sxs-lookup"><span data-stu-id="043ad-125">Enterprise users can also assume a conference role predefined by the organizer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="043ad-126">Los usuarios empresariales que llaman desde un teléfono IP de Office o desde un operador de Lync Server 2013 o Lync 2010 no reciben su número de teléfono debido a que ya se han autenticado.</span><span class="sxs-lookup"><span data-stu-id="043ad-126">Enterprise users who dial in from an office IP phone or from Lync Server 2013 or Lync 2010 Attendant are not prompted for their phone number because they are already authenticated.</span></span>



</div>

<span data-ttu-id="043ad-p106">Los usuarios anónimos que deseen unirse a una conferencia de acceso telefónico local, deben marcar uno de los números de acceso a la conferencia y, a continuación, se les pedirá que escriban el identificador de la conferencia. A los usuarios anónimos sin autenticar también se les pide que registren su nombre. El nombre grabado identifica a los usuarios sin autenticar en la conferencia. No se admiten usuarios anónimos en la conferencia hasta que se haya unido a ella al menos un coordinador o un usuario autenticado, y no se les puede asignar un rol definido previamente.</span><span class="sxs-lookup"><span data-stu-id="043ad-p106">Anonymous users who want to join a dial-in conference dial one of the conference access numbers and then they are prompted to enter the conference ID. Unauthenticated anonymous users are also prompted to record their name. The recorded name identifies unauthenticated users in the conference. Anonymous users are not admitted to the conference until at least one leader or authenticated user has joined, and they cannot be assigned a predefined role.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="043ad-p107">Los usuarios de empresa que elijan no escribir su número de teléfono y su PIN no se autenticarán. Se les pedirá que registren su nombre y se les considerará usuarios anónimos en la conferencia.</span><span class="sxs-lookup"><span data-stu-id="043ad-p107">Enterprise users who choose not to enter their phone number and PIN are not authenticated. They are prompted to record their name and are treated as anonymous users in the conference.</span></span>



</div>

<span data-ttu-id="043ad-p108">A la hora programada, el organizador de la reunión puede restringir el acceso a la reunión bloqueándola o cerrándola. En este caso, se solicitará a los usuarios de acceso telefónico local que se autentiquen. Si prefieren no autenticarse o no lo hacen correctamente, se les transferirá a la sala de espera, donde esperarán hasta que el coordinador acepte o rechace su entrada, o bien hasta que se agote el tiempo de espera y sean desconectados. Los usuarios de acceso telefónico local escucharán música mientras esperan su admisión a la conferencia. Una vez admitidos en una conferencia, los usuarios de acceso telefónico local pueden participar en la parte de audio de la conferencia y usar los comandos de tono de marcado de frecuencia múltiple (DTMF) con las teclas del teléfono. Los coordinadores de acceso telefónico pueden usar comandos DTMF para activar o desactivar el audio de los participantes, bloquear o desbloquear la conferencia, admitir a personas de la sala de espera y activar o desactivar los anuncios de entrada y salida. Los coordinadores también pueden usar un comando DTMF para admitir a todas las personas de la sala de espera, lo que modifica los permisos de la reunión para habilitar a todos los que se unan más tarde. Todos los participantes de acceso telefónico pueden usar comandos DTMF para escuchar la Ayuda, escuchar la lista de conferencias y silenciarse.</span><span class="sxs-lookup"><span data-stu-id="043ad-p108">At schedule time, the meeting organizer can choose to restrict access to the meeting by making the meeting closed or locked. In this case, dial-in users are requested to authenticate. If dial-in users fail or choose not to authenticate, they are transferred to the lobby. They wait in the lobby until a leader accepts or rejects them, or they time out and are disconnected. Dial-in users hear music if they are waiting to be admitted to the conference. After they are admitted to a conference, dial-in users can participate in the audio portion of the conference and can exercise dual-tone multi-frequency (DTMF) commands by using the phone keypad. Dial-in leaders can exercise DTMF commands to turn participants' ability to unmute on or off, lock or unlock the conference, admit people from the lobby, and turn entry and exit announcements on or off. Leaders can also use a DTMF command to admit everyone from the lobby, which changes the permissions of the meeting to allow anyone who subsequently joins. All dial-in participants can exercise DTMF commands to hear Help, listen to the conference roster, and mute themselves.</span></span>

<span data-ttu-id="043ad-142">Los participantes de acceso telefónico (es decir, los participantes que accedan o no desde el RTC) oirán anuncios personales durante la conferencia, como si han sido silenciados o se les ha dado la voz, si la reunión está siendo grabada o si hay alguien esperando en la sala de espera.</span><span class="sxs-lookup"><span data-stu-id="043ad-142">Dial-in participants (that is, whether or not they dial from the PSTN), hear personal announcements during the conference, such as whether they have been muted or unmuted, the meeting is being recorded, or someone is waiting in the lobby.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="043ad-143">Los participantes que se unan a la conferencia haciendo clic en un vínculo, en lugar de acceder mediante el marcado telefónico, no oirán anuncios personales.</span><span class="sxs-lookup"><span data-stu-id="043ad-143">Participants who join the conference by clicking a link instead of dialing in do not hear personal announcements.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

