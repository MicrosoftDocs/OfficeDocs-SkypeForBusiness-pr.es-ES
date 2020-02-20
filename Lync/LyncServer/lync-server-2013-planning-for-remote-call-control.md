---
title: 'Lync Server 2013: Planeación del control remoto de llamadas'
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
ms.openlocfilehash: ee463a93afdb32e4c9cd8e90b068a6d03220cb22
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Planeación del control remoto de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

En Lync Server 2013, la compatibilidad con escenarios de control remoto de llamadas permite a los usuarios controlar sus teléfonos de central de conmutación (PBX) con Lync 2013 en sus equipos de escritorio. En esta sección se describen las características del control remoto de llamadas y los requisitos necesarios para implementar el control remoto de llamadas.

La integración entre una PBX y Lync Server 2013 permite que los usuarios habilitados para el control remoto de llamadas usen la interfaz de usuario (UI) de Lync 2013 para controlar las llamadas en sus teléfonos PBX de las siguientes maneras:

<div>


> [!NOTE]  
> Las funcionalidades de la PBX que hospeda el teléfono PBX de un usuario son las que determinan en última instancia las características de control remoto de llamadas disponibles para el usuario.



</div>

  - Efectuar una llamada realizada

  - Responder a una llamada entrante

  - Responder a una llamada entrante con un mensaje instantáneo
    
    <div>
    

    > [!NOTE]  
    > Es decir, cuando el número de teléfono del autor de la llamada puede asociarse con una dirección de mensaje instantáneo en la lista global de direcciones (GAL) de la organización, en la lista de contactos de Lync del destinatario de la llamada o en la organización de un socio federado.

    
    </div>

  - Transferir una llamada

  - Desviar una llamada entrante

  - Poner llamadas en espera

  - Alternar entre varias llamadas simultáneas

  - Responder a una segunda llamada mientras se está participando en una llamada (es decir, poner llamadas en espera)

  - Marcar dígitos de tono de marcado de frecuencia múltiple (DTMF)

  - En la ventana Conversación, escribir notas en el programa Microsoft Office OneNote

Además, cuando un usuario está habilitado para el control remoto de llamadas, Lync 2013 proporciona al usuario la siguiente información de llamada:

  - Identificación de un llamador por nombre cuando existe el número de teléfono del autor de la llamada en la lista de contactos de un cliente de mensajería y colaboración de Microsoft Office Outlook habilitado para el control de llamadas remotos, la lista de contactos de Lync o la GAL de la organización.

  - Últimas llamadas entrantes y realizadas, que se guardan en la carpeta Historial de conversaciones de Outlook.

  - Las notificaciones de llamadas perdidas, que se envían a la carpeta Bandeja de entrada de Outlook del usuario, pero se generan solo si Lync se ejecuta cuando se recibe la llamada entrante.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Control remoto de llamadas y Telefonía IP empresarial

Aunque las características de control remoto de llamadas son independientes de las características de Enterprise Voice y los usuarios no se pueden habilitar para ambas, la telefonía IP empresarial proporciona un subconjunto de características que también están disponibles para los usuarios que están habilitados para el control remoto de llamadas. Si se implementa la telefonía IP empresarial, los usuarios habilitados para el control remoto de llamadas pueden usar Lync para acceder a las siguientes características de telefonía IP empresarial:

  - Realizar y recibir llamadas de audio a otro cliente de Lync

  - Unirse a la parte de audio de una conferencia creada por un usuario que está habilitado para telefonía IP empresarial

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Tareas de implementación para el control remoto de llamadas en Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

