---
title: 'Lync Server 2013: Definir los requisitos para la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organizations's requirements for monitoring
ms:assetid: d587ff04-9af6-4ac1-ad42-076e7a40ac75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205284(v=OCS.15)
ms:contentKeyID: 48185491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7a81f83cddca46a50f84fb20785a59b20a3db78
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-monitoring-in-lync-server-2013"></a>Definir los requisitos para la supervisión en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-05_

La simplificación de la implementación y la instalación de la supervisión en Microsoft Lync Server 2013 también ha simplificado los procesos implicados en la definición de los requisitos de la organización para la supervisión. Sin embargo, hay varios problemas clave que se deben solucionar antes de empezar a instalar y configurar Lync Server 2013:

**¿Qué tipo de datos desea supervisar?** Lync Server 2013 permite supervisar dos tipos de datos diferentes: datos de grabación de llamadas en profundidad (CDR) y datos de calidad de la experiencia (QoE). La grabación de detalles de llamadas le permite realizar un seguimiento del uso de las características de Lync Server, como las llamadas telefónicas de voz a través de IP (VoIP); mensajería instantánea (mi); transferencias de archivos; conferencias de audio y vídeo (A/V); y sesiones de uso compartido de aplicaciones. Esta información le ayuda a saber qué características de Lync Server se usan (y cuáles no) y también proporciona información sobre cuándo se usan estas características. Los datos de calidad de la experiencia permiten mantener un registro de la calidad de las llamadas de audio y vídeo realizadas en la organización e incluyen, entre otros, la cantidad de paquetes de red perdidos, el ruido de fondo y la cantidad de "vibración" (diferencias en el retraso de paquetes).

Si elige habilitar la supervisión en Lync Server 2013 puede habilitar la supervisión de CDR y la supervisión de QoE, o bien, puede elegir habilitar un tipo de supervisión y dejar el otro tipo deshabilitado. Por ejemplo, supongamos que sus usuarios usan la mensajería instantánea y la transferencia de archivos, pero no las llamadas de audio o vídeo. En este caso, no tiene sentido habilitar la supervisión de QoE. Del mismo modo, Lync Server facilita la activación y desactivación de la supervisión después de implementar la supervisión. Por ejemplo, supongamos que decidió implementar la supervisión, pero con la supervisión de QoE inicialmente deshabilitada. Si los usuarios empiezan a tener problemas con las llamadas de audio o vídeo, puede habilitar la supervisión de QoE y usar los datos obtenidos para solucionar más fácilmente estos problemas.

No hay ventajas (o desventaja) específicas para instalar la supervisión al mismo tiempo que se instala Lync Server frente a la instalación de supervisión después de instalar Lync Server. Solo hay que tener en cuenta que, antes de instalar la supervisión, es preciso seleccionar un equipo para que hospede el almacén de supervisión de back-end y que ese equipo precisa tener una versión compatible de SQL Server instalada y configurada para poder usarlo en la supervisión. Si ya ha instalado SQL Server en un equipo y ese equipo está listo para su uso, puede instalar la supervisión al mismo tiempo que instala Lync Server. Si no tiene un equipo de back-end listo, puede seguir instalando Lync Server por sí mismo y, a continuación, instalar la supervisión siempre que el equipo back-end esté listo para su uso.

**¿Cuándo desea instalar la supervisión?** La supervisión se puede instalar y configurar al mismo tiempo que se instala y configura Lync Server 2013; el Asistente para la implementación de Lync Server le proporcionará la oportunidad de asociar los grupos front-end con una base de datos de supervisión durante la configuración. Como alternativa, puede instalar la supervisión después de instalar Lync Server. Esto se puede realizar con el generador de topologías para asociar los servidores y los servidores front-end con una base de datos de supervisión y, a continuación, publicar la topología revisada.

