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
ms.openlocfilehash: 45707cafca4a7ed9da7cdeb5e162128ccd73468d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a>Componentes y topologías para el servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

El servidor de chat persistente admite configuraciones de un solo servidor y de varios servidores. El servidor de chat persistente también puede ejecutarse en un servidor de Lync Server 2013 Standard Edition. Estas configuraciones constan de los siguientes componentes y topologías del servidor de chat persistente.

<div>

## <a name="persistent-chat-server-components"></a>Componentes del servidor de chat persistente

La instalación de la versión más reciente del servidor de chat persistente requiere los siguientes componentes:

  - Uno o más equipos que ejecuten el servidor de chat persistente y proporcionen los siguientes servicios:
    
      - Servicio de chat persistente
    
      - Servicio de cumplimiento, que se activa si el cumplimiento está habilitado
    
    <div>
    

    > [!IMPORTANT]  
    > En Lync Server 2013, los servicios Web de chat persistente para la carga y descarga de archivos se encuentra ahora en&nbsp;el servidor front-end de lync Server 2013.<BR>Los servicios Web de chat persistente para la administración de salones de chat también se combinan&nbsp;con el servidor front-end de Lync Server 2013.

    
    </div>

  - Servidores (es decir, más de un servidor si se usa la creación de reflejo) que hospeden la base de datos back-end de SQL Server para hospedar la base de datos de contenido de chat persistente en la que se almacenan el contenido, las salas y las categorías de los salones de chat.
    
    <div>
    

    > [!NOTE]  
    > La base de datos back-end almacena los datos del historial de chat, incluida la información sobre categorías y salones de chat persistente que se crean.

    
    </div>

  - Si se habilitó el cumplimiento normativo, se crearán un servidor (es) (más de un servidor si se usa la creación de reflejo) que hospeden la base de datos back-end de SQL Server para hospedar la base de datos de cumplimiento de chat persistente, en la que se almacenan los eventos de cumplimiento y el contenido de chat para fines de cumplimiento.

Para administrar el servidor de chat persistente desde un equipo independiente (como una consola administrativa), use el panel de control de Lync Server en el equipo. A continuación, este equipo debe implementarse en un dominio de servicios de dominio de Active Directory, con al menos un servidor de catálogo global en la raíz del bosque.

