---
title: 'Lync Server 2013: componentes y topologías para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 862635d091a216df61058c0f0ff00eaa9d32a0c2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Componentes y topologías para el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

El servidor de chat persistente admite configuraciones de servidor único y configuraciones de varios servidores. El servidor de chat persistente también puede ejecutarse en un servidor de Lync Server 2013 Standard Edition. Estas configuraciones se componen de los siguientes componentes y topologías de servidores de chat persistentes.

<div>

## <a name="persistent-chat-server-components"></a>Componentes del servidor de chat persistentes

La instalación de la versión más reciente del servidor de chat persistente requiere los siguientes componentes:

  - Uno o más equipos que ejecutan el servidor de chat persistente y proporcionan los siguientes servicios:
    
      - Servicio de chat persistente
    
      - Servicio de cumplimiento, que se activa si el cumplimiento está habilitado
    
    <div>
    

    > [!IMPORTANT]  
    > En Lync Server 2013, los servicios Web de chat persistente para carga y descarga de archivos se colocan ahora&nbsp;con el servidor front-end de lync Server 2013.<BR>Los servicios Web de chat persistentes para la administración de salones de chat también se&nbsp;colocan con el servidor front-end de Lync Server 2013.

    
    </div>

  - Servidores (es decir, hay más de un servidor si se usa el reflejo) que hospedan la base de datos back-end de SQL Server para hospedar la base de datos de contenido de chat persistente en la que se almacenan el contenido, las salas y las categorías del salón de chat.
    
    <div>
    

    > [!NOTE]  
    > La base de datos back-end almacena los datos del historial de chats, incluida información sobre categorías y salones de chat persistentes que se crean.

    
    </div>

  - Si se ha habilitado la compatibilidad, se pueden almacenar servidores (más de un servidor, si se usan reflejo) que hospedan la base de datos back-end de SQL Server para hospedar la base de datos de cumplimiento de chats persistentes, en la que se almacenan los eventos de cumplimiento y el contenido de chat para fines de cumplimiento.

Para administrar el servidor de chat persistente desde un equipo independiente (como una consola administrativa), use el panel de control de Lync Server en el equipo. Este equipo debe implementarse en un dominio de servicios de dominio de Active Directory, con al menos un servidor de catálogo global en la raíz del bosque.

