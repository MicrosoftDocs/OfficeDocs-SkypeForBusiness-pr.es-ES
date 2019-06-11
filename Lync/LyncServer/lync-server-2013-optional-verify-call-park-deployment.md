---
title: 'Lync Server 2013: (opcional) comprobar la implementación del parque de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 110617bbd77da0efb8802c6aba401f2ea5075b01
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Faculta Comprobar la implementación del parque de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

Después de instalar y configurar el parque de llamadas, debe comprobar la configuración para asegurarse de que el aparcamiento y la recuperación de llamadas funciona según lo esperado. Como mínimo, compruebe los elementos siguientes:

  - Llamar a un usuario que tiene habilitada la opción estacionamiento de llamadas y hacer que el usuario aparca la llamada.
    
    <div>
    

    > [!NOTE]  
    > Si habilitó el parque de llamadas en la Directiva de voz justo antes de realizar esta prueba, el usuario que está aparcando la llamada necesita cerrar la sesión de Lync Server y, después, volver a iniciarla para poder ver la opción estacionamiento de llamadas en la lista de llamadas de transferencia.

    
    </div>

  - Marque el número de órbita para recuperar la llamada.

  - Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.

</div>

<span> </span>

</div>

</div>

</div>

