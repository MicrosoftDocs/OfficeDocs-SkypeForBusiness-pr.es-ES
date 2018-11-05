---
title: Servicios de dominio de Active Directory para Lync Server 2013
TOCTitle: Servicios de dominio de Active Directory para Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59679368
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Servicios de dominio de Active Directory para Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Servicios de dominio de Active Directory funciona como servicio de directorio para las redes de Windows Server 2003, Windows Server 2008, Windows Server 2012 y Windows Server 2012 R2. Servicios de dominio de Active Directory también constituyen la base sobre la que se ha creado la infraestructura de seguridad de Microsoft Lync Server 2013. El objetivo de esta sección es describir cómo Lync Server 2013 utiliza Servicios de dominio de Active Directory para crear un entorno de confianza para las características de MI, conferencia web, medios y voz. Para más información sobre las extensiones de Lync Server a Servicios de dominio de Active Directory y sobre cómo preparar un entorno para Servicios de dominio de Active Directory, vea [Preparar Servicios de dominio de Active Directory en Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) en la documentación sobre implementación. Para más información sobre el rol de Servicios de dominio de Active Directory en redes de Windows Server, consulte la documentación de la versión del sistema operativo que está usando.

Lync Server 2013 utiliza Servicios de dominio de Active Directory para almacenar:

  - La configuración global que requieren todos los servidores que ejecutan Lync Server 2013 en un bosque.

  - La información de servicio que identifica los roles de todos los servidores que ejecutan Lync Server 2013 en un bosque.

  - Algunas configuraciones de usuario.

## Active Directory Infraestructura

Entre los requisitos de la infraestructura de Active Directory se incluyen los siguientes:

  - Requisitos del sistema operativo para los controladores de dominio

  - Requisitos del nivel funcional de dominio y bosque

  - Requisitos del dominio del catálogo global