Para obtener más información sobre los requisitos de hardware y software para el servidor de chat persistente, consulte [los requisitos técnicos para el servidor de chat persistente en Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [hardware compatible para Lync Server 2013](lync-server-2013-supported-hardware.md), así como compatibilidad de la [infraestructura y el software de servidor en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación de soporte técnico.

</div>

<div>

## <a name="supported-collocation"></a>Collocation compatibles

Lync Server 2013 admite una gran variedad de escenarios collocation, lo que le ofrece la flexibilidad de ahorrar costos de hardware ejecutando varios componentes en un servidor (si tiene una pequeña organización) o para ejecutar componentes individuales en diferentes servidores (si tiene una organización más grande que necesita escalabilidad y rendimiento). Los factores de escalabilidad se deben considerar sin duda antes de decidir si se Collocate los componentes.

El servicio de cumplimiento de chat persistente, si el cumplimiento está habilitado, se encuentra en el servidor front-end de Lync Server 2013.

Se puede implementar el servidor de chat persistente en el servidor Standard Edition. El servidor back-end de servidor de chat persistente y la base de datos de cumplimiento de chat persistente se pueden colocar en el servidor Standard Edition en el servidor de back-end local de SQL Server Express. Para obtener más información sobre los componentes que se pueden colocar aquí, consulte [compatibilidad de servidor collocation en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de soporte técnico.

Para Lync Server 2013 Enterprise Edition, los servidores de chat persistentes no se pueden colocar en el servidor Enterprise Edition. La base de datos de SQL Server para el servidor de chat persistente puede colocarse con la base de datos del servidor back-end de un grupo de servidores front end Enterprise Edition. La base de datos de SQL Server para el cumplimiento persistente de la conversación también puede incluirse con la base de datos servidor back-end de un grupo de servidores Enterprise Edition.

<div>


> [!IMPORTANT]  
> El servidor que hospeda la base de datos de chat persistente puede hospedar otras bases de datos. Sin embargo, cuando considere collocating la base de datos de chat persistente con otras bases de datos, tenga en cuenta que si está almacenando los mensajes de más de unos pocos usuarios, el espacio en disco necesario para la base de datos de chat persistente puede crecer muy grande. Por esta razón, no recomendamos collocating la base de datos de chat persistente con la base de datos back-end.



</div>

Si Collocate la base de datos de chat persistente con la base de datos back-end, puede usar una única instancia de SQL Server para cualquiera de las bases de datos o todas ellas, o bien puede usar una instancia independiente de SQL Server para cada base de datos, con la siguiente limitación:

  - Cada instancia de SQL Server puede contener una única base de datos back-end y una única base de datos de chat persistente.

Para más información sobre collocation de todos los roles de servidor y bases de datos, consulte compatibilidad con [servidores de collocation en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de soporte.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Topologías de servidores de chat persistentes

El servidor de chat persistente admite las siguientes topologías:

  - Servidor de servidor front-end de servidor de mensajería instantánea de servidor de Lync Server 2013 Enterprise Edition

  - Servidor front-end de servidor de la mensajería instantánea de Lync Server 2013 Enterprise Edition

  - Servidor de Lync Server 2013 Standard Edition con SQL Server Express

  - Servidor de Lync Server 2013 Standard Edition y servidor de chat persistente en un servidor independiente que usa un servidor Standard Edition como servidor del próximo salto.

Puede Agregar un servidor de chat persistente a la implementación de Lync Server 2013 mediante el generador de topologías. Puede Agregar un servidor único o un grupo de servidores de chat persistente de servidor múltiple a su topología.

<div>


> [!IMPORTANT]  
> Después de crear un grupo de servidores de chat persistente con un único servidor mediante el generador de topologías, no puede agregar servidores adicionales al grupo.



</div>

<div>

## <a name="single-server-topology"></a>Topología de servidor único

La configuración mínima y la implementación más sencilla para el servidor de chat persistente es una topología única de servidor de chat persistente. Esta implementación requiere un único servidor que ejecute el servidor de chat persistente (que, opcionalmente, ejecuta el servicio de cumplimiento, si el cumplimiento está habilitado), un servidor que hospede tanto la base de datos de SQL Server como la de la base de datos de SQL Server para almacenar el datos de cumplimiento.

<div>


> [!IMPORTANT]  
> No puede agregar servidores adicionales a un grupo de servidores de chat persistente que se inicie como una implementación de servidor único en el generador de topología. Le recomendamos que use la topología del grupo de varios servidores, incluso si está usando un solo servidor, para que pueda agregar más servidores más adelante, si es necesario.



</div>

La siguiente ilustración muestra todos los componentes obligatorios y opcionales de una topología para un único servidor de usuario de chat persistente con cumplimiento normativo.

**Servidor único de chat persistente**

![Topología de servidor único con servicio de cumplimiento](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de servidor único con servicio de cumplimiento")

</div>

<div>

## <a name="multiple-server-topology"></a>Topología de varios servidores

Para proporcionar mayor capacidad y confiabilidad, puede implementar una topología de varios servidores, como se describe en [planear el servidor de chat persistente en Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecutan el servidor de chat persistente (la alta disponibilidad y las configuraciones de recuperación ante desastres permiten hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en espera). Cada servidor puede admitir hasta 20.000 usuarios simultáneos, para un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores. Una topología de varios servidores es la misma que la topología de servidor único, excepto en que varios servidores hospedan un servidor de chat persistente y pueden escalar más alto. Varios equipos que ejecutan el servidor de chat persistente deben residir en el mismo dominio de servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.

La siguiente ilustración muestra todos los componentes de una topología de varios servidores con varios equipos que ejecutan un servidor de chat persistente, el servicio de cumplimiento opcional y una base de datos de cumplimiento independiente.

**Varios servidores de chat persistentes**

![Topología de varios servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")

Las topologías de varios servidores permiten agrupar las funciones de servidor. En un grupo de servidores, los servicios de chat persistentes se comunican y comparten datos. Por ejemplo, el historial de conversaciones publicado originalmente en un servicio de chat persistente está disponible desde cualquier servicio de chat persistente en el sistema. Cualquier servicio de chat persistente puede acceder a un archivo que se carga a través de un servicio de chat persistente. Los usuarios se pueden conectar a diferentes servidores de aplicaciones para el servidor de mensajería instantánea y pueden estar conversando y comunicándose entre sí.

El puerto predeterminado de TCP 8011 conecta un servidor a un grupo de servidores y lo usa el servicio de chat persistente para comunicarse entre sí o con fines administrativos.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