**¿Cuántas bases de datos de supervisión de backend necesita?** Una sola base de datos de supervisión puede admitir decenas de miles de usuarios (para Microsoft Lync Server 2010, se estimó que una base de datos colocada para la supervisión y el archivado podrían admitir 240.000 usuarios). Además, varias agrupaciones front end pueden usar una sola base de datos de supervisión; Si tiene tres grupos front-end de su organización, puede asociar los tres grupos con el mismo almacén de back-end.

Esto significa simplemente que, para muchas organizaciones, la capacidad de la base de datos no será el factor decisivo a la hora de determinar el número de bases de datos de supervisión de back-end que serán necesarias. En su lugar, es posible que se dé más importancia a la velocidad de red. Supongamos que tiene tres grupos de servidores front-end, pero uno de estos grupos de servidores se encuentra en una conexión de red lenta. En ese caso, puede que desee tener dos bases de datos de supervisión: una base de datos para los dos grupos de servidores con la conexión de red buena y otra base de datos para el grupo de servidores con la conexión de red más lenta.

Al planear la infraestructura de supervisión, también debe tener en cuenta que Lync Server 2013 admite el uso de bases de datos reflejadas. La creación de reflejo de la base de datos es una forma de mantener al mismo tiempo dos copias de una base de datos, cada una de ellas en un servidor diferente. Cada vez que se escriben datos en la base de datos principal, esos mismos datos se escriben en la base de datos reflejada. Si la base de datos principal da error o no está disponible, puede realizar la "conmutación por error" en la base de datos reflejada mediante un simple comando de PowerShell de Lync Server. Por ejemplo:

    Invoke-CsDatabaseFailover -PoolFqdn atl-cs-001.litwareinc.com -DatabaseType "Monitoring" -NewPrincipal "Mirror"

En términos de planeación, esto es importante, ya que será necesario duplicar la cantidad de bases de datos necesarias, ya que, aparte de cada base de datos principal, necesitará otra base de datos que haga de reflejo.

**¿Los sitios de Lync Server necesitan tener sus propias configuraciones de supervisión personalizadas?** Al instalar Lync Server 2013, también instalará colecciones globales de parámetros de configuración de CDR y QoE; Estas colecciones internacionales le ofrecen la posibilidad de aplicar la misma configuración de CDR y QoE a toda la organización. In many cases, this will be sufficient: often-times you will want, say, to have CDR monitoring enabled for all of your users.

En cambio, en ocasiones querrá aplicar otras configuraciones en sitios diferentes. Por ejemplo, quizás quiera usar la supervisión de CDR y QoE en el sitio de Redmond, pero desee usar solo la supervisión de CDR en el sitio de Dublín. Igualmente, es posible que quiera conservar los datos de supervisión durante 60 días en el sitio de Redmond, y mantener ese mismo tipo de datos durante 30 días en el sitio de Dublín. Lync Server 2013 le permite crear colecciones independientes de opciones de configuración de CDR y QoE en el ámbito del sitio; Esto le permite administrar cada sitio de forma diferente. De esta forma, podrá administrar cada sitio de forma diferente (esto incluye la habilitación y la deshabilitación de la supervisión, así como también la configuración de las opciones de administración como, por ejemplo, cuánto tiempo se retendrán los datos).

Puede tomar esta decisión antes o después de implementar la supervisión. Por ejemplo, implemente la supervisión y administre toda la organización con la configuración global. Si más tarde cambia de opinión, cree una colección de opciones independiente para, por ejemplo, el sitio de Redmond y después use esta configuración para administrar la supervisión de Redmond. (La configuración aplicada en el ámbito de sitio siempre tiene preferencia sobre la configuración aplicada en el ámbito global). Si vuelve a cambiar de opinión, solo tiene que eliminar las opciones de configuración aplicadas al sitio de Redmond. Cuando se elimina una colección de opciones de configuración de un sitio, se aplica automáticamente la colección global de configuración al sitio.

</div>

<span> </span>

</div>

</div>

</div>

