---
title: 'Lync Server 2013: servicios de dominio de Active Directory para Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5a4e548f68f68a65ac4ecfb2e4ddc532b5f337c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529717"
---
# <a name="active-directory-domain-services-for-lync-server-2013"></a>Servicios de dominio de Active Directory para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-11-13_

Servicios de dominio de Active Directory funciona como el servicio de directorio para Windows Server 2003, Windows Server 2008, Windows Server 2012 y redes de Windows Server 2012 R2. Los servicios de dominio de Active Directory también sirven como base sobre la que se crea la infraestructura de seguridad de Microsoft Lync Server 2013. La finalidad de esta sección es describir cómo Lync Server 2013 usa los servicios de dominio de Active Directory para crear un entorno confiable para la mensajería instantánea, la conferencia Web, los medios y la voz. Para obtener más información sobre las extensiones de Lync Server a los servicios de dominio de Active Directory y sobre cómo preparar el entorno para los servicios de dominio de Active Directory, consulte preparación de los [servicios de dominio de Active Directory para Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación sobre implementación. Para obtener más información sobre el rol de los servicios de dominio de Active Directory en las redes de Windows Server, consulte la documentación de la versión del sistema operativo que está usando.

Lync Server 2013 usa los servicios de dominio de Active Directory para almacenar:

  - La configuración global que requieren todos los servidores que ejecutan Lync Server 2013 en un bosque.

  - Información de servicio que identifica los roles de todos los servidores que ejecutan Lync Server 2013 en un bosque.

  - Algunas opciones de configuración del usuario.

<div>

## <a name="active-directory-infrastructure"></a>Infraestructura de Active Directory

Entre los requisitos de infraestructura para Active Directory se incluyen los siguientes:

  - Requisitos del sistema operativo para los controladores de dominio

  - Requisitos del nivel funcional de dominio y bosque

  - Requisitos del dominio del catálogo global

Para obtener más información, consulte [Active Directory Infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación sobre implementación.

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a>Preparación de los servicios de dominio de Active Directory

<div>


> [!NOTE]  
> Se recomienda implementar la configuración global en el contenedor de configuración en lugar del contenedor del sistema. Esto no mejora la seguridad, pero puede dar como resultado mejoras de escalabilidad para algunas topologías de servicios de dominio de Active Directory. Si va a migrar desde Microsoft Office Communications Server 2007 y ha usado el contenedor del sistema pero tiene previsto usar el contenedor de configuración, debe mover la configuración del contenedor del sistema antes de realizar los preparativos de actualización. Para migrar la configuración del contenedor del sistema al contenedor de configuración, vea Office Communications Server 2007 global Settings Migration Tool en <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A> .



</div>

Al implementar Lync Server 2013, el primer paso consiste en preparar los servicios de dominio de Active Directory. La preparación de los servicios de dominio de Active Directory para Lync Server 2013 consta de los tres pasos siguientes:

  - **Preparar el esquema**. Esta tarea amplía el esquema de los servicios de dominio de Active Directory para incluir clases y atributos específicos de Lync Server 2013. Para obtener información detallada sobre la preparación del esquema, consulte Running Active Directory Schema Preparation [in Lync Server 2013](lync-server-2013-running-schema-preparation.md) en la documentación sobre implementación. Para obtener más información, vea [migración de Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Preparar el bosque**. Esta tarea crea la configuración global y los objetos en el dominio raíz del bosque, junto con los grupos de servicio universal y administrativo que rigen el acceso a estos objetos y configuraciones. Para obtener información detallada acerca de la preparación del bosque, consulte [Running Forest Preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) en la documentación sobre implementación.

  - **Prepare el dominio**. Esta tarea agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios del dominio. Esta tarea debe completarse en todos los dominios en los que desea implementar servidores que ejecutan Lync Server 2013 y cualquier dominio en el que residen los usuarios de Lync Server. Para obtener información detallada sobre la preparación del dominio, consulte [Running Domain Preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) en la documentación sobre implementación.

Para obtener información general sobre el proceso completo para preparar Active Directory y los derechos y permisos necesarios para realizar cada paso, consulte [Active Directory Infrastructure Requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación sobre implementación.

</div>

<div>

## <a name="universal-groups"></a>Grupos universales

Durante la preparación del bosque, Lync Server 2013 crea varios grupos universales dentro de los servicios de dominio de Active Directory que tienen permiso para obtener acceso a los servicios y la configuración global y administrarlos. Estos grupos universales incluyen:

  - **Grupos administrativos**. Estos grupos definen los roles de administrador fundamentales para una red de Lync Server. Durante la preparación del bosque, estos grupos de administradores se agregan a los grupos de infraestructura de Lync Server.

  - **Grupos de servicio**. Estos grupos son cuentas de servicio necesarias para tener acceso a varios servicios proporcionados por Lync Server.

  - **Grupos de infraestructura**. Estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Lync Server. Funcionan como componentes de los grupos administrativos y no se deben modificar ni agregar usuarios directamente a ellos. Durante la preparación del bosque, los grupos de servicio y administración específicos se agregan a los grupos de infraestructura correspondientes.

Para obtener información detallada sobre los grupos universales específicos que se crearon al preparar AD para Lync Server, así como los grupos de servicio y administración que se agregan a los grupos de infraestructura, vea [los cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación sobre implementación.

<div>


> [!NOTE]  
> Lync Server 2013 admite los grupos universales de Windows Server 2012 para servidores que ejecutan Lync Server 2013, así como sistemas operativos Windows Server 2003 para controladores de dominio. Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque. La compatibilidad con grupos universales, combinada con la delegación de administrador, simplifica la administración de una implementación de Lync Server. Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.



</div>

</div>

<div>

## <a name="role-based-access-control"></a>Control de acceso Role-Based

Además de crear grupos de servicio universal y de administración, y agregar grupos de servicio y administración a los grupos universales apropiados, la preparación del bosque también crea grupos de control de acceso (RBAC) de Role-Based. Para obtener más información sobre los grupos RBAC específicos creados por la preparación del bosque, consulte [Changes by Forest Preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación sobre implementación. Para obtener más información acerca de los grupos RBAC, consulte [role-based access control (RBAC) para Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de control de acceso (ACE) y herencia

La preparación del bosque crea ACE privadas y públicas, y agrega entradas ACE para los grupos universales que crea. Crea ACE privadas específicas en el contenedor de configuración global usado por Lync Server. Este contenedor solo se usa en Lync Server y se encuentra en el contenedor de configuración o en el contenedor del sistema en el dominio raíz, en función de dónde almacene la configuración global.

El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.

Para más información sobre las ACE públicas creadas y agregadas por la preparación del bosque y la preparación del dominio, consulte [Changes by Forest Preparation in Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) y [cambios realizados por la preparación del dominio en Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) en la documentación sobre implementación.

Las organizaciones a menudo bloquean los servicios de dominio de Active Directory (AD DS) para ayudar a mitigar los riesgos de seguridad. Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que necesita Lync Server 2013. Esto puede incluir la eliminación de ACE de contenedores y unidades organizativas, y la deshabilitación de la herencia de permisos en objetos user, Contact, InetOrgPerson o Computer. En un entorno de Active Directory bloqueado, los permisos deben establecerse manualmente en los contenedores y en las unidades organizativas que los requieran. Para obtener más información, consulte [preparación de servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) en la documentación sobre implementación.

</div>

<div>

## <a name="server-information"></a>Información del servidor

Durante la activación, Lync Server 2013 publica la información del servidor en las tres ubicaciones siguientes de los servicios de dominio de Active Directory:

  - Un punto de conexión de servicio (SCP) en cada objeto de equipo de Active Directory correspondiente a un equipo físico en el que Lync Server 2013 está instalado.

  - Objetos de servidor creados en el contenedor de la clase **msRTCSIP-pools** .

  - Servidores de confianza especificados en el generador de topologías.

</div>

<div>

## <a name="service-connection-points"></a>Puntos de conexión de servicio

Cada objeto de Lync Server 2013 en los servicios de dominio de Active Directory tiene un SCP denominado servicios de RTC, que a su vez contiene una serie de atributos que identifican cada equipo y especifican los servicios que proporciona. Entre los atributos de SCP más importantes se encuentran *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*y *serviceBindingInformation*. Las aplicaciones de administración de activos de terceros pueden recuperar información del servidor en una implementación consultando estos y otros atributos de SCP.

</div>

<div>

## <a name="active-directory-server-objects"></a>Objetos de servidor de Active Directory

Cada rol de servidor de Lync Server 2013 tiene un objeto de Active Directory correspondiente cuyos atributos definen los servicios proporcionados por el rol. Además, cuando se activa un servidor Standard Edition o cuando se crea un grupo de servidores Enterprise Edition, Lync Server 2013 crea un nuevo objeto **msRTCSIP-Pool** en el contenedor **msRTCSIP-pools** . La clase **msRTCSIP-Pool** especifica el nombre de dominio completo (FQDN) del grupo, junto con la asociación entre los componentes front-end y back-end del grupo. (Un servidor Standard Edition se considera un grupo lógico cuyos extremos delantero y back se combinan en un solo equipo).

</div>

<div>

## <a name="trusted-servers"></a>Servidores de confianza

En Lync Server 2013, los servidores de confianza son los que se especifican al ejecutar el generador de topologías y publicar la topología. La topología publicada, incluida toda la información del servidor, se almacena en el almacén de administración central. Solo se confía en los servidores definidos en el almacén de administración central. En Lync Server 2013, un servidor de confianza es el único que cumple con los siguientes criterios:

  - El FQDN del servidor se produce en la topología almacenada en el almacén de administración central.

  - El servidor presenta un certificado válido de una entidad de certificación de confianza. Para obtener más información, consulte [requisitos de infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Si falta alguno de estos criterios, el servidor no es de confianza y se rechaza la conexión con él. Este doble requisito evita un posible ataque, si no es probable, en el que un servidor malintencionado intenta asumir el FQDN de un servidor válido.

Además, para habilitar las implementaciones de Microsoft Office Communications Server 2007 R2 y Microsoft Office Communications Server 2007 para comunicarse con los servidores de Lync Server 2013, Lync Server 2013 crea contenedores durante la preparación del bosque para la retención de listas de servidores de confianza para versiones anteriores. En la tabla siguiente se describen los contenedores creados para habilitar la compatibilidad con las implementaciones anteriores.

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a>Listas de servidores de confianza y sus contenedores de Active Directory para la compatibilidad con versiones anteriores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lista de servidores de confianza</th>
<th>Contenedor de Active Directory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidores Standard Edition y servidores front-end del grupo de servidores Enterprise</p></td>
<td><p>Servicio RTC/configuración global</p></td>
</tr>
<tr class="even">
<td><p>Servidores de conferencia</p></td>
<td><p>Servicio RTC/MCU de confianza</p></td>
</tr>
<tr class="odd">
<td><p>Servidores de componentes Web</p></td>
<td><p>Servicio de RTC/confianza</p></td>
</tr>
<tr class="even">
<td><p>Servidores de mediación y servidores de Communicator Web Access, servidor de aplicaciones, registrador con QoE, servicio de conferencia A/V (también servidores SIP de terceros)</p></td>
<td><p>Servicio RTC/servicios de confianza</p></td>
</tr>
<tr class="odd">
<td><p>Servidores proxy</p></td>
<td><p>Lync Server 2013 no admite compatibilidad con versiones anteriores para servidores proxy</p></td>
</tr>
</tbody>
</table>


Para admitir servidores de confianza de versiones anteriores, debe ejecutar la herramienta Best Practices Analyzer. Para obtener más información sobre cómo ejecutar el analizador de procedimientos recomendados, consulte [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

