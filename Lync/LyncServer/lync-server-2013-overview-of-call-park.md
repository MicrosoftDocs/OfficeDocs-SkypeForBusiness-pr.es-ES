---
title: 'Lync Server 2013: información general sobre el estacionamiento de llamadas'
description: 'Lync Server 2013: información general sobre el estacionamiento de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 373a758dcc64dc390255239c0d1fb628308080a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559266"
---
# <a name="overview-of-call-park-in-lync-server-2013"></a><span data-ttu-id="5a5eb-103">Información general sobre el estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a5eb-103">Overview of Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a5eb-104">_**Última modificación del tema:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="5a5eb-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="5a5eb-105">La aplicación de estacionamiento de llamadas de Lync Server 2013 permite que los usuarios de Enterprise Voice hagan lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5a5eb-105">The Lync Server 2013 Call Park application lets Enterprise Voice users do any of the following:</span></span>

  - <span data-ttu-id="5a5eb-106">Poner una llamada en espera y recuperar la llamada desde el mismo teléfono o desde otro.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-106">Put a call on hold and then retrieve the call from the same phone or another phone.</span></span>

  - <span data-ttu-id="5a5eb-107">Poner una llamada en espera para transferirla a un departamento o área general, por ejemplo, a un departamento de ventas o a un almacén donde hay un teléfono de área común.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-107">Put a call on hold to transfer it to a department or general area (for example, to a sales department or a warehouse where there is a common area phone).</span></span>

  - <span data-ttu-id="5a5eb-108">Poner una llamada en espera y conservar el teléfono original que ha respondido disponible para recibir otras llamadas.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-108">Put a call on hold and keep the original answering phone free for other calls.</span></span>

<span data-ttu-id="5a5eb-109">Cuando un usuario detiene una llamada, Lync Server transfiere la llamada a un número temporal, denominado *órbita*, donde la llamada se mantiene hasta que se recupera o se agota el tiempo de espera. Lync Server envía la órbita al usuario que ha estacionado la llamada.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-109">When a user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until it is retrieved or it times out. Lync Server sends the orbit to the user who parked the call.</span></span> <span data-ttu-id="5a5eb-110">Para recuperar la llamada estacionada, el usuario puede marcar el número de órbita o hacer clic en el botón o vínculo de órbita de la ventana Conversación.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-110">To retrieve the parked call, the user can dial the orbit number or click the orbit link or button in the Conversation window.</span></span>

<span data-ttu-id="5a5eb-p102">El usuario que estacionó una llamada puede notificar a alguien que recupere la llamada usando un mecanismo externo, como la mensajería instantánea (MI) o un sistema de paginación, para comunicar el número de órbita a otro usuario. El usuario que estacionó la llamada puede dejar la ventana Conversación abierta para recibir una notificación cuando se recupere la llamada.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-p102">The user who parked a call can notify someone to retrieve the call by using an external mechanism, such as instant messaging (IM) or a paging system, to communicate the orbit number to someone else. The user who parked the call can leave the Conversation window open to receive notification when the call is retrieved.</span></span>

<span data-ttu-id="5a5eb-113">Debido a que los intervalos de órbita son únicos globalmente, es posible recuperar las llamadas de cualquier teléfono PBX o sitio de Lync Server si el enrutamiento está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-113">Because orbit ranges are globally unique, it is possible to retrieve calls from any Lync Server site or PBX phone if routing is configured appropriately.</span></span> <span data-ttu-id="5a5eb-114">Si nadie recupera la llamada en un período de tiempo configurable, la llamada volverá a sonar para la persona que la estacionó.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-114">If no one retrieves the call within a configurable amount of time, the call rings back to the person who parked it.</span></span> <span data-ttu-id="5a5eb-115">Si dicha persona no responde esta vez, la llamada se transferirá a un destino de conmutación por error, como un operador, si se ha configurado así.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-115">If that person does not answer the ringback, the call is transferred to a fallback destination, such as to an operator, if so configured.</span></span> <span data-ttu-id="5a5eb-116">Puede configurar el número de veces que desea que suene la llamada antes de ser transferida de una a diez veces.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-116">You can configure the number of times the call rings back before being transferred from one to ten times.</span></span> <span data-ttu-id="5a5eb-117">Si nadie responde a una llamada transferida, la llamada se desconectará.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-117">If no one answers a transferred call, the call is disconnected.</span></span> <span data-ttu-id="5a5eb-118">La órbita se libera cuando se recupera la llamada o se desconecta.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-118">The orbit is freed when the call is retrieved or disconnected.</span></span>

