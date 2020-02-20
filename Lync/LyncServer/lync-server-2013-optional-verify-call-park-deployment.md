---
title: 'Lync Server 2013: (opcional) comprobar la implementación del estacionamiento de llamadas'
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
ms.openlocfilehash: 0e0389e729f91da7cb91dff9426e38c1dcf20024
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Opcional Comprobar la implementación del estacionamiento de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-11_

Después de instalar y configurar el estacionamiento de llamadas, debe comprobar la configuración para asegurarse de que el estacionamiento y la recuperación de llamadas funciona según lo esperado. Como mínimo, compruebe los elementos siguientes:

  - Llamar a un usuario con el estacionamiento de llamadas habilitado y hacer que el usuario estacione la llamada.
    
    <div>
    

    > [!NOTE]  
    > Si habilitó el estacionamiento de llamadas en la Directiva de voz justo antes de realizar esta prueba, el usuario que estaciona la llamada tiene que cerrar sesión en Lync Server y, a continuación, volver a iniciarla, para poder ver la opción estacionamiento de llamadas en la lista de llamadas de transferencia.

    
    </div>

  - Marque el número de órbita para recuperar la llamada.

  - Estacione otra llamada, deje que finalice el tiempo de espera de la llamada estacionada y no recupere la señal de llamada. Compruebe que la llamada con el tiempo de espera agotado se enrute correctamente al destino de reserva que se especifica en **OnTimeoutURI**.

</div>

<span> </span>

</div>

</div>

</div>

