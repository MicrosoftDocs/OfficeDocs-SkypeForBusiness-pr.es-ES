---
title: 'Lync Server 2013: información general sobre la llamada en estacionamiento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2d6f6b8f0f6a91e75071c7d103cf4bff3b4be1f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="a29c7-102">Información general sobre el parque de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a29c7-102">Overview of Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a29c7-103">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="a29c7-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="a29c7-104">La aplicación de Parque de llamadas de Lync Server 2013 permite a los usuarios de Enterprise Voice realizar cualquiera de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a29c7-104">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="a29c7-105">Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.</span><span class="sxs-lookup"><span data-stu-id="a29c7-105">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="a29c7-106">Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="a29c7-106">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="a29c7-107">Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.</span><span class="sxs-lookup"><span data-stu-id="a29c7-107">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="a29c7-108">Cuando un usuario detiene una llamada, Lync Server transfiere la llamada a un número temporal, denominado *órbita*, en el que se mantiene la llamada hasta que se recupera o se agota el tiempo de espera. Lync Server envía la órbita al usuario que detuvo la llamada.</span><span class="sxs-lookup"><span data-stu-id="a29c7-108">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="a29c7-109">Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación.</span><span class="sxs-lookup"><span data-stu-id="a29c7-109">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="a29c7-p102">El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de localización, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.</span><span class="sxs-lookup"><span data-stu-id="a29c7-p102">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="a29c7-112">Dado que los intervalos de órbita son únicos globalmente, es posible recuperar las llamadas de cualquier sitio de Lync Server o de un teléfono PBX si el enrutamiento está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a29c7-112">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="a29c7-113">Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó.</span><span class="sxs-lookup"><span data-stu-id="a29c7-113">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="a29c7-114">Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así.</span><span class="sxs-lookup"><span data-stu-id="a29c7-114">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="a29c7-115">Puedes configurar el número de veces que deseas que suene la llamada antes de ser transferida de una a diez veces.</span><span class="sxs-lookup"><span data-stu-id="a29c7-115">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="a29c7-116">Si nadie responde a una llamada transferida, la llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="a29c7-116">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="a29c7-117">La órbita se libera cuando se recupera la llamada o se desconecta.</span><span class="sxs-lookup"><span data-stu-id="a29c7-117">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="a29c7-118">Al implementar el estacionamiento de llamadas, necesitarás reservar intervalos de números de extensión para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="a29c7-118">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="a29c7-119">Estas extensiones necesitan ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado.</span><span class="sxs-lookup"><span data-stu-id="a29c7-119">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="a29c7-120">Luego, necesitarás configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="a29c7-120">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="a29c7-121">Cada grupo de servidores front-end tiene una tabla de estacionamiento de llamadas en el servidor back end correspondiente que se usa para administrar las llamadas que se aparcarán en el grupo.</span><span class="sxs-lookup"><span data-stu-id="a29c7-121">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="a29c7-122">La lista de intervalos de órbita se almacena en el almacén de administración central y se usa para enrutar órbitas hasta el grupo de destino.</span><span class="sxs-lookup"><span data-stu-id="a29c7-122">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="a29c7-123">Cada grupo de Lync Server en el que se implementa y configura la aplicación de estacionamiento de llamadas puede tener uno o más intervalos Orbitantes.</span><span class="sxs-lookup"><span data-stu-id="a29c7-123">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="a29c7-124">Los intervalos de órbita deben ser únicos globalmente en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a29c7-124">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="a29c7-p105">También configuras otras opciones de estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puedes especificar el archivo de música que deseas que se reproduzca mientras la llamada está en espera.</span><span class="sxs-lookup"><span data-stu-id="a29c7-p105">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a29c7-127">No se realiza una copia de seguridad de los archivos de música personalizada que se encuentran en espera para el servicio de recuperación de desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, dañados o borrados.</span><span class="sxs-lookup"><span data-stu-id="a29c7-127">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="a29c7-128">Guarda siempre una copia de seguridad independiente de los archivos de música en espera personalizados que haya cargado para el estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a29c7-128">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="a29c7-129">La aplicación Estacionamiento de llamadas es un componente de la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="a29c7-129">The Call Park application is a component of Enterprise Voice.</span></span> <span data-ttu-id="a29c7-130">Al implementar la telefonía IP empresarial, la aplicación de estacionamiento de llamadas se instala y activa automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a29c7-130">When you deploy Enterprise Voice, the Call Park application is installed and activated automatically.</span></span> <span data-ttu-id="a29c7-131">Sin embargo, antes de poder usar el parque de llamadas, el administrador de telefonía IP debe configurarlo y habilitarlo para los usuarios mediante la Directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="a29c7-131">Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

