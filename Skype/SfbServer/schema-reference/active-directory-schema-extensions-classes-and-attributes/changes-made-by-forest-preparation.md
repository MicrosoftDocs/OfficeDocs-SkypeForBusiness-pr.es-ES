---
title: Cambios realizados por la preparación del bosque en Skype para Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: En esta sección se describe la configuración global y objetos y los grupos universales de servicio y administración que se crean mediante el paso de preparación del bosque.
ms.openlocfilehash: 27b8e183f4c76c7c5db71af1422ba9185206632a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213427"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Cambios realizados por la preparación del bosque en Skype para Business Server

En esta sección se describe la configuración global y objetos y los grupos universales de servicio y administración que se crean mediante el paso de preparación del bosque.

## <a name="active-directory-global-settings-and-objects"></a>Configuración Global de active Directory y objetos

Si almacenar la configuración global en el contenedor de configuración (como es el caso de todos los nuevos Skype para las implementaciones de Business Server), la preparación del bosque usa el contenedor Services existente y agrega un objeto **RTC Service** bajo el Configuration\Services objeto. Bajo el objeto RTC Service, la preparación del bosque agrega un objeto de **Configuración Global** de tipo msRTCSIP-GlobalContainer. El objeto global settings contiene toda la configuración que se aplica a la Skype para la implementación de Business Server. Si almacena la configuración global en el contenedor del sistema, la preparación del bosque usa un contenedor de Microsoft bajo el contenedor del sistema de dominio raíz y un objeto RTC Service bajo el objeto System\Microsoft.

La preparación del bosque, también agrega un nuevo objeto **msRTCSIP-Domain** para el dominio raíz en el que se ejecuta el procedimiento.

## <a name="active-directory-universal-service-and-administration-groups"></a>Servicio Universal de Active Directory y los grupos de administración

La preparación del bosque crea grupos universales basados en el dominio que especifique y agrega entradas de control de acceso (ACE) para estos grupos. Este paso crea los grupos universales en los contenedores User del dominio que especifique.

Los grupos universales permiten a los administradores obtener acceso y administrar los servicios y la configuración global. La preparación del bosque agrega los siguientes tipos de grupos universales:

- **Grupos administrativos** Estos grupos definen roles de administrador para una Skype para red Business Server.

- **Grupos de infraestructura** Estos grupos proporcionan permiso para tener acceso a áreas específicas de la Skype para infraestructura de Business Server. Funcionan como componentes de los grupos administrativos. No debe modificar estos grupos o agregar los usuarios directamente a ellos.

- **Grupos de servicio** Estos grupos son cuentas de servicio que requieren acceso a diversos Skype para servicios de Business Server.

En la siguiente tabla se describe los grupos administrativos.

**Grupos administrativos creados durante la preparación del bosque**

|**Grupo administrativo**|**Descripción**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permite a los miembros Administrar servidor y configuración de grupo de servidores, incluidos todos los roles de servidor, la configuración global y los usuarios.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permite a los miembros administrar la configuración de usuario y mover usuarios de un servidor o grupo de servidores a otro.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permite a los miembros leer la configuración de servidor, grupo de servidores y usuario.  <br/> |

En la siguiente tabla se describe los grupos de infraestructura.

**Grupos de infraestructura creados durante la preparación del bosque**

|**Grupo de infraestructura**|**Descripción**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Concede acceso de escritura a los objetos de configuración global de Skype para Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede acceso de sólo lectura para objetos de configuración global de Skype para Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede acceso de solo lectura a Skype para la configuración de usuario de Business Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede acceso de solo lectura a Skype para la configuración de Business Server. Este grupo no tiene acceso a la configuración de nivel de grupo de servidores, sólo a la configuración específica para un servidor individual.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede acceso de solo lectura a Skype para la configuración del servidor de negocio y se colocan en el grupo de administradores locales de las aplicaciones de sucursal con funciones de supervivencia durante la instalación.  <br/> |

En la siguiente tabla se describe los grupos de servicio.

**Grupos de servicio creados durante la preparación del bosque**

