---
title: Distribución de la carga de conferencias de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd78b6dcedc66f5a2235b45066be7faf70d4379b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Distribución de la carga de conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

A diferencia de otras soluciones de conferencia dedicadas, la arquitectura de Lync Server es un modelo de hardware compartido. Esto significa que muchos componentes de software comparten el mismo hardware, cada uno de los cuales es compatible con diferentes comunicaciones en tiempo real. Cada tipo de comunicación en tiempo real coloca cargas específicas en los servidores. Por ejemplo, el servidor front-end puede ejecutar los componentes de enrutamiento protocolo de inicio de sesión (SIP), aplicaciones web (como la búsqueda de la libreta de direcciones), servicio de conferencias web, servicio de conferencia A/V, aplicaciones de telefonía empresarial (por ejemplo, conferencias Operador y aplicación de grupo de respuesta) y servidor de mediación. Un conjunto de bases de datos en el servidor front-end también proporciona almacenamiento y procesamiento para datos de usuarios, contactos, presencia, Conferencia y enrutamiento de voz. Con este uso compartido de hardware, los componentes, servicios y procesos se compiten por la CPU y los recursos de memoria, de modo que las cargas de trabajo sin conferencias tengan un impacto directo en la escala de servidores.

Comparado con otras soluciones de conferencia basadas en puertos de hardware, la arquitectura de conferencias de Lync Server es un modelo sin reserva. Cuando un usuario programa una reunión, Lync Server crea un registro en la base de datos de conferencia, que almacena los datos de conferencia, pero no reserva los recursos de hardware para la reunión programada con antelación. En su lugar, Lync Server tiene lógica de equilibrio de carga integrada para asignar dinámicamente los recursos de conferencia en los servidores front-end de modo que se distribuyan uniformemente en todos los servidores front-end del grupo. De esta manera, se aplican y utilizan recursos de hardware, pero hace que resulte desafiante dar soporte a reuniones muy grandes (especialmente sin un plan adecuado). Por ejemplo, cuando se ejecuta una agrupación de Lync Server 2013 cerca de su capacidad máxima, cada servidor front-end podría hospedar aproximadamente 125 reuniones de tamaño medio. Agregar otra reunión pequeña no sería un problema, pero agregar una reunión de 1000 usuarios sería un problema porque los servidores front-end probablemente no podrían admitir una reunión tan grande al mismo tiempo que las otras 125 reuniones.

</div>

<span> </span>

</div>

</div>

</div>