Para más información, consulte [Requisitos de infraestructura de Active Directory para Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación sobre implementación.

## Servicios de dominio de Active Directory Preparación


> [!NOTE]
> Le recomendamos que implemente la configuración global en el contenedor de configuración en lugar del contenedor del sistema. Así no mejorará la seguridad, pero obtendrá una mejor escalabilidad para algunas topologías de Servicios de dominio de Active Directory. Si va a migrar desde Microsoft Office Communications Server 2007 y ha usado el contenedor del sistema pero desea usar el contenedor de configuración, DEBE mover la configuración del contenedor del sistema ANTES de preparar la actualización. Para migrar la configuración del contenedor del sistema al contenedor de configuración, consulte Office Communications Server 2007 Herramienta de migración de la configuración global en <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.



Al implementar Lync Server 2013, el primer paso a seguir es preparar Servicios de dominio de Active Directory. La preparación de Servicios de dominio de Active Directory para Lync Server 2013 consiste en los tres pasos que siguen:

  - **Preparar esquema**. Esta tarea extiende el esquema de Servicios de dominio de Active Directory para que incluya las clases y los atributos específicos de Lync Server 2013. Para más información sobre cómo preparar el esquema, consulte [Ejecutar la preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-running-schema-preparation.md) en la documentación sobre implementación. Para obtener más información, vea [Migrar de Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).

  - **Preparar el bosque**. Esta tarea crea la configuración global y objetos en el dominio raíz del bosque, junto con los grupos universales de servicio y administración que controlan el acceso a dicha configuración y dichos objetos. Para más información sobre cómo preparar el bosque, consulte [Ejecutar la preparación del bosque para Lync Server 2013](lync-server-2013-running-forest-preparation.md) en la documentación sobre implementación.

  - **Preparar el dominio**. Esta tarea agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar a los usuarios del dominio. Esta tarea debe completarse en todos los dominios en los que desee implementar servidores que ejecuten Lync Server 2013 y en los dominios en los que residan sus usuarios de Lync Server. Para más información sobre cómo preparar el dominio, consulte [Ejecutar la preparación del dominio para Lync Server 2013](lync-server-2013-running-domain-preparation.md) en la documentación sobre implementación.

Para obtener una descripción general del proceso completo para preparar Active Directory y los derechos y permisos necesarios para realizar cada paso, consulte [Requisitos de infraestructura de Active Directory para Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) en la documentación sobre implementación.

## Grupos universales

Durante la preparación del bosque, Lync Server 2013 crea varios grupos universales dentro de Servicios de dominio de Active Directory con permiso para obtener acceso y administrar servicios y la configuraciones globales. Entre estos grupos universales se incluyen:

  - **Grupos administrativos**. Estos grupos definen los roles de administrador fundamentales de una red de Lync Server. Durante la preparación del bosque, estos grupos de administradores se añaden a grupos de infraestructura de Lync Server.

  - **Grupos de servicio**. Estos grupos son cuentas de servicio necesarias para acceder a varios servicios que presta Lync Server.

  - **Grupos de infraestructura**. Estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Lync Server. Funcionan como componentes de grupos administrativos. No debe modificar estos grupos ni agregar usuarios directamente. Durante la preparación del bosque, se agregan grupos de servicio y administración específicos a los grupos de infraestructura correspondientes.

Para más información sobre los grupos universales específicos creados durante la preparación de AD para Lync Server, así como sobre los grupos de servicio y administración que se agregaron a los grupos de infraestructura, consulte [Cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación sobre implementación.


> [!NOTE]
> Lync Server 2013 admite los grupos universales de Windows Server 2012 para servidores que ejecutan Lync Server 2013, así como los sistemas operativos Windows Server 2003 para los controladores de dominios. Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque, y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque. La compatibilidad de grupo universal, combinada con la delegación de administrador, simplifica la administración de una implementación de Lync Server. Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos.



## Control de acceso basado en roles

Además de crear grupos universales de servicio y administración y añadir grupos de servicio y administración a los grupos universales correspondientes, la preparación del bosque también crea grupos de control de acceso basado en roles (RBAC). Para más información sobre los grupos RBAC específicos creados por la preparación del bosque, consulte [Cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) en la documentación sobre implementación. Para más información sobre los grupos RBAC, consulte [Control de acceso basado en roles (RBAC) para Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).

## Entradas de control de acceso (ACE) y herencia

La preparación del bosque crea ACE privadas y públicas, y agrega ACE en los grupos universales que crea. Crea ACE privadas específicas en el contenedor de la configuración global que usa Lync Server. A este contenedor solo lo utiliza Lync Server y está ubicado en el contenedor de la configuración o en el contenedor del sistema en el dominio raíz, en función de dónde almacene la configuración global.

El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.

Para más información sobre las ACE públicas creadas y agregadas durante la preparación del bosque y la preparación del dominio, consulte [Cambios realizados por la preparación del bosque en Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) y [Cambios realizados por la preparación del dominio en Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) en la documentación sobre implementación.

Las organizaciones bloquean a menudo Servicios de dominio de Active Directory (AD DS) para ayudar a mitigar los riesgos para la seguridad. Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que Lync Server 2013 requiere. Puede incluir la eliminación de ACE de contenedores y unidades organizativas y la deshabilitación de la herencia de permisos en los objetos User, Contact, InetOrgPerson o Computer. En un entorno de Active Directory bloqueado, los permisos deben establecerse manualmente en los contenedores y en las unidades organizativas que los requieren. Para más información, consulte [Preparar Servicios de dominio de Active Directory bloqueados en Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) en la documentación sobre implementación.

## Información sobre el servidor

Durante la activación, Lync Server 2013 publica información de servidor en las tres ubicaciones siguientes de Servicios de dominio de Active Directory:

  - Un punto de conexión de servicio (SCP) en cada objeto de equipo de Active Directory que corresponde a un equipo físico en el que está instalado Lync Server 2013.

  - Objetos de servidor creados en el contenedor de la clase **msRTCSIP-Pools**.

  - Servidores de confianza especificados en Generador de topologías.

## Puntos de conexión de servicio

Cada objeto de Lync Server 2013 en Servicios de dominio de Active Directory tiene un SCP denominado Servicios RTC, que a su vez contiene varios atributos que identifican a cada equipo y especifican los servicios que proporciona. Algunos de los atributos más importantes de SCP son *serviceDNSName*, *serviceDNSNameType*, *serviceClassname* y *serviceBindingInformation*. Las aplicaciones de administración de activos de otro fabricante pueden recuperar la información de servidor de una implementación consultando estos y otros atributos de los SCP.

## Active Directory Objetos de servidor

Cada rol del servidor Lync Server 2013 tiene un objeto de Active Directory correspondiente cuyos atributos definen los servicios proporcionados por dicho rol. Asimismo, cuando se activa un servidor Servidor Standard Edition, o cuando se crea un grupo de servidores Enterprise Edition, Lync Server 2013 crea un nuevo objeto **msRTCSIP-Pool** en el contenedor **msRTCSIP-Pools**. La clase **msRTCSIP-Pool** especifica el nombre de dominio completo (FQDN) del grupo, junto con la asociación entre los componentes front-end y back-end del grupo de servidores. (Un servidor Servidor Standard Edition es un grupo de servidores lógico cuyos front-end y back-end se combinan en un único equipo.)

## Servidores de confianza

En Lync Server 2013, los servidores de confianza son aquellos que se especifican al ejecutar Generador de topologías y al publicar su topología. La topología publicada, incluida toda la información del servidor, se almacena en el almacén de administración central. Solo los servidores definidos en el almacén de administración central son de confianza. En Lync Server 2013, un servidor de confianza es el que cumple los siguientes criterios:

  - El FQDN del servidor se produce en la topología almacenada en el almacén de administración central.

  - El servidor presenta un certificado válido de una CA de confianza. Para obtener información detallada, consulte [Requisitos de la infraestructura de certificados para Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).

Si no se cumple alguno de estos criterios, el servidor no se considera de confianza y se rechaza la conexión con dicho servidor. Estos dos requisitos impiden que se produzca un posible ataque, aunque poco probable, en el que un servidor no autorizado intenta adoptar el FQDN de un servidor válido.

Además, para habilitar las implementaciones de Microsoft Office Communications Server 2007 R2 y Microsoft Office Communications Server 2007 para comunicarse con los servidores de Lync Server 2013, Lync Server 2013 crea contenedores durante la preparación del bosque para las listas de servidores de confianza de versiones anteriores. La siguiente tabla describe los contenedores creados para habilitar la compatibilidad con implementaciones anteriores.

### Listas de servidores de confianza y sus contenedores de Active Directory para la compatibilidad con versiones anteriores

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
<td><p>Lync Server 2013 no admite la compatibilidad con versiones anteriores en servidores proxy</p></td>
</tr>
</tbody>
</table>


Para admitir servidores de confianza de versiones anteriores, debe ejecutar la herramienta de compatibilidad con versiones anteriores. Para más información sobre cómo ejecutar el analizador de procedimientos recomendados, consulte [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).