Para obtener más información acerca de los requisitos de hardware y software para el servidor de chat persistente, consulte [Technical Requirements for persistent chat Server in Lync server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server Software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación de compatibilidad.

</div>

<div>

## <a name="supported-collocation"></a>Escenarios de instalación compatibles

Lync Server 2013 admite una amplia variedad de escenarios de combinación, lo que proporciona la flexibilidad necesaria para ahorrar costos de hardware mediante la ejecución de varios componentes en un servidor (si tiene una organización pequeña) o para ejecutar componentes individuales en diferentes servidores (si tiene un organización más grande que necesita escalabilidad y rendimiento). Los factores de escalabilidad se deben tener en cuenta antes de decidir si los componentes se van a combinar.

El servicio de cumplimiento de chat persistente, si el cumplimiento está habilitado, se combina con el servidor front-end de Lync Server 2013.

El servidor de chat persistente se puede implementar en el servidor Standard Edition. El servidor back-end del servidor de chat persistente y la base de datos de cumplimiento de chat persistente se pueden combinar en el servidor Standard Edition en el servidor back-end local de SQL Server Express. Para obtener más información sobre los componentes que se pueden combinar allí, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.

Para Lync Server 2013 Enterprise Edition, los servidores de chat persistente no se pueden combinar en el servidor Enterprise Edition. La base de datos de SQL Server para el servidor de chat persistente se puede combinar con la base de datos del servidor back-end de un grupo de servidores front-end Enterprise Edition. La base de datos de SQL Server para el cumplimiento de chat persistente también se puede combinar con la base de datos del servidor back-end de un grupo de servidores Enterprise Edition.

<div>


> [!IMPORTANT]  
> El servidor que hospeda la base de datos de chat persistente puede hospedar otras bases de datos. Sin embargo, cuando considere la posibilidad de combinar la base de datos de chat persistente con otras bases de datos, tenga en cuenta que si está almacenando los mensajes de más de unos pocos usuarios, el espacio en disco que necesita la base de datos de chat persistente puede aumentar considerablemente. Por este motivo, no se recomienda combinar la base de datos de chat persistente con la base de datos back-end.



</div>

Si combinar la base de datos de chat persistente con la base de datos back-end, puede usar una única instancia de SQL Server para cualquiera o todas las bases de datos, o puede usar una instancia independiente de SQL Server para cada base de datos, con la siguiente limitación:

  - Cada instancia de SQL Server puede contener una sola base de datos back-end y una sola base de datos de chat persistente.

Para obtener más información sobre la combinación de todos los roles de servidor y las bases de datos, consulte [Supported Server combinación en Lync server 2013](lync-server-2013-supported-server-collocation.md) en la documentación sobre compatibilidad.

</div>

<div>

## <a name="persistent-chat-server-topologies"></a>Topologías de servidor de chat persistente

El servidor de chat persistente admite las siguientes topologías:

  - Servidor front-end de servidor de chat persistente de servidor único de Lync Server 2013 Enterprise Edition

  - Servidor front-end de servidor de chat persistente de varios servidores de Lync Server 2013 Enterprise Edition

  - Lync Server 2013 servidor Standard Edition con SQL Server Express

  - Servidor de Lync Server 2013 Standard Edition y servidor de chat persistente en un servidor independiente que usa un servidor Standard Edition como servidor del próximo salto.

Puede Agregar un servidor de chat persistente a la implementación de Lync Server 2013 mediante el generador de topologías. Puede Agregar un servidor único o un grupo de servidores de chat persistente de varios servidores a la topología.

<div>


> [!IMPORTANT]  
> Después de crear un grupo de servidores de chat persistente con un único servidor mediante el generador de topologías, no puede agregar más servidores al grupo.



</div>

<div>

## <a name="single-server-topology"></a>Topología de un solo servidor

La configuración mínima y la implementación más sencilla para el servidor de chat persistente son una única topología de servidor front-end de chat persistente. Esta implementación requiere un único servidor que ejecute el servidor de chat persistente (que, opcionalmente, ejecuta el servicio de cumplimiento, si el cumplimiento está habilitado), un servidor que hospede la base de datos de SQL Server y, si es necesario el cumplimiento normativo, la base de datos de SQL Server para almacenar el datos de cumplimiento.

<div>


> [!IMPORTANT]  
> No puede agregar servidores adicionales a un grupo de servidores de chat persistente que se inicie como una implementación de un solo servidor en el generador de topologías. Recomendamos usar la topología de grupo de varios servidores (aun cuando vaya a usar un solo servidor) para que, de este modo, pueda agregar más servidores posteriormente si así lo necesita.



</div>

En la siguiente figura se muestran todos los componentes necesarios y opcionales de una topología para un servidor front-end de servidor de chat persistente único con el cumplimiento normativo.

**Servidor de chat persistente único**

![Topología de un solo servidor con servicio de cumplimiento](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de un solo servidor con servicio de cumplimiento")

</div>

<div>

## <a name="multiple-server-topology"></a>Topología de varios servidores

Para proporcionar mayor capacidad y confiabilidad, puede implementar una topología de varios servidores, como se describe en [Planning for persistent chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topología de varios servidores puede incluir hasta cuatro equipos activos que ejecutan el servidor de chat persistente (la alta disponibilidad y las configuraciones de recuperación ante desastres permiten hasta ocho, pero solo cuatro pueden estar activos y los cuatro restantes en espera). Cada servidor puede admitir hasta 20.000 usuarios simultáneos, para un total de 80.000 usuarios simultáneos conectados a un grupo de servidores de chat persistente con 4 servidores. Una topología de varios servidores es la misma que la topología de un único servidor, excepto en que varios servidores hospedan un servidor de chat persistente y pueden escalar más. Los distintos equipos que ejecutan el servidor de chat persistente deben residir en el mismo dominio de servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.

En la siguiente figura se muestran todos los componentes de una topología de varios servidores con varios equipos que ejecutan el servidor de chat persistente, el servicio opcional de cumplimiento y una base de datos de cumplimiento independiente.

**Varios servidores de chat persistente**

![Topología de varios servidores](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")

Las topologías de varios servidores permiten agrupar las funciones de servidor. En un grupo de servidores, los servicios de chat persistente se comunican y comparten datos. Por ejemplo, el historial de chat que se publicó originalmente en un servicio de chat persistente está disponible desde cualquier servicio de chat persistente en el sistema. Cualquier servicio de chat persistente puede acceder a un archivo que se carga a través de un servicio de chat persistente. Los usuarios pueden conectarse a diferentes servidores front-end del servidor de chat persistente y pueden estar chateando y comunicándose entre sí.

El puerto predeterminado TCP 8011 conecta un servidor a un grupo de servidores y lo usa el servicio de chat persistente para comunicarse entre ellos o con fines administrativos.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

