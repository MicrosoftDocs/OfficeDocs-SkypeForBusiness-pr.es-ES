---
title: Cambios realizados por la preparación del bosque en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: En esta sección se describe la configuración global y los objetos, así como el servicio universal y los grupos de administración, que se crean mediante el paso de preparación del bosque.
ms.openlocfilehash: 3da4c97a5dab0b7738f01201f9c0cc5b4e34a782
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745876"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Cambios realizados por la preparación del bosque en Skype Empresarial Server

En esta sección se describe la configuración global y los objetos, así como el servicio universal y los grupos de administración, que se crean mediante el paso de preparación del bosque.

## <a name="active-directory-global-settings-and-objects"></a>Configuración global y objetos de Active Directory

Si almacena la configuración global en el contenedor De configuración (como ocurre con todas las implementaciones de Skype Empresarial Server nuevas), la preparación del bosque usa el contenedor de servicios existente y agrega un objeto de servicio **RTC** en el objeto Configuration\Services. Al preparar el bosque, se agrega un objeto de **Global Settings** de tipo msRTCSIP-GlobalContainer dentro del objeto RTC Service. El objeto de configuración global contiene toda la configuración que se aplica a la Skype Empresarial Server implementación. Si almacena la configuración global en el contenedor System, al preparar el bosque se usa un contenedor Microsoft dentro del contenedor System del dominio raíz y se agrega un objeto RTC Service dentro del objeto System\Microsoft.

Al preparar el bosque, se agrega también un nuevo objeto **msRTCSIP-Domain** para el dominio raíz en el que se ejecuta el procedimiento.

## <a name="active-directory-universal-service-and-administration-groups"></a>Servicio universal y grupos de administración de Active Directory

La preparación del bosque crea grupos universales basados en el dominio especificado y agrega entradas de control de acceso (ACE) para estos grupos. Este paso crea los grupos universales en los contenedores User del dominio especificado.

Los grupos universales permiten a los administradores obtener acceso a la configuración global y los servicios y administrarlos. La preparación del bosque agrega los siguientes tipos de grupos universales:

- **Grupos administrativos** Estos grupos definen roles de administrador para una Skype Empresarial Server red.

- **Grupos de infraestructura** Estos grupos proporcionan permiso para obtener acceso a áreas específicas de la Skype Empresarial Server infraestructura. Funcionan como componentes de grupos administrativos. No debe modificar estos grupos ni agregar usuarios directamente.

- **Grupos de servicios** Estos grupos son cuentas de servicio necesarias para tener acceso a varios Skype Empresarial Server servicios.

En la tabla siguiente se describen los grupos administrativos.

**Grupos administrativos creados durante la preparación de un bosque**

|**Grupo administrativo**|**Descripción**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permite a los miembros administrar la configuración de los servidores y grupos de servidores, incluidos todos los roles de servidor, la configuración global y los usuarios.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permite a los miembros administrar la configuración de los usuarios y mover los usuarios de un servidor o grupo de servidores a otro.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permite a los miembros leer la configuración de los servidores, grupos de servidores y usuarios.  <br/> |

En la tabla siguiente se describen los grupos de infraestructura.

**Grupos de infraestructura creados durante la preparación de un bosque**

|**Grupo de infraestructura**|**Descripción**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Concede acceso de escritura a objetos de configuración global para Skype Empresarial Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede acceso de solo lectura a objetos de configuración global para Skype Empresarial Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede acceso de solo lectura a Skype Empresarial Server configuración del usuario.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede acceso de solo lectura a Skype Empresarial Server configuración. Este grupo no tiene acceso a la configuración de nivel de grupo de servidores, sino únicamente a la configuración específica de un servidor individual.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede acceso de solo lectura Skype Empresarial Server configuración y se colocan en el grupo Administradores locales de los dispositivos de sucursal con funciones de supervivencia durante la instalación.  <br/> |

