---
title: 'Lync Server 2013: planificación de control remoto de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c07674be037c7d2fe06d6e2811dcd3264cc6db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Planear el control remoto de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

En Lync Server 2013, la compatibilidad con los escenarios de control remoto de llamadas permite a los usuarios controlar sus teléfonos de central de conmutación (PBX) con Lync 2013 en sus equipos de escritorio. En esta sección se describen las características y los requisitos de control remoto de llamadas para implementar el control remoto de llamadas.

La integración entre una PBX y Lync Server 2013 permite que los usuarios habilitados para el control remoto de llamadas usen la interfaz de usuario (IU) de Lync 2013 para controlar las llamadas en sus teléfonos PBX de las siguientes maneras:

<div>


> [!NOTE]  
> En última instancia, las capacidades de la PBX que hospeda el teléfono PBX de un usuario determinan las características de control remoto de llamadas que estarán disponibles para ese usuario.



</div>

  - Realizar una llamada saliente

  - Responder a una llamada entrante

  - Responder a una llamada entrante con un mensaje instantáneo
    
    <div>
    

    > [!NOTE]  
    > Es decir, cuando el número de teléfono de la persona que llama se puede asociar con una dirección de mensaje instantáneo en la lista global de direcciones (GAL) de la organización, en la lista de contactos de Lync de la persona que llama o en la organización de un socio federado.

    
    </div>

  - Transferir una llamada

  - Desviar una llamada entrante

  - Poner las llamadas en espera

  - Alternar entre varias llamadas simultáneas

  - Contestar una segunda llamada mientras ya está en una llamada (es decir, llamada en espera)

  - Marcar dígitos de multifrecuencia de tono dual (DTMF)

  - En la ventana de conversación, escriba notas en el programa de toma de notas de Microsoft Office OneNote

Además, cuando un usuario está habilitado para el control remoto de llamadas, Lync 2013 proporciona al usuario la siguiente información de la llamada:

  - Identificación de una persona que llama cuando el número de teléfono de la persona que llama está en la lista de contactos de un cliente de mensajería y colaboración de Microsoft Office Outlook habilitado para el control de llamadas remoto, lista de contactos de Lync o la GAL de su organización.

  - Llamadas entrantes y salientes anteriores, que se guardan en la carpeta Historial de conversaciones de Outlook.

  - Notificaciones de llamadas perdidas, que se envían a la carpeta Bandeja de entrada de Outlook del usuario, pero se generan solo si Lync se está ejecutando cuando se recibe la llamada entrante.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Control remoto de llamadas y telefonía IP empresarial

Aunque las características de control remoto de llamadas son independientes de las características de telefonía IP empresarial y los usuarios no pueden habilitarse para ambas, la telefonía IP empresarial ofrece un subconjunto de características que también están disponibles para los usuarios que están habilitados para el control remoto de llamadas. Si se implementa la telefonía IP empresarial, los usuarios habilitados para el control remoto de llamadas pueden usar Lync para acceder a las siguientes características de telefonía IP empresarial:

  - Realizar y recibir llamadas de audio a otro cliente de Lync

  - Unirse a la parte de audio de una conferencia creada por un usuario que está habilitado para telefonía IP empresarial

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Implementación de tareas para el control remoto de llamadas en Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

