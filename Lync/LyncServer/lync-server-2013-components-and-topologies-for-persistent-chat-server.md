---
title: "Lync Server 2013: Componentes y tipologías para el servidor de chat persistente"
TOCTitle: Componentes y tipologías para el servidor de chat persistente
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48275546
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Componentes y tipologías para el servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-05_

El Servidor de chat persistente admite configuraciones tanto de un solo servidor como de varios servidores. El Servidor de chat persistente también puede ejecutar un Servidor Standard Edition de Lync Server 2013. Estas configuraciones constan de las siguientes topologías y componentes de Servidor de chat persistente.

## Componentes del Servidor de chat persistente

Los siguientes componentes son necesarios para instalar la versión más reciente del Servidor de chat persistente:

  - Uno o más equipos que ejecuten Servidor de chat persistente y proporcionen los siguientes servicios:
    
      - Servicio de Chat persistente
    
      - Servicio de cumplimiento, que se activa si el cumplimiento está habilitado
    
    > [!IMPORTANT]  
    > En Lync Server 2013, los servicios web de carga y descarga de archivos del Chat persistente ahora se combinan con el Servidor front-end de Lync Server 2013.<br />
    > Los servicios web de Chat persistente para administrar salones de chat también se combinan con el Servidor front-end de Lync Server 2013.


  - El servidor o los servidores (más de uno si se usa la creación de reflejos) que hospedan la base de datos back-end de SQL Server para hospedar la base de datos de contenido del Chat persistente en la que se almacenan el contenido, salones y categorías de los salones de chat.
    

    > [!NOTE]
    > La base de datos back-end almacena datos de historial de chat, incluida información sobre las categorías y salones de Chat persistente que se han creado.



  - Si el cumplimiento está habilitado, un servidor o servidores (más de uno si se usa la creación de reflejos) que hospedan la base de datos back-end de SQL Server para hospedar la base de datos de cumplimiento del Chat persistente en la que se almacenan los eventos de cumplimiento y el contenido de los chats con fines de cumplimiento.

Para administrar Servidor de chat persistente desde un equipo independiente (como, por ejemplo, una consola administrativa), utilice el Panel de control de Lync Server en el equipo. A continuación, este equipo debe implementarse en un dominio de Servicios de dominio de Active Directory, con al menos un servidor de catálogo global en la raíz del bosque.

Para obtener más información sobre los requisitos de hardware y software del Servidor de chat persistente, consulte [Requisitos técnicos para el servidor de chat persistente en Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Hardware admitido en Lync Server 2013](lync-server-2013-supported-hardware.md) y [Software de servidor y compatibilidad con la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) en la documentación de compatibilidad.

## Combinación admitida

Lync Server 2013 admite diversos escenarios de combinación, lo que reporta flexibilidad para ahorrar costes de hardware ejecutando varios componentes en un servidor (si la organización es pequeña) o ejecutar componentes individuales en distintos servidores (si se trata de una organización más grande que requiere escalabilidad y rendimiento). Los factores de escalabilidad se deben tener en cuenta antes de decidir si los componentes se van a combinar.

El servicio de cumplimiento del Chat persistente (si el cumplimiento está habilitado), se combina con el Servidor front-end de Lync Server 2013.