En la tabla siguiente se describen los grupos de servicio.

**Grupos de servicio creados durante la preparación de un bosque**

|**Grupo de servicio**|**Descripción**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Incluye cuentas de servicio usadas para ejecutar servidores front-end y servidores Standard Edition cliente. Este grupo permite a los servidores acceso de lectura y escritura Skype Empresarial Server configuración global y objetos de usuario de Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Incluye cuentas de servicio usadas para ejecutar servidores de conferencia A/V, servicios web, servidor de mediación, servidor de archivado y servidor de supervisión.  <br/> |
|RTCProxyUniversalServices  <br/> |Incluye cuentas de servicio usadas para ejecutar Skype Empresarial Server servidores perimetrales.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Incluye servidores que pueden participar en la replicación Skype Empresarial Server almacén de administración central.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede acceso de solo lectura a Skype Empresarial Server configuración, pero permite la configuración para la instalación de un servidor de sucursal con funciones de supervivencia y una implementación de aplicación de sucursal con funciones de supervivencia.  <br/> |

A continuación, la preparación del bosque agrega los grupos de servicio y administración a los grupos de infraestructura correspondientes del siguiente modo:

- RTCUniversalServerAdmins se agrega a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins se agrega como miembro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices y RTCUniversalReadOnlyAdmins se agregan como miembros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

Durante la preparación del bosque también se crean los siguientes grupos de control de acceso basado en roles (RBAC):

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

- CsResponseGroupManager

Para obtener información detallada sobre los roles RBAC y las tareas que cada uno de ellos puede acometer, consulte [Role-Based Access Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control) en la documentación de planeación.

La preparación del bosque crea entradas ACE privadas y públicas. Crea ACE privadas en el contenedor de configuración global que usa Skype Empresarial Server. Este contenedor solo lo usa Skype Empresarial Server y se encuentra en el contenedor de configuración o en el contenedor del sistema en el dominio raíz, en función de dónde almacene la configuración global. Las entradas ACE públicas que se crean al preparar el bosque se indican en la siguiente tabla:

**Entradas ACE públicas creadas al preparar el bosque**


| **ACE**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Leer el dominio raíz Contenedor del sistema (no heredado) **\\**\* <br/>        | X  <br/>                            |
| Leer el contenedor DisplaySpecifiers de configuración (no heredado)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>*Las ACE que no se heredan no conceden acceso a objetos secundarios en estos contenedores. Las entradas de control de acceso que se heredan permiten el acceso a los objetos secundarios de estos contenedores.

En el contenedor Configuration, bajo el contexto de nomenclatura de configuración, el procedimiento de preparación del bosque realiza las siguientes tareas:

- Agrega una entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para la página **RTC property** dentro de los atributos adminContextMenu y adminPropertyPages del especificador de presentación de idioma correspondiente a los objetos User, Contact e InetOrgPerson (por ejemplo, CN=user-Display,CN=409,CN=DisplaySpecifiers).

- Agrega un objeto **RTCPropertySet** de tipo **controlAccessRight** en **Extended-Rights** que se aplica a las clases User y Contact.

- Agrega un objeto **RTCUserSearchPropertySet** de tipo **controlAccessRight** en **Extended-Rights** que se aplica a las clases User, Contact, OU y DomainDNS.

- Agrega **msRTCSIP-PrimaryUserAddress** en el atributo **extraColumns** de cada especificador de presentación de unidad organizativa de idioma (por ejemplo, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) y copia los valores del atributo **extraColumns** de la presentación predeterminada (por ejemplo, CN=default-Display, CN=409,CN=DisplaySpecifiers).

- Agrega los atributos de filtro **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** y **msRTCSIP-UserEnabled** en el atributo **attributeDisplayNames** de cada especificador de presentación de idioma de los objetos Users, Contacts e InetOrgPerson (por ejemplo, en inglés: CN=user-Display,CN=409,CN=DisplaySpecifiers).