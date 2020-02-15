---
title: Componentes y topologías de Lync Server 2013 para conferencias
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d14c12ad1e28dc2a40fed5b19b5928a5bedc069
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Componentes y topologías para conferencias en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-04_

Al seleccionar Conferencia en el generador de topologías, las conferencias se implementan como parte del servidor front-end o del servidor Standard Edition. Las conferencias de acceso telefónico y el uso compartido de PowerPoint requieren componentes y configuraciones adicionales. En las secciones siguientes se describen los componentes y las topologías admitidos para las conferencias web, las conferencias A/V y las conferencias de acceso telefónico.

<div>

## <a name="supported-components"></a>Componentes admitidos

Los únicos componentes de conferencia web y conferencia A/V requieren son los servidores front-end de la organización o los servidores Standard Edition. Para obtener una lista de requisitos de hardware y software para los servidores front-end y los servidores Standard Edition, consulte [hardware admitido para Lync server 2013](lync-server-2013-supported-hardware.md) y [compatibilidad con la infraestructura y el software de servidor en Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).

Lync Server 2013 usa Office Web Apps y Office Web Apps Server para controlar el uso compartido y la representación de presentaciones de PowerPoint. Para más información sobre la instalación y la configuración del servidor de Office Web Apps, vea [Configuring Integration with Office Web Apps Server and Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Además de los requisitos de conferencia web y conferencia A/V, las conferencias de acceso telefónico local usan los siguientes componentes de Lync Server 2013:

  - ****   El servicio de aplicación de servicio de aplicación proporciona una plataforma para implementar, hospedar y administrar aplicaciones de comunicaciones unificadas (UC). Las conferencias de acceso telefónico local usan dos aplicaciones de comunicaciones unificadas que requieren el servicio de aplicación: operador de conferencia y anuncio de conferencia. El servicio de aplicación se instala y se activa de forma predeterminada en todos los servidores front-end de un grupo de servidores front-end, y en todos los servidores Standard Edition, al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencias de acceso telefónico local.

  - ****   La aplicación de operador de conferencia de aplicaciones operador de conferencia es una aplicación de comunicaciones unificadas que acepta llamadas de red telefónica conmutada (RTC), reproduce preguntas y une las llamadas a una conferencia a/V. La aplicación operador de conferencia se instala y activa de forma predeterminada al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencia de acceso telefónico local.

  - **Anuncio de conferencia**   la aplicación de anuncio de conferencia de aplicaciones es una aplicación de comunicaciones unificadas que reproduce tonos y mensajes a los participantes de la RTC en determinadas acciones, como cuando un participante se une a una conferencia o la abandona, los participantes se silencian o se desactivan, por ejemplo, alguien entra en la sala de espera o la Conferencia está bloqueada o desbloqueada. La aplicación de anuncio de conferencia también admite comandos de tono de marcado de frecuencia múltiple (DTMF) del teclado del teléfono. La aplicación de anuncio de conferencia se instala y activa automáticamente de forma predeterminada al implementar una carga de trabajo de conferencia y seleccionar la opción de conferencia de acceso telefónico local.

  - **Página configuración de conferencia de acceso telefónico**   local la página Configuración de conferencia de acceso telefónico local muestra los números de acceso telefónico de la Conferencia con los idiomas disponibles, asignada información de conferencia (es decir, para las reuniones que no necesitan programarse) y controles DTMF en la Conferencia, y admite la administración del número de identificación personal (PIN) y la información de conferencia asignada. La página de configuración de la Conferencia de acceso telefónico local se instala automáticamente como parte de los servicios Web.

  - **Lync Server 2013, Mediation Server y**   la Conferencia RTC para conferencias de acceso telefónico local requieren un servidor de mediación para convertir la señalización (y los medios, en algunas configuraciones) entre Lync Server 2013 y la puerta de enlace RTC, y una puerta de enlace RTC para convertir la señalización y los medios entre el servidor de mediación y la puerta de enlace RTC. Para las conferencias de acceso telefónico local, debe implementar al menos un servidor de mediación y, al menos, uno de los siguientes elementos:
    
      - Una puerta de enlace RTC
    
      - IP-PBX
    
      - Un controlador de borde de sesión (SBC) para un proveedor de servicios de telefonía por Internet al que se conecta mediante la configuración de un tronco SIP
    
    <div>
    

    > [!NOTE]  
    > Si también está implementando la telefonía IP empresarial, el servidor de mediación y las puertas de enlace RTC forman parte de la implementación de telefonía IP empresarial. Si no está implementando Enterprise Voice, debe implementar al menos un servidor de mediación y al menos una puerta de enlace RTC, IP-PBX o SBC para las conferencias de acceso telefónico local.

    
    </div>

  - ****   Almacén de archivos del almacén de archivos se usa para los archivos de audio de nombre grabado. El almacenamiento de archivos es un componente estándar de toda implementación Enterprise Edition o Standard Edition.

  - **Almacén de usuario el**almacén de usuario se usa para almacenar los PIN del usuario Lync Server 2013.    Los PIN tienen asignado un algoritmo hash. El almacenamiento de usuarios es un componente estándar de toda implementación Enterprise Edition o Standard Edition.

  - **Panel de control de Lync Server**   algunas opciones de configuración de acceso telefónico se pueden configurar mediante el panel de control de Lync Server.

  - **Shell de administración de Lync Server**   todas las opciones de acceso telefónico local se pueden configurar con los cmdlets del shell de administración de Lync Server. Los cmdlets del shell de administración de Lync Server están disponibles para implementar, configurar, ejecutar, supervisar y solucionar problemas de aplicación del operador de conferencia y de la aplicación de anuncio de conferencia. Para obtener más información acerca de los cmdlets específicos, consulte Lync Server Management Shell Documentation.

</div>

<div>

## <a name="supported-topologies"></a>Topologías admitidas

En Lync Server 2013, el servidor que ejecuta los servicios de conferencia siempre se combina con los servidores front-end o los servidores Standard Edition. Durante la implementación inicial, el generador de topologías le ofrece la opción de incluir conferencias en la topología. También puede utilizar el Generador de topologías para agregar conferencia a una implementación existente. Para obtener más información, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

<div>

## <a name="dial-in-conferencing-toplogies"></a>Topologías de conferencias de acceso telefónico local

Puede implementar la característica de conferencia de acceso telefónico local en las configuraciones y topologías siguientes:

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 Enterprise Edition

  - Con o sin telefonía IP empresarial

Puede implementar aplicaciones de servicio de aplicación, operador de conferencia y anuncio de conferencia en un sitio central, pero no en un sitio de sucursal.

<div>


> [!NOTE]  
> Si implementa la Conferencia de acceso telefónico local, debe implementarla en todos los grupos de servidores en los que implemente Lync Server 2013 conferencias. No es necesario asignar números de acceso en cada grupo de servidores, pero debe implementar la característica de conferencia de acceso telefónico local en cada grupo de servidores. Este requisito admite la característica de nombre grabado cuando un usuario llama a un número de acceso de un grupo de servidores para unirse a una conferencia de 2013 de Lync Server en un grupo de servidores diferente.



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Topologías admitidas para Lync Server 2013 y Office Web Apps

Lync Server 2013 proporciona las siguientes formas de configurar Office Web Apps Server. Dependiendo de sus necesidades, puede:

  - **Instale Lync Server 2013 y Office Web Apps Server local detrás del firewall de su organización y en la misma zona de red.** Con esta topología, el acceso externo a Office Web Apps Server se proporcionará a través del servidor proxy inverso. Tanto Lync Server 2013 como Office Web Apps Server (o una granja de servidores de Office Web Apps Server) están instalados de forma local y detrás del firewall de la organización. Lo ideal sería instalar Office Web Apps Server en la misma zona de red que Lync Server.
    
    Los clientes externos de Lync pueden conectarse a Lync Server 2013 y a Office Web Apps Server mediante un servidor de proxy inverso, que es un servidor que recibe solicitudes de Internet y las reenvía a la red interna. (Los clientes internos no necesitan usar el servidor de proxy inverso porque se pueden conectar directamente a Office Web Apps Server). Esta topología funciona mejor si desea usar una granja de Office Web Apps Server dedicada que solo se usa en Lync Server 2013.

  - **Uso de Office Web Apps Server implementado externamente**
    
    En esta topología, Lync Server 2013 se implementa localmente y usa un servidor de Office Web Apps que se implementa fuera de la zona de red de Lync Server. Esto puede ocurrir cuando Office Web Apps Server se comparte entre varias aplicaciones de la Corporación y se implementa en una red que requiere Lync Server para usar la interfaz externa de Office Web Apps Server y viceversa.
    
    No es necesario instalar un servidor proxy inverso; en su lugar, todas las solicitudes del servidor de Office Web Apps a Lync Server 2013 se enrutan a través del servidor perimetral. Tanto el cliente de Lync interno como el externo se conectan a Office Web Apps Server mediante la dirección URL externa.
    
    Si Office Web Apps Server está implementado fuera del firewall interno, seleccione la opción el **servidor de Office Web Apps se implementa en una red externa (es decir, perimetral/Internet)** en el generador de topologías. Para obtener más información [, consulte Configuración de la integración con Office Web Apps Server y Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Sea cual sea la topología seleccionada, es fundamental que estén abiertos los puertos de firewall correctos. Debe asegurarse de que los firewalls, los nombres DNS, las direcciones IP y los puertos no estén bloqueados por los firewalls de Office Web Apps Server, el equilibrador de carga o Lync Server.

<div>


> [!NOTE]  
> Otra opción para ofrecer acceso externo a Office Web Apps Server es implementar el servidor en la red perimetral. Si decide hacerlo, tenga en cuenta que el programa de instalación de Office Web Apps Server requiere que el equipo servidor pertenezca a su dominio de Active Directory. A menos que la Directiva de red permita que los equipos de la red perimetral sean miembros de dominio de Active Directory, se recomienda no instalar Office Web Apps Server en la red perimetral. En su lugar, debe instalar Office Web Apps Server en la red interna y proporcionar a los usuarios externos el acceso a través del servidor proxy inverso.



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

