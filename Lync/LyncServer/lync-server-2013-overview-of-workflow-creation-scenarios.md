---
title: 'Lync Server 2013: Resumen de escenarios de creación de flujo de trabajo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08ecb210ea937184039587d289c5c9c57cb4fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>Resumen de escenarios de creación de flujo de trabajo en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-17_

Al crear flujos de trabajo, hay dos posibles escenarios:

  - **El Administrador crea y configura el flujo de trabajo**: el miembro del rol CsResponseGroupAdministrator (o equivalente) crea y activa el flujo de trabajo y todos los elementos del flujo de trabajo, como los grupos de agentes, colas, días festivos y horario laboral, música, en espera, etc.

  - **El Administrador crea el flujo de trabajo y el Director configura las opciones**: el miembro del rol CsResponseGroupAdministrator (o equivalente) define el URI del SIP principal, Nombre para mostrar, asigna uno o varios miembros del rol CsResponseGroupManager, y selecciona una cola y activa el flujo de trabajo. El CsResponseGroupManager puede iniciar sesión a continuación y editar la configuración del flujo de trabajo creando grupos de agentes y también asigna el grupo a la cola, configurando el número de teléfono, horario laboral y festivos, música, en espera, etc.
    
    <div>
    

    > [!NOTE]  
    > Cuando desee crear un flujo de trabajo administrado, tiene que crear el flujo de trabajo como activo. Tras guardar un flujo de trabajo activo y administrado, modifique y desactive el flujo de trabajo.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

