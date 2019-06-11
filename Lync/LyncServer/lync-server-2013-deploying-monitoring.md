---
title: 'Lync Server 2013: implementación de la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying monitoring
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398199(v=OCS.15)
ms:contentKeyID: 48183442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 584b99b6e5fad72a07a35b748ab9bafa4116701a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-monitoring-in-lync-server-2013"></a>Implementación de la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-17_

Se han realizado cambios importantes en la infraestructura de supervisión de Microsoft Lync Server 2013, comenzando con el hecho de que el rol de servidor de supervisión ha quedado obsoleto. En lugar de roles de servidor de supervisión independientes (que suelen requerir que las organizaciones configuren equipos dedicados para que actúen como servidores de supervisión), los servicios de supervisión ahora se colocan en cada servidor front-end. Entre otras cosas, este cambio ayuda a:

  - Reduzca el número de roles de servidor necesarios al implementar Lync Server 2013. En este caso, disminuir la función de servidor de supervisión también ayuda a reducir los costos al eliminar la necesidad de mantener servidores dedicados para la supervisión.

  - Reduzca la complejidad de la configuración y la administración de Lync Server. Collocating automáticamente los servicios de supervisión en cada servidor front-end que ya no necesita para instalar, configurar y administrar el rol servidor de supervisión.

<div>


> [!NOTE]  
> El rol servidor de archivado también ha quedado obsoleto en Lync Server 2013. Al igual que los servicios de supervisión, los servicios de archivado de Lync Server 2013 ahora se colocan en cada servidor front-end. Es importante destacar simplemente porque la supervisión y el archivado comparten a menudo la misma instancia de base de datos de SQL Server.



</div>

Como cabría esperar, estos cambios tienen una repercusión importante en el modo en que se instalan y administran los servicios de supervisión. Por ejemplo, puesto que el rol servidor de supervisión ya no existe, el nodo servidor de supervisión se ha quitado del generador de topología de Lync Server; a su vez, esto significa que ya no usará el nuevo Asistente para servidor de supervisión de topología Builder para agregar un nuevo servidor de supervisión a su topología. (El asistente ya no existe). En su lugar, normalmente implementará servicios de supervisión dentro de su topología completando los dos pasos siguientes:

1.  Habilitar la supervisión al mismo tiempo que se configura un nuevo grupo de Lync Server. (En Lync Server 2013, la supervisión está habilitada o deshabilitada para cada grupo). Tenga en cuenta que puede habilitar la supervisión de un grupo sin recopilar realmente datos de supervisión, un proceso descrito en la sección configuración de la configuración de registro de detalles de llamadas y calidad de la experiencia de esta documentación.

2.  Al asociar un almacén de supervisión (es decir, una base de datos de supervisión) con el nuevo grupo de servidores. Tenga en cuenta que un único almacén de supervisión se puede asociar con varios grupos de servidores. En función de la cantidad de usuarios hospedados en los grupos de registradores, no tiene que configurar una base de datos de supervisión independiente para cada uno de los grupos. En su lugar, varios grupos de servidores pueden usar el almacén de supervisión único.

Aunque a menudo es más sencillo habilitar la supervisión al mismo tiempo que crea un nuevo grupo de servidores, también es posible crear un nuevo grupo de servidores con la supervisión deshabilitada. Si lo hace, posteriormente podrá usar el Generador de topología para habilitar el servicio: el Generador de topologías ofrece una manera de habilitar o deshabilitar la supervisión para un grupo de servidores, o para asociar un grupo de servidores con un almacén de supervisión diferente. Tenga en cuenta que, aunque ya no haya un rol de servidor de supervisión, tendrá que crear uno o varios almacenes: bases de datos de back-end usadas para almacenar los datos recopilados por el servicio de supervisión. Estas bases de datos de back-end se pueden crear con Microsoft SQL Server 2008 R2 o Microsoft SQL Server 2012.

<div>


> [!NOTE]  
> Si se ha habilitado la supervisión para un grupo, puede deshabilitar el proceso de recopilación de datos de supervisión sin tener que cambiar su topología: el shell de administración de Lync Server le permite deshabilitar (y volver a habilitar más adelante) la grabación de detalles de llamadas (CDR) o la calidad of Experience (QoE) recopilación de datos. Para obtener más información, vea la sección de configuración del registro de detalles de llamadas y los valores de calidad de experiencia de este documento.



</div>

Otra mejora importante para la supervisión en Lync Server 2013 es el hecho de que los informes de supervisión de Lync Server ahora son compatibles con IPv6: los informes que usan el campo dirección IP mostrarán direcciones IPv4 o IPv6, en función de: 1, la consulta SQL que se usa; y 2) donde la dirección IPv6 está almacenada en la base de datos de supervisión.

<div>


> [!NOTE]  
> Asegúrese de que el tipo de inicio del servicio del Agente SQL Server sea automático y de que el servicio del Agente SQL Server se esté ejecutando para la instancia de SQL que contiene las bases de datos de supervisión, de manera que las tareas de mantenimiento predeterminadas de supervisión de SQL Server puedan ejecutarse según se programaron, bajo el control del servicio del Agente SQL Server.



</div>

Esta documentación le guiará a través del proceso de instalación y configuración de los informes de supervisión y supervisión de Lync Server 2013. En la documentación se proporcionan instrucciones detalladas que le ayudarán a:

  - Habilitar la supervisión en la topología y asociar un almacén de supervisión a un grupo de servidores front-end.

  - Instale SQL Server Reporting Services y los informes de supervisión de Lync Server. Los informes de supervisión son informes previamente configurados que ofrecen diferentes vistas sobre la información almacenada en una base de datos de supervisión.

  - Configurar la recopilación de datos de grabación de detalles de llamadas (CDR) y calidad de la experiencia (QoE). La grabación de detalles de llamadas le permite realizar un seguimiento del uso de las funciones de Lync Server, como llamadas telefónicas de voz a través de IP (VoIP); mensajería instantánea (mi); transferencias de archivos; conferencias de audio y vídeo (A/V); y sesiones de uso compartido de aplicaciones. Las métricas QoE controlan la calidad de las llamadas de audio y vídeo de la organización, incluyen datos sobre el número de paquetes perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

  - Purgue de forma manual los registros de CDR o de QoE de la base de datos de supervisión.

</div>

<span> </span>

</div>

</div>

</div>

