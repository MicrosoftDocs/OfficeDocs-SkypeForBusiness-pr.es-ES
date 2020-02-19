---
title: Lync Server 2013 para la distribución de carga de conferencia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b37c61be4d715751b18581c643babfddae06ea5e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Distribución de carga de conferencia en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

A diferencia de otras soluciones de conferencia dedicadas, la arquitectura de Lync Server es un modelo de hardware compartido. Esto significa que varios componentes de software comparten el mismo hardware, cada uno de los cuales admite diferentes comunicaciones en tiempo real. Cada tipo de comunicación en tiempo real coloca cargas específicas en los servidores. Por ejemplo, el servidor front-end puede ejecutar los componentes de enrutamiento del Protocolo de inicio de sesión (SIP), las aplicaciones web (como la búsqueda de la libreta de direcciones), el servicio de conferencia Web, el servicio de conferencia A/V, las aplicaciones de telefonía IP empresarial (por ejemplo, la aplicación del operador de conferencia y el servidor de mediación). Un conjunto de bases de datos en el servidor front-end también proporciona almacenamiento y procesamiento para datos de usuario, contacto, presencia, Conferencia y enrutamiento de voz. Con este uso compartido de hardware, los componentes, servicios y procesos compiten por la CPU y los recursos de memoria, por lo que las cargas de trabajo que no son de Conferencia tienen un impacto directo en el escalado del servidor.

En comparación con otras soluciones de conferencia basadas en puertos de hardware, la arquitectura de conferencia de Lync Server es un modelo sin reserva. Cuando un usuario programa una reunión, Lync Server crea un registro en la base de datos de conferencia, que almacena los datos de conferencia, pero no reserva ningún recurso de hardware para la reunión programada antes de tiempo. En su lugar, Lync Server tiene una lógica de equilibrio de carga integrada para asignar dinámicamente recursos de conferencia en los servidores front-end de manera que distribuya las cargas equitativamente entre todos los servidores front-end del grupo. Esto hace que las provisiones y el uso de los recursos de hardware sean efectivos, pero dificulta la compatibilidad con reuniones muy grandes (especialmente sin una planeación adecuada). Por ejemplo, cuando se ejecuta un grupo de servidores de Lync Server 2013 cerca de su capacidad máxima, cada servidor front-end puede hospedar aproximadamente 125 reuniones de tamaño medio. Agregar otra reunión pequeña no sería un problema, pero agregar una reunión para 1000 usuarios sería un problema porque los servidores front-end probablemente no podrían admitir una reunión tan grande al mismo tiempo que las otras 125 reuniones.

</div>

<span> </span>

</div>

</div>

</div>

