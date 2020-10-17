---
title: 'Lync Server 2013: (opcional) comprobar la implementación del estacionamiento de llamadas'
description: 'Lync Server 2013: (opcional) Compruebe la implementación del estacionamiento de llamadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772392a3a791ed57c3220d80e9bd510d8803debb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541936"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a><span data-ttu-id="1e021-103">Opcional Comprobar la implementación del estacionamiento de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e021-103">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e021-104">_**Última modificación del tema:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="1e021-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="1e021-105">Después de instalar y configurar el estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que el estacionamiento y la recuperación de llamadas funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="1e021-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="1e021-106">Como mínimo, compruebe los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1e021-106">At minimum, verify the following:</span></span>

  - <span data-ttu-id="1e021-107">Llamar a un usuario con el estacionamiento de llamadas habilitado y hacer que el usuario estacione la llamada.</span><span class="sxs-lookup"><span data-stu-id="1e021-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1e021-108">Si habilitó el estacionamiento de llamadas en la Directiva de voz justo antes de realizar esta prueba, el usuario que estaciona la llamada tiene que cerrar sesión en Lync Server y, a continuación, volver a iniciarla, para poder ver la opción estacionamiento de llamadas en la lista de llamadas de transferencia.</span><span class="sxs-lookup"><span data-stu-id="1e021-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Lync Server, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span>

    
    </div>

  - <span data-ttu-id="1e021-109">Marque el número de órbita para recuperar la llamada.</span><span class="sxs-lookup"><span data-stu-id="1e021-109">Dial the orbit number to retrieve the call.</span></span>

  - <span data-ttu-id="1e021-p102">Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="1e021-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

