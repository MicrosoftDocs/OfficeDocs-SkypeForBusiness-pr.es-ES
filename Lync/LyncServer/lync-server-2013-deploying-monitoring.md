---
title: 'Lync Server 2013: implementación de la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49d62537f91145803f60f51c18b86816a0af657f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>Implementación de la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-17_

Se han realizado cambios importantes en la infraestructura de supervisión de Microsoft Lync Server 2013, comenzando con el hecho de que la función de servidor de supervisión está en desuso. En lugar de roles de servidor de supervisión independientes (que normalmente requerían que las organizaciones configuraran equipos dedicados para que actuaran como servidores de supervisión) se instalan ahora servicios de supervisión en cada servidor front-end. Entre otras cuestiones, este cambio ayuda a:

  - Reduzca el número de roles de servidor necesarios al implementar Lync Server 2013. En este caso, al dejar de usar el servidor de supervisión también se contribuye a reducir costes eliminando la necesidad de mantener servidores dedicados para supervisión.

  - Reduzca la complejidad de la configuración y la administración de Lync Server. Al instalar automáticamente los servicios de supervisión en cada servidor front-end ya no tiene que instalar, configurar y administrar el rol del servidor de supervisión.

<div>


> [!NOTE]  
> El rol de servidor de archivado también está en desuso en Lync Server 2013. Al igual que los servicios de supervisión, los servicios de archivado de Lync Server 2013 ahora se colocan en cada servidor front-end. Esto es importante tenerlo en cuenta simplemente porque la supervisión y el archivado a menudo comparten la misma instancia de base de datos de SQL Server.



</div>

Como puede esperar, estos cambios tienen un impacto principal en la manera en que se instalan y se administran los servicios de supervisión. Por ejemplo, como el rol del servidor de supervisión ya no existe, el nodo del servidor de supervisión se ha quitado del generador de topologías de Lync Server; a su vez, esto significa que ya no usa el nuevo servidor de supervisión del generador de topologías para agregar un nuevo servidor de supervisión a la topología. (El asistente ya no existe). En su lugar, normalmente implementará los servicios de supervisión en la topología completando los dos pasos siguientes:

1.  Habilitación de la supervisión al mismo tiempo que configura un nuevo grupo de Lync Server. (En Lync Server 2013, la supervisión está habilitada o deshabilitada de forma agrupada por grupo). Tenga en cuenta que puede habilitar la supervisión de un grupo de servidores sin realmente recopilar datos de supervisión, un proceso que se explica en la sección configuración del registro de detalles de llamadas y de la calidad de la experiencia de esta documentación.

2.  Asociando un almacén de supervisión (es decir, una base de datos de supervisión) con el nuevo grupo de servidores. Tenga en cuenta que un único almacén de supervisión se puede asociar con varios grupos de servidores. En función del número de usuarios hospedados en sus grupos de servidores del registrador, eso significa que no tiene que configurar una base de datos de supervisión independiente para cada uno de sus grupos de servidores. En su lugar, el almacén de supervisión único se puede usar por varios grupos de servidores.

Aunque a menudo es más sencillo habilitar la supervisión al mismo tiempo que crea un nuevo grupo de servidores, también es posible crear un nuevo grupo de servidores con la supervisión deshabilitada. Si lo hace, posteriormente podrá usar el Generador de topología para habilitar el servicio: el Generador de topologías ofrece una manera de habilitar o deshabilitar la supervisión para un grupo de servidores, o para asociar un grupo de servidores con un almacén de supervisión diferente. Tenga en cuenta que aunque ya no hay un rol de servidor de supervisión, todavía tendrá que crear uno o más almacenes de supervisión: bases de datos back-end usadas para almacenar los datos recopilados por el servicio de supervisión. Estas bases de datos back-end se pueden crear con Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012.

<div>


> [!NOTE]  
> Si se ha habilitado la supervisión para un grupo de servidores, puede deshabilitar el proceso de recopilación de datos de supervisión sin tener que cambiar la topología: el shell de administración de Lync Server proporciona una forma de deshabilitar (y volver a habilitar) el registro detallado de llamadas (CDR) o la calidad de la experiencia (QoE) de recopilación de datos. Para obtener más información, vea la sección de configuración del registro de detalles de llamadas y los valores de calidad de experiencia de este documento.



</div>

Otra mejora importante para la supervisión en Lync Server 2013 es que los informes de supervisión de Lync Server ahora admiten IPv6: los informes que usan el campo de dirección IP mostrarán las direcciones IPv4 o IPv6, según: 1) la consulta SQL que se usa; y 2) donde la dirección IPv6 se almacena en la base de datos de supervisión.

<div>


> [!NOTE]  
> Asegúrese de que el tipo de inicio del servicio Agente SQL Server es automático y de que el servicio del Agente SQL Server se está ejecutando para la instancia de SQL que retiene las bases de datos de supervisión, de modo que los trabajos de mantenimiento de SQL Server de supervisión predeterminada puedan ejecutarse de acuerdo a su programación. bajo el control del servicio del Agente SQL Server.



</div>

Esta documentación le guiará por el proceso de instalación y configuración de los informes de supervisión y supervisión para Lync Server 2013. La documentación proporciona instrucciones detalladas que le ayudarán a:

  - Habilitar la supervisión en su topología y asociar un almacén de supervisión a un grupo de servidores front-end.

  - Instale SQL Server Reporting Services y los informes de supervisión de Lync Server. Los informes de supervisión son informes preconfigurados que ofrecen diferentes vistas sobre la información almacenada en una base de datos de supervisión.

  - Configure el registro de detalles de llamada (CDR) y la recopilación de datos de calidad de experiencia (QoE). El registro detallado de llamadas permite realizar un seguimiento del uso de las capacidades de Lync Server, como llamadas telefónicas de voz sobre IP (VoIP); mensajería instantánea (mi); transferencias de archivos; Conferencia de audio/vídeo (A/V); y sesiones de uso compartido de aplicaciones. Las métricas QoE controlan la calidad de las llamadas de audio y vídeo de la organización, incluyen datos sobre el número de paquetes perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

  - Depure manualmente los registros de CDR y/o QoE de la base de datos de supervisión.

</div>

<span> </span>

</div>

</div>

</div>