<span data-ttu-id="5a5eb-119">Al implementar Estacionamiento de llamadas, deberá reservar intervalos de números de extensión (órbitas) para estacionar llamadas.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-119">When you deploy Call Park, you need to reserve ranges of extension numbers for parking calls.</span></span> <span data-ttu-id="5a5eb-120">Estas extensiones deben ser extensiones virtuales: extensiones que no tienen ningún usuario o teléfono asignado.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-120">These extensions need to be virtual extensions: extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="5a5eb-121">A continuación, deberá configurar la tabla de órbitas de estacionamiento de llamadas con los intervalos de números de extensión y especificar qué servicio de aplicaciones hospeda la aplicación Estacionamiento de llamadas que administra cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-121">You then configure the call park orbit table with the ranges of extension numbers and specify which Application service hosts the Call Park application that handles each range.</span></span> <span data-ttu-id="5a5eb-122">Cada grupo de servidores front-end dispone de una tabla de estacionamiento de llamadas en el servidor back-end correspondiente que se usa para administrar las llamadas que se estacionan en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-122">Each Front End pool has a Call Park table on the corresponding Back End Server that is used to manage calls that are parked on the pool.</span></span> <span data-ttu-id="5a5eb-123">La lista de intervalos de órbitas se almacena en el almacén de administración central y se usa para redirigir órbitas al grupo de servidores de destino.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-123">The list of orbit ranges is stored in Central Management store and is used to route orbits to the destination pool.</span></span> <span data-ttu-id="5a5eb-124">Cada grupo de Lync Server en el que se implementa y configura la aplicación de estacionamiento de llamadas puede tener uno o más intervalos de órbitas.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-124">Each Lync Server pool where the Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="5a5eb-125">Los intervalos de órbitas deben ser únicos en todo el mundo en la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-125">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<span data-ttu-id="5a5eb-p105">También configura otras opciones de Estacionamiento de llamadas, como, por ejemplo, el lugar al que se redirigirán las llamadas si transcurre el tiempo de espera y si la persona que está al teléfono oirá música mientras la llamada está estacionada. Asimismo, puede especificar el archivo de música que desea que se reproduzca mientras la llamada está en espera.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-p105">You also configure other Call Park settings, such as where calls are redirected if they time out and whether the person on the phone hears music while parked. You can also specify the music file to play while the call is on hold.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5a5eb-128">No se realiza una copia de seguridad de los archivos de música en espera personalizados para el estacionamiento de llamadas como parte del proceso de recuperación ante desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, dañados o borrados.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-128">Customized music-on-hold files for Call Park are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="5a5eb-129">Guarde siempre una copia de seguridad independiente de los archivos de música en espera que haya cargado para Estacionamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-129">Always keep a separate backup copy of the customized music-on-hold files that you have uploaded for Call Park.</span></span>



</div>

<span data-ttu-id="5a5eb-p107">La aplicación Estacionamiento de llamadas es un componente de Enterprise Voice. Al implementar Enterprise Voice, la aplicación Estacionamiento de llamadas se instalará y activará de forma automática. Sin embargo, para poder usar el estacionamiento de llamadas, el administrador de Enterprise Voice deberá configurarlo y habilitarlo para los usuarios mediante una directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="5a5eb-p107">The Call Park application is a component of Enterprise Voice. When you deploy Enterprise Voice, the Call Park application is installed and activated automatically. Before you can use Call Park, however, the Enterprise Voice administrator must configure it and enable it for users through voice policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

