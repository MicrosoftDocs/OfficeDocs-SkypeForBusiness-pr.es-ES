---
title: 'Lync Server 2013: Componentes y topologías para conferencias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5caf5ba33e863e08bf4f728d2bf11394f37f20b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Componentes y topologías para conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-04_

Al seleccionar conferencias en el generador de topologías, las conferencias se implementan como parte del servidor front-end o del servidor Standard Edition. Las conferencias de acceso telefónico local y el uso compartido de PowerPoint requieren configuración y componentes adicionales. En las siguientes secciones se describen los componentes y las topologías compatibles para conferencias web, conferencias A/V y conferencias de acceso telefónico local.

<div>

## <a name="supported-components"></a>Componentes admitidos

Los únicos componentes que las conferencias web y las conferencias A/V requieren son los servidores front-end de la organización o los servidores Standard Edition. Para obtener una lista de los requisitos de hardware y software para los servidores front-end y los servidores Standard Edition, consulte [hardware admitido para Lync server 2013](lync-server-2013-supported-hardware.md) y [compatibilidad con el software de servidor y la infraestructura en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y el procesamiento de presentaciones de PowerPoint. Para obtener más información sobre cómo instalar y configurar el servidor de Office Web Apps, vea [configurar la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Además de los requisitos para las conferencias web y A/V, las conferencias de acceso telefónico local usan los siguientes componentes de Lync Server 2013:

  - ****   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas (UC). Las conferencias de acceso telefónico local usan dos aplicaciones de comunicaciones unificadas que requieren servicio de aplicación: operador de conferencia y anuncio de conferencia. El servicio de aplicación se instala y activa de forma predeterminada en todos los servidores front-end de un grupo de servidores front-end y en todos los servidores Standard Edition cuando se implementa una carga de trabajo de conferencia y se selecciona la opción de conferencia de acceso telefónico local.

  - ****   El Asistente para conferencias de conferencia del operador de conferencia es una aplicación de comunicaciones unificadas que acepta llamadas de red telefónica conmutada (RTC), reproduce preguntas y une las llamadas a una conferencia a/V. El operador de conferencias se instala y activa de forma predeterminada al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencia de acceso telefónico local.

  - **Anuncio de conferencia**   la aplicación de anuncios de conferencias es una aplicación de comunicaciones unificadas que reproduce tonos y se solicita a los participantes de la RTC en determinadas acciones, como cuando se unen a los participantes o salen de una conferencia. los participantes se silencian o se silencian, alguien entra en la sala de conferencias o la Conferencia está bloqueada o desbloqueada. La aplicación de anuncio de conferencia también es compatible con los comandos multifrecuencia de tono dual (DTMF) del teclado del teléfono. El anuncio de conferencia se instala automáticamente y se activa de forma predeterminada al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencia de acceso telefónico local.

  - **Página configuración de conferencia de acceso telefónico**   local la página Configuración de conferencia de acceso telefónico local muestra los números de acceso telefónico local de la Conferencia con los idiomas disponibles, la información de conferencia asignada (es decir, las reuniones que no es necesario programar) y controles de DTMF en conferencia y admite la administración del número de identificación personal (PIN) e información de conferencia asignada. La página de Configuración de conferencia de acceso telefónico local se instala automáticamente como parte de los servicios web.

  - **Lync Server 2013, servidor de mediación y**   Conferencia de acceso telefónico local de la puerta de enlace RTC requiere un servidor de mediación para traducir la señalización (y los medios, en algunas configuraciones) entre Lync Server 2013 y la puerta de enlace RTC, y una puerta de enlace RTC para traducir señalización y medios entre el servidor de mediación y la puerta de enlace PSTN. Para las conferencias de acceso telefónico local, debe implementar al menos un servidor de mediación y al menos uno de los siguientes elementos:
    
      - Puerta de enlace RTC
    
      - Un sistema IP-PBX
    
      - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta por medio de la configuración de un tronco SIP
    
    <div>
    

    > [!NOTE]  
    > Si también va a implementar la telefonía IP empresarial, el servidor de mediación y las puertas de enlace RTC forman parte de la implementación de telefonía IP empresarial. Si no está implementando la telefonía IP empresarial, debe implementar al menos un servidor de mediación y, como mínimo, una puerta de enlace PSTN, IP-PBX o SBC para las conferencias de acceso telefónico local.

    
    </div>

  - ****   El almacén de archivos del almacén de archivos se usa para archivos de audio de nombres grabados. El almacenamiento de archivos es un componente estándar de toda implementación Enterprise Edition o Standard Edition.

  - **** Almacén de usuario del almacén de usuario se usa para almacenar los pin de 2013 de Lync Server.    Los PIN tienen asignado un algoritmo hash. El almacenamiento de usuarios es un componente estándar de toda implementación Enterprise Edition o Standard Edition.

  - **Panel de control de Lync Server**   es posible configurar la configuración de acceso telefónico mediante el panel de control de Lync Server.

  - **Shell de administración de Lync Server**   toda la configuración de acceso telefónico local se puede establecer mediante los cmdlets del shell de administración de Lync Server. Los cmdlets del shell de administración de Lync Server están disponibles para implementar, configurar, ejecutar, supervisar y solucionar problemas de aplicaciones del operador de conferencias y de la aplicación de anuncios de conferencias. Para obtener más información sobre cmdlets específicos, consulte la documentación del shell de administración de Lync Server.

</div>

<div>

## <a name="supported-topologies"></a>Topologías admitidas

En Lync Server 2013, el servidor que ejecuta servicios de conferencia siempre se encuentra en los servidores front-end o servidores Standard Edition. Durante la implementación inicial, Topology Builder le ofrece la opción de incluir conferencias en su topología. También puede utilizar el generador de topologías para agregar conferencias a una implementación existente. Para obtener más información, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Toplogies de conferencia de acceso telefónico local

Puede implementar conferencias de acceso telefónico local en las siguientes topologías y configuraciones:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Con o sin telefonía IP empresarial

Puede implementar la aplicación servicio de aplicaciones, operador de conferencia y anuncio de conferencia en un sitio central, pero no en un sitio de sucursal.

<div>


> [!NOTE]  
> Si implementa una conferencia de acceso telefónico local, debe implementarla en todos los grupos donde implementará la Conferencia de 2013 de Lync Server. No es necesario asignar números de acceso en cada grupo de servidores, pero tiene que implementar la característica de conferencia de acceso telefónico local en cada grupo de servidores. Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso desde un grupo para unirse a una conferencia de 2013 de Lync Server en un grupo diferente.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Topologías compatibles con Lync Server 2013 y Office Web Apps

Lync Server 2013 proporciona las siguientes formas de configurar el servidor de Office Web Apps. Dependiendo de sus necesidades, puede:

  - **Instale Lync Server 2013 y Office Web Apps Server local detrás del firewall de su organización y en la misma zona de red.** Con esta topología, el acceso externo a Office Web Apps Server se proporcionará a través del servidor proxy inverso. Tanto Lync Server 2013 como Office Web Apps Server (o una granja de Office Web Apps Server) están instalados de forma local y detrás del firewall de la organización. Idealmente, debe instalar Office Web Apps Server en la misma zona de red que Lync Server.
    
    Los clientes externos de Lync pueden conectarse a Lync Server 2013 y a Office Web Apps Server mediante un servidor proxy inverso, que es un servidor que recibe solicitudes de Internet y las reenvía a la red interna. (Los clientes internos no necesitan usar el servidor proxy inverso porque pueden conectarse directamente a Office Web Apps Server). Esta topología funciona mejor si desea usar una granja de servidores de Office Web Apps dedicada que solo se usa en Lync Server 2013.

  - **Usar un servidor de Office Web Apps implementado externamente**
    
    En esta topología, Lync Server 2013 se implementa de forma local y usa un servidor de Office Web Apps que se implementa fuera de la zona de red de Lync Server. Esto puede ocurrir cuando Office Web Apps Server se comparte en varias aplicaciones de la Corporación y se implementa en una red que necesita Lync Server para usar la interfaz externa de Office Web Apps Server y viceversa.
    
    No es necesario instalar un servidor proxy inverso; en su lugar, todas las solicitudes de Office Web Apps Server a Lync Server 2013 se enrutan a través del servidor perimetral. Los clientes de Lync internos y externos se conectan a Office Web Apps Server mediante la dirección URL externa.
    
    Si el servidor de Office Web Apps se implementa fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (es decir, perimetral/Internet)** en el generador de topología. Para obtener más información [, vea configuración de la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Sea cual sea la topología seleccionada, es fundamental que estén abiertos los puertos de firewall correctos. Debe asegurarse de que los firewalls, las direcciones IP y los puertos no estén bloqueados por firewalls en el servidor de Office Web Apps, el equilibrador de carga o el servidor de Lync.

<div>


> [!NOTE]  
> Otra opción para proporcionar acceso externo a Office Web Apps Server es implementar el servidor en la red perimetral. Si decide hacerlo, tenga en cuenta que la configuración de Office Web Apps Server requiere que el equipo servidor sea miembro de su dominio de Active Directory. A menos que su Directiva de red permita que los equipos de la red perimetral sean miembros de dominio de Active Directory, se recomienda que no instale Office Web Apps Server en la red perimetral. En su lugar, debe instalar Office Web Apps Server en la red interna y proporcionar acceso a usuarios externos a través del servidor proxy inverso.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

