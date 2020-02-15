---
title: 'Lync Server 2013: definición de los requisitos para la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a8f411b62aa1368600db21b59b4b009ca6df6c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Definición de los requisitos para la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

La optimización de la implementación y la instalación de la supervisión en Microsoft Lync Server 2013 también ha simplificado los procesos necesarios para definir los requisitos de la organización para la supervisión. No obstante, aún hay varios problemas clave que deben tratarse antes de empezar a instalar y configurar Lync Server 2013:

**¿Qué tipo de datos desea supervisar?** Lync Server 2013 permite supervisar dos tipos de datos diferentes: datos de grabación con detalles de llamadas (CDR) y datos de calidad de la experiencia (QoE). El registro detallado de llamadas permite realizar un seguimiento del uso de las características de Lync Server, como llamadas telefónicas de voz sobre IP (VoIP); mensajería instantánea (mi); transferencias de archivos; Conferencia de audio/vídeo (A/V); y sesiones de uso compartido de aplicaciones. Esta información le ayudará a saber qué características de Lync Server se usan (y cuáles no), y también proporciona información sobre cuándo se usan estas características. Los datos de calidad de la experiencia permiten mantener un registro de la calidad de las llamadas de audio y las videollamadas realizadas en la organización e incluyen, entre otros, el número de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

Si elige habilitar la supervisión en Lync Server 2013, puede habilitar la supervisión de CDR y la supervisión de QoE, o bien, puede elegir habilitar un tipo de supervisión y dejar el otro tipo deshabilitado. Por ejemplo, supongamos que sus usuarios usan la mensajería instantánea y la transferencia de archivos, pero no las audiollamadas ni las videollamadas. En este caso, no tiene sentido habilitar la supervisión QoE. De forma similar, Lync Server facilita la habilitación y deshabilitación de la supervisión después de que se haya implementado la supervisión. Por ejemplo, supongamos que decidió implementar la supervisión, pero con la supervisión QoE inhabilitada. Si los usuarios empiezan a tener problemas con las audiollamadas o las videollamadas, puede habilitar la supervisión QoE y usar los datos obtenidos para solucionar más fácilmente estos problemas.

No hay ventajas (o desventajas) específicas para instalar la supervisión al mismo tiempo que se instala Lync Server frente a la supervisión después de que Lync Server se haya instalado. Solo hay que tener en cuenta que, antes de instalar la supervisión, debe seleccionar un PC para que hospede el almacén de supervisión de back-end y que ese PC debe tener una versión compatible de SQL Server instalada y configurada para poder usarlo en la supervisión. Si ya ha instalado SQL Server en un equipo y ese equipo está listo para su uso, puede instalar la supervisión al mismo tiempo que instala Lync Server. Si no tiene preparado un equipo back-end, puede continuar con la instalación de Lync Server por sí mismo y, a continuación, instalar la supervisión siempre que el equipo back-end esté listo para su uso.

**¿Cuándo desea instalar la supervisión?** La supervisión se puede instalar y configurar al mismo tiempo que se instala y configura Lync Server 2013; el Asistente para la implementación de Lync Server le proporcionará la oportunidad de asociar los grupos de servidores front-end con una base de datos de supervisión durante la instalación. Como alternativa, puede instalar la supervisión después de instalar Lync Server. Esto puede realizarse mediante el generador de topologías para asociar los servidores y grupos de servidores front-end con una base de datos de supervisión y, a continuación, publicar la topología revisada.

**¿Cuántas bases de datos de supervisión de back-end necesita?** Una sola base de datos de supervisión puede admitir decenas de miles de usuarios (para Microsoft Lync Server 2010, se estimó que una base de datos combinada para la supervisión y el archivado podrían admitir 240.000 usuarios). Además, varios grupos de servidores front-end pueden usar una sola base de datos de supervisión; Si tiene tres grupos de servidores front-end de su organización, puede asociar los tres grupos con el mismo almacén de back-end.

Esto significa simplemente que, para muchas organizaciones, la capacidad de la base de datos no será el factor determinante a la hora de determinar el número de bases de datos de supervisión back-end que se necesitarán. En su lugar, es posible que se dé más importancia a la velocidad de red. Supongamos que tiene tres grupos de servidores front-end, pero uno de estos grupos de servidores se encuentra en una conexión de red lenta. En ese caso, puede que desee tener dos bases de datos de supervisión: una base de datos para los dos grupos de servidores con la conexión de red buena, y otra base de datos para el grupo de servidores con la conexión de red más lenta.

Al planear la infraestructura de supervisión, también debe tener en cuenta que Lync Server 2013 admite el uso de bases de datos reflejadas. La creación de reflejo de la base de datos es una forma de mantener al mismo tiempo dos copias de una misma base de datos, cada una de ellas en un servidor diferente. Cada vez que se escriben datos en la base de datos principal, esos mismos datos se escriben en la base de datos reflejada. Si se produce un error en la base de datos principal o no está disponible, puede realizar la "conmutación por error" a la base de datos reflejada mediante un sencillo comando de Lync Server PowerShell. Por ejemplo:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

En términos de planificación, esto es importante, ya que será necesario duplicar el número de bases de datos necesarias: además de cada base de datos principal, necesitará otra base de datos que haga de reflejo.

**¿Los sitios de Lync Server necesitan sus propias configuraciones de supervisión personalizadas?** Al instalar Lync Server 2013, también se instalan colecciones globales de opciones de configuración de CDR y QoE; Estas colecciones globales le ofrecen la posibilidad de aplicar la misma configuración de CDR y QoE a toda la organización. En muchos casos, esto será suficiente: a menudo, lo que quiere decir es que tenga habilitada la supervisión de CDR para todos los usuarios.

Sin embargo, también puede haber ocasiones en las que desee aplicar diferentes configuraciones a sitios diferentes. Por ejemplo, quizás desee usar la supervisión de CDR y QoE en su sitio de Redmond, pero use solo la supervisión de CDR en su sitio de Dublin. Del mismo modo, es posible que desee conservar datos de supervisión durante 60 días en el sitio de Redmond, pero solo necesita mantener este tipo de datos durante 30 días en el sitio de Dublin. Lync Server 2013 permite crear colecciones independientes de opciones de configuración de CDR y QoE en el ámbito del sitio; Esto le permite administrar cada sitio de forma diferente. (Esto incluye la habilitación y deshabilitación de la supervisión, así como la configuración de la administración, como la duración de retención de los datos).

Puede tomar esta decisión antes o después de implementar la supervisión. Por ejemplo, implemente la supervisión y administre toda la organización con la configuración global. Si más tarde cambia de opinión, cree una colección de valores para, por ejemplo, el sitio de Redmond y después use la configuración para administrar la supervisión de Redmond. (La configuración aplicada en el ámbito del sitio, siempre tiene preferencia sobre la configuración aplicada en el ámbito global). Si vuelve a cambiar de opinión, solo tiene que eliminar la configuración aplicada al sitio de Redmond. Cuando se elimina una colección de configuración de un sitio, se aplica automáticamente la colección global de configuración al sitio.

</div>

<span> </span>

</div>

</div>

</div>