El Servidor de chat persistente se implementa en el Servidor Standard Edition. El Servidor back-end de Servidor de chat persistente y la base de datos de cumplimiento de Chat persistente se pueden combinar en el Servidor Standard Edition del Servidor back-end local de SQL Server Express. Para obtener más información sobre los componentes que se pueden combinar ahí, consulte [Instalación de servidores compatibles en Lync Server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de compatibilidad.

En Lync Server 2013Enterprise Edition, los Servidores de chat persistente no se pueden combinar en el Enterprise Edition Server. La base de datos de SQL Server del Servidor de chat persistente se puede combinar con la base de datos del Servidor back-end de un Grupo de servidores front-end de Enterprise Edition. La base de datos de SQL Server para el cumplimiento del Chat persistente también se puede combinar con la base de datos del Servidor back-end de un grupo de servidores Enterprise Edition.

> [!IMPORTANT]  
> El servidor que hospeda la base de datos del Chat persistente puede hospedar otras bases de datos. Sin embargo, cuando piense en combinar la base de datos del Chat persistente con otras bases de datos, tenga en cuenta que si conserva los mensajes de numerosos usuarios, el espacio en disco necesario para la base de datos del Chat persistente puede dispararse. Por este motivo, recomendamos no combinar la base de datos del Chat persistente con la base de datos back-end.



Si combina la base de datos del Chat persistente con la base de datos back-end, puede optar entre usar una única instancia de SQL Server para cualquiera o todas las bases de datos o usar una instancia de SQL Server independiente para cada base de datos, si bien con la siguiente limitación:

  - Cada instancia de SQL Server puede contener una sola base de datos back-end y una sola base de datos de Chat persistente.

Para más información sobre la combinación de todos los roles de servidor y de las bases de datos, consulte [Instalación de servidores compatibles en Lync Server 2013](lync-server-2013-supported-server-collocation.md) en la documentación de compatibilidad.

## Topologías del Servidor de chat persistente

Servidor de chat persistente admite distintas topologías:

  - Lync Server 2013 único servidor Enterprise Edition Servidor de chat persistenteServidor front-end

  - Lync Server 2013 varios servidores Enterprise Edition Servidor de chat persistenteServidor front-end

  - Lync Server 2013Servidor Standard Edition que utiliza SQL Server Express

  - Lync Server 2013Servidor Standard Edition y Servidor de chat persistente en un servidor independiente que utiliza Servidor Standard Edition como el servidor del próximo salto.

Puede agregar el Servidor de chat persistente a su instalación de Lync Server 2013 mediante el Generador de topologías. Puede agregar uno o varios servidores de tipo Grupo de servidores de chat persistente a su topología.

> [!IMPORTANT]  
> Después de crear un Grupo de servidores de chat persistente con un solo servidor mediante el Generador de topologías, no podrá agregar a él más servidores.



## Topología de un solo servidor

La configuración mínima y la implementación más sencilla del Servidor de chat persistente es la topología de un solo Servidor front-end de Servidor de chat persistente. Requiere un servidor único para ejecutar el Servidor de chat persistente (que ejecuta opcionalmente el servicio de cumplimiento, en caso de que este se habilite), un servidor para hospedar la base de datos de SQL Server y, si se requiere el cumplimiento de normas, la base de datos de SQL Server para almacenar los datos de cumplimiento.

> [!IMPORTANT]  
> No se pueden agregar más servidores a un Grupo de servidores de chat persistente que se haya iniciado como una implementación de un solo servidor en el Generador de topologías. Recomendamos usar la topología de grupo de varios servidores (aun cuando vaya a usar un solo servidor) para que, de este modo, pueda agregar más servidores posteriormente si así lo necesita.



En la siguiente ilustración se muestran todos los componentes opcionales y obligatorios de una topología de un solo Servidor front-end de Servidor de chat persistente con el servicio de cumplimiento.

**Un solo servidor de chat persistente**

![Topología de un solo servidor con servicio de cumplimiento](images/Gg615006.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topología de un solo servidor con servicio de cumplimiento")

## Topología de varios servidores

Para ofrecer mayor capacidad y fiabilidad, puede implementar una topología de varios servidores, tal como se describe en [Planeación del servidor de chat persistente en Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md). Con la topología de varios servidores, el Servidor de chat persistente puede estar ejecutándose hasta en cuatro equipos activos (las configuraciones de recuperación ante desastres y la alta disponibilidad permitirán hasta ocho, pero solamente cuatro pueden estar activos, mientras que el resto permanecen en espera). Cada servidor puede admitir un máximo de 20.000 usuarios simultáneos para dar servicio a un total de 80.000 usuarios simultáneos conectados a un Grupo de servidores de chat persistente con 4 servidores. Las topologías de varios servidores son iguales que las de un solo servidor, salvo por el hecho de que el Servidor de chat persistente está hospedado en varios servidores y puede escalarse más. Los equipos en los que se ejecute el Servidor de chat persistente deben residir en el mismo dominio de Servicios de dominio de Active Directory que Lync Server y el servicio de cumplimiento.

En la ilustración siguiente se muestran todos los componentes de una topología de varios servidores con varios equipos en los que se ejecuta el Servidor de chat persistente, el servicio opcional de cumplimiento y una base de datos de cumplimiento independiente.

**Varios servidores de chat persistente**

![Topología de varios servidores](images/Gg615006.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topología de varios servidores")

Las topologías de varios servidores permiten agrupar las funciones de servidor. En un grupo de servidores, los servicios de Chat persistente se pueden comunicar y compartir datos. Por ejemplo, el historial de conversaciones que se registra originalmente en un servicio de Chat persistente estará disponible desde cualquier servicio de Chat persistente en el sistema. Asimismo, cualquier servicio de Chat persistente puede acceder a un archivo que se haya cargado a través de un servicio de Chat persistente. Los usuarios se pueden conectar a distintos Servidores front-end de Servidor de chat persistente y conversar y comunicarse los unos con los otros.

El puerto predeterminado TCP 8011 conecta un servidor con un grupo de servidores y el servicio de Chat persistente lo usa para comunicarse o con fines administrativos.