|**Grupo de servicio**|**Descripción**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Incluye las cuentas de servicio utilizadas para ejecutar el servidor Front-End y servidores Standard Edition. Este grupo permite acceso de lectura y escritura de los servidores a Skype para la configuración global Business Server y objetos de usuario de Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Incluye las cuentas de servicio utilizadas para ejecutar / servidores de conferencia A/v, servicios Web, servidor de mediación, el servidor de archivado y el servidor de supervisión.  <br/> |
|RTCProxyUniversalServices  <br/> |Incluye las cuentas de servicio utilizadas para ejecutar Skype para los servidores perimetrales de servidor empresarial.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Incluye servidores que pueden participar en Skype para la replicación del almacén de Administración Central de servidor empresarial.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede acceso de solo lectura a Skype para la configuración del servidor de negocio, pero permite la configuración para la instalación de un servidor de sucursal con funciones de supervivencia y la implementación de dispositivo de sucursal con funciones de supervivencia.  <br/> |

La preparación del bosque, a continuación, agrega los grupos de servicio y administración a los grupos de infraestructura correspondientes, como se indica a continuación:

- RTCUniversalServerAdmins se agrega a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins se agrega como un miembro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices y RTCUniversalReadOnlyAdmins se agregan como miembros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

La preparación del bosque también crea los siguientes grupos de acceso basado en roles (RBAC) del control:

- CSAdministrator

- CSArchivingAdministrator

- CSHelpDesk

- CSLocationAdministrator

- CSResponseGroupAdministrator

- CSServerAdministrator

- CSUserAdministrator

- CSViewOnlyAdministrator

- CSVoiceAdministrator

- CsPersistentChatAdministator

- AdministradorGrupoRespuestaCs

Para obtener información detallada sobre roles RBAC y las tareas permitidas para cada uno de ellos, consulte [Role-Based Access Control](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) en la documentación de planeación.

La preparación del bosque crea entradas ACE privadas y públicas. Crea entradas ACE privadas en el contenedor de configuración global utilizado por Skype para Business Server. Este contenedor se utiliza sólo por Skype para Business Server y se encuentra en el contenedor de configuración o en el contenedor del sistema en el dominio raíz, dependiendo de dónde almacenar la configuración global. En la siguiente tabla, se enumeran las ACE públicas creadas por la preparación del bosque.

**Entradas ACE públicas creadas por la preparación del bosque**


| **as**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Dominio de raíz de lectura del contenedor del sistema (no heredado)**\\**\* <br/>        | X  <br/>                            |
| Contenedor DisplaySpecifiers de Read Configuration (no heredado)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* Las entradas ACE que no se heredan no conceden acceso a objetos secundarios de estos contenedores. Las ACE que se heredan conceden permisos a objetos secundarios de estos contenedores.

En el contenedor Configuration, bajo el contexto de nomenclatura de configuración, la preparación del bosque realiza las tareas siguientes:

- Agrega una entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para la página de **propiedades RTC** en la adminContextMenu y adminPropertyPages atributos del idioma especificador de presentación a los usuarios, contactos, Contact e InetOrgPerson (por ejemplo, CN = user-Display, CN = 409, CN = DisplaySpecifiers).

- Agrega un objeto **RTCPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases User y Contact.

- Agrega un objeto **RTCUserSearchPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases de usuario, Contact, OU y DomainDNS.

- Agrega **msRTCSIP-PrimaryUserAddress** bajo el atributo **extraColumns** de cada especificador de presentación de unidad organizativa (OU) de idioma (por ejemplo, CN = organizationalUnit-Display, CN = 409, CN = DisplaySpecifiers) y copia los valores de la atributo **extraColumns** de la presentación predeterminada (por ejemplo, CN = default-Display, CN = 409, CN = DisplaySpecifiers).

- Agrega **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**y **msRTCSIP-UserEnabled** filtrado atributos bajo el atributo **attributeDisplayNames** de cada idioma mostrar especificador para los usuarios, contactos, y los objetos InetOrgPerson (por ejemplo, en inglés: CN = user-Display, CN = 409, CN = DisplaySpecifiers).


