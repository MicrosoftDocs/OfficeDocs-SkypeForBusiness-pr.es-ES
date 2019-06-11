---
title: 'Lync Server 2013: servicios de dominio de Active Directory para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a>Servicios de dominio de Active Directory para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-13_

Los servicios de dominio de Active Directory funcionan como el servicio de directorio para Windows Server 2003, Windows Server 2008, Windows Server 2012 y redes Windows Server 2012 R2. Los servicios de dominio de Active Directory también sirven como la base en la que se creó la infraestructura de seguridad 2013 de Microsoft Lync Server. El propósito de esta sección es describir cómo Lync Server 2013 usa los servicios de dominio de Active Directory para crear un entorno digno de confianza para mensajería instantánea, conferencias web, multimedia y voz. Para obtener más información sobre las extensiones de Lync Server a los servicios de dominio de Active Directory y sobre cómo preparar el entorno para los servicios de dominio de Active Directory, vea [preparar los servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la implementación. documentación. Para obtener más información sobre el rol de los servicios de dominio de Active Directory en las redes de Windows Server, consulte la documentación de la versión del sistema operativo que está usando.

Lync Server 2013 usa los servicios de dominio de Active Directory para almacenar:

  - Configuración global que necesitan todos los servidores que ejecutan Lync Server 2013 en un bosque.

  - Información de servicio que identifica los roles de todos los servidores que ejecutan Lync Server 2013 en un bosque.

  - Algunas configuraciones de usuario.

<div>

## <a name="active-directory-infrastructure"></a>Infraestructura de Active Directory

Entre los requisitos de infraestructura para Active Directory se incluyen los siguientes:

  - Requisitos del sistema operativo para los controladores de dominio

  - Requisitos del nivel funcional de dominio y bosque

  - Requisitos del dominio del catálogo global

Para obtener más información, vea requisitos de la [infraestructura de Active Directory para Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación de implementación.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Preparación de los servicios de dominio de Active Directory

<div>


> [!NOTE]  
> Se recomienda implementar la configuración global en el contenedor de configuración en lugar del contenedor del sistema. Esto no mejora la seguridad, pero puede dar lugar a mejoras de escalabilidad para algunas topologías de los servicios de dominio de Active Directory. Si va a migrar desde Microsoft Office Communications Server 2007 y ha usado el contenedor del sistema pero tiene previsto usar el contenedor de configuración, debe mover la configuración en el contenedor del sistema antes de realizar la preparación de la actualización. Para migrar la configuración del contenedor del sistema al contenedor configuración, consulte la herramienta de migración configuración global de Office <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>Communications Server 2007 en.



</div>

Al implementar Lync Server 2013, el primer paso es preparar los servicios de dominio de Active Directory. La preparación de los servicios de dominio de Active Directory para Lync Server 2013 consta de los tres pasos siguientes:

  - **Preparar esquema**. Esta tarea extiende el esquema de los servicios de dominio de Active Directory para incluir clases y atributos específicos de Lync Server 2013. Para obtener detalles sobre la preparación del esquema, consulte ejecución de la [preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-running-schema-preparation.md) en la documentación de implementación. Para obtener más información, vea [migración de Office Communications server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Preparar el bosque**. Esta tarea crea la configuración global y los objetos en el dominio raíz del bosque, junto con el servicio universal y los grupos administrativos que rigen el acceso a estos valores y objetos. Para obtener detalles sobre la preparación del bosque, consulte ejecución de la [preparación del bosque para Lync Server 2013](lync-server-2013-running-forest-preparation.md) en la documentación de implementación.

  - **Preparar el dominio**. Esta tarea agrega las entradas de control de acceso (ACE) necesarias a grupos universales que conceden permisos para hospedar y administrar los usuarios del dominio. Esta tarea debe completarse en todos los dominios en los que desee implementar servidores que ejecuten Lync Server 2013 y cualquier dominio en el que se encuentren los usuarios de Lync Server. Para obtener más información sobre la preparación del dominio, vea [ejecución de la preparación del dominio de Lync Server 2013](lync-server-2013-running-domain-preparation.md) en la documentación de implementación.

Para obtener información general sobre el proceso completo de preparación de Active Directory y los derechos y permisos necesarios para realizar cada paso, vea [requisitos de la infraestructura de Active Directory para Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación de implementación.

</div>

<div>

## <a name="universal-groups"></a>Grupos universales

Durante la preparación del bosque, Lync Server 2013 crea varios grupos universales dentro de los servicios de dominio de Active Directory que tienen permiso para acceder y administrar la configuración global y los servicios. Entre estos grupos universales se incluyen:

  - **Grupos administrativos**. Estos grupos definen los roles de administrador fundamentales para una red de Lync Server. Durante la preparación del bosque, estos grupos de administradores se agregan a los grupos de infraestructura de Lync Server.

  - **Grupos de servicio**. Estos grupos son cuentas de servicio necesarias para obtener acceso a los distintos servicios proporcionados por Lync Server.

  - **Grupos de infraestructura**. Estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Lync Server. Funcionan como componentes de los grupos administrativos y no deben modificarse ni se deben agregar directamente usuarios a esos grupos. Durante la preparación del bosque, se añaden grupos de servicio y administración específicos a los grupos de infraestructura correspondientes.

Para obtener información sobre los grupos universales específicos que se han creado al preparar AD para Lync Server, así como los grupos de servicio y administración que se agregan a los grupos de infraestructura, consulte [cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en el Documentación de implementación.

<div>


> [!NOTE]  
> Lync Server 2013 admite los grupos universales de Windows Server 2012 para servidores que ejecutan Lync Server 2013, así como sistemas operativos Windows Server 2003 para controladores de dominio. Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque, y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque. La compatibilidad con los grupos universales, junto con la delegación de administrador, simplifica la administración de una implementación de Lync Server. Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Control de acceso basado en roles

Además de crear grupos universales de servicio y administración y añadir grupos de servicio y administración a los grupos universales correspondientes, la preparación del bosque también crea grupos de control de acceso basado en roles (RBAC). Para obtener detalles sobre los grupos RBAC específicos creados por la preparación del bosque, consulte [cambios hechos por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación de implementación. Para obtener más información sobre los grupos RBAC, consulte [control de acceso basado en roles (RBAC) para Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de control de acceso (ACE) y herencia

La preparación del bosque crea ACE privadas y públicas, y añade ACE en los grupos universales que crea. Crea ACE privadas específicas en el contenedor de configuración global usado por Lync Server. Este contenedor solo es utilizado por Lync Server y se encuentra en el contenedor configuración o en el contenedor del sistema en el dominio raíz, según dónde se almacene la configuración global.

El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.

Para obtener detalles sobre las ACE públicas creadas y agregadas por la preparación del bosque y la preparación del dominio, consulte [los cambios realizados por la preparación del bosque en Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) y [los cambios realizados por la preparación del dominio en Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) en la implementación documentación.

Las organizaciones suelen bloquear los servicios de dominio de Active Directory (AD DS) para ayudar a mitigar los riesgos de seguridad. Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que necesita Lync Server 2013. Puede incluir la eliminación de ACE de contenedores y unidades organizativas y la deshabilitación de la herencia de permisos en los objetos User, Contact, InetOrgPerson o Computer. En un entorno de Active Directory bloqueado, los permisos deben establecerse manualmente en contenedores y unidades organizativas que los requieran. Para obtener más información, vea [preparar servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) en la documentación de implementación.

</div>

<div>

## <a name="server-information"></a>Información sobre el servidor

Durante la activación, Lync Server 2013 publica la información del servidor en las tres siguientes ubicaciones de los servicios de dominio de Active Directory:

  - Un punto de conexión de servicio (SCP) en cada objeto de equipo de Active Directory correspondiente a un equipo físico en el que está instalado Lync Server 2013.

  - Objetos de servidor creados en el contenedor de la clase **msRTCSIP-Pools**.

  - Servidores de confianza especificados en el generador de topología.

</div>

<div>

## <a name="service-connection-points"></a>Puntos de conexión de servicio

Cada objeto de Lync Server 2013 de los servicios de dominio de Active Directory tiene un SCP denominado servicios de RTC, que a su vez contiene una serie de atributos que identifican cada equipo y especifican los servicios que proporciona. Algunos de los atributos más importantes de SCP son *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* y *serviceBindingInformation*. Las aplicaciones de administración de activos de otro fabricante pueden recuperar la información de servidor de una implementación consultando estos y otros atributos de los SCP.

</div>

<div>

## <a name="active-directory-server-objects"></a>Objetos de servidor de Active Directory

Cada rol de servidor de Lync Server 2013 tiene un objeto de Active Directory correspondiente cuyos atributos definen los servicios proporcionados por ese rol. Además, cuando se activa un servidor Standard Edition o cuando se crea un grupo de servidores Enterprise Edition, Lync Server 2013 crea un nuevo objeto **msRTCSIP-Pool** en el contenedor de **msRTCSIP-pools** . La clase **msRTCSIP-Pool** especifica el nombre de dominio completo (FQDN) del grupo, junto con la asociación entre los componentes front-end y back-end del grupo de servidores. (Un servidor Standard Edition se considera un grupo lógico cuyos extremos frontal y posterior se colocan en un solo equipo).

</div>

<div>

## <a name="trusted-servers"></a>Servidores de confianza

En Lync Server 2013, los servidores de confianza son los que se especifican al ejecutar Topology Builder y publicar su topología. La topología publicada, incluida toda la información del servidor, se almacena en el almacén de administración central. Solo los servidores definidos en el almacén de administración central son de confianza. En Lync Server 2013, un servidor de confianza es aquel que cumple los siguientes criterios:

  - El FQDN del servidor se produce en la topología almacenada en el almacén de administración central.

  - El servidor presenta un certificado válido de una CA de confianza. Para obtener más información, consulte [requisitos de infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Si no se cumple alguno de estos criterios, el servidor no se considera de confianza y se rechaza la conexión con dicho servidor. Estos dos requisitos impiden que se produzca un posible ataque, aunque poco probable, en el que un servidor no autorizado intenta adoptar el FQDN de un servidor válido.

Además, para permitir que las implementaciones de Microsoft Office Communications Server 2007 R2 y Microsoft Office Communications Server 2007 se comuniquen con los servidores de Lync Server 2013, Lync Server 2013 crea contenedores durante la preparación del bosque para almacenar listas de servidores de confianza para versiones anteriores. La siguiente tabla describe los contenedores creados para habilitar la compatibilidad con implementaciones anteriores.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Listas de servidores de confianza y sus contenedores de Active Directory para la compatibilidad con versiones anteriores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Listas de servidores de confianza</th>
<th>Contenedor de Active Directory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidores de Standard Edition y servidores front-end del grupo Enterprise Edition</p></td>
<td><p>Servicio RTC/Configuración global</p></td>
</tr>
<tr class="even">
<td><p>Servidores de conferencia</p></td>
<td><p>Servicio RTC/MCU de confianza</p></td>
</tr>
<tr class="odd">
<td><p>Servidores de componentes web</p></td>
<td><p>Servicio RTC/Servidores de componentes web de confianza</p></td>
</tr>
<tr class="even">
<td><p>Servidores de mediación y servidores de Communicator Web Access, Servidor de aplicaciones, Registrador con QoE, Servicio de conferencia A/V (también servidores SIP de otros fabricantes)</p></td>
<td><p>Servicio RTC/Servicios de confianza</p></td>
</tr>
<tr class="odd">
<td><p>Servidores proxy</p></td>
<td><p>Lync Server 2013 no admite compatibilidad con versiones anteriores para servidores proxy</p></td>
</tr>
</tbody>
</table>


Para admitir servidores de confianza de versiones anteriores, debe ejecutar la herramienta Best Practices Analyzer. Para obtener más información sobre cómo ejecutar el analizador de [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633)procedimientos recomendados, consulte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

