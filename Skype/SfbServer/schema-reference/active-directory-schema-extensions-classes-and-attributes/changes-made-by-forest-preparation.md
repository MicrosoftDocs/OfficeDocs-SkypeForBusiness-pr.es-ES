---
title: Cambios realizados por la preparación del bosque en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: En esta sección se describen la configuración global y los objetos, así como el servicio universal y los grupos de administración creados por el paso de preparación del bosque.
ms.openlocfilehash: ece4a9bd1db5f43b52a96265dee41ee3a0a30b22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296703"
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Cambios realizados por la preparación del bosque en Skype empresarial Server

En esta sección se describen la configuración global y los objetos, así como el servicio universal y los grupos de administración creados por el paso de preparación del bosque.

## <a name="active-directory-global-settings-and-objects"></a>Objetos y configuración global de Active Directory

Si almacena la configuración global en el contenedor de configuración (como es el caso de todas las nuevas implementaciones de Skype empresarial Server), la preparación del bosque usa el contenedor servicios existentes y agrega un objeto de **servicio RTC** en el Configuration\Services examina. En el objeto de servicio RTC, la preparación del bosque agrega un objeto de **configuración global** de tipo MsRTCSIP-GlobalContainer. El objeto configuración global contiene toda la configuración que se aplica a la implementación de Skype empresarial Server. Si almacena la configuración global en el contenedor del sistema, la preparación del bosque usa un contenedor de Microsoft en el contenedor del sistema del dominio raíz y un objeto de servicio RTC bajo el objeto System\Microsoft.

La preparación del bosque también agrega un nuevo objeto **msRTCSIP-Domain** para el dominio raíz en el que se ejecuta el procedimiento.

## <a name="active-directory-universal-service-and-administration-groups"></a>Servicio universal de Active Directory y grupos de administración

La preparación del bosque crea grupos universales basados en el dominio que especifique y agrega entradas de control de acceso (ACE) para estos grupos. Este paso crea los grupos universales en los contenedores de usuario del dominio que especifique.

Los grupos universales permiten a los administradores acceder y administrar la configuración y los servicios globales. La preparación del bosque agrega los siguientes tipos de grupos universales:

- **Grupos administrativos** Estos grupos definen los roles de administrador para una red de Skype empresarial Server.

- **Grupos de infraestructura** Estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Skype empresarial Server. Funcionan como componentes de grupos administrativos. No debe modificar estos grupos ni agregar usuarios directamente.

- **Grupos de servicio** Estos grupos son cuentas de servicio necesarias para acceder a diversos servicios de Skype empresarial Server.

En la tabla siguiente se describen los grupos administrativos.

**Grupos administrativos creados durante la preparación del bosque**

|**Grupo administrativo**|**Descripción**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permite a los miembros administrar la configuración del servidor y del grupo, incluidos los roles de servidor, la configuración global y los usuarios.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permite a los miembros administrar la configuración de usuario y mover los usuarios de un servidor o grupo a otro.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permite que los miembros lean la configuración del servidor, del grupo y del usuario.  <br/> |

En la tabla siguiente se describen los grupos de infraestructura.

**Grupos de infraestructura creados durante la preparación del bosque**

|**Grupo de infraestructura**|**Descripción**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Concede acceso de escritura a objetos de configuración global para Skype empresarial Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede acceso de solo lectura a objetos de configuración global para Skype empresarial Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede acceso de solo lectura a la configuración de usuario de Skype empresarial Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede acceso de solo lectura a la configuración de Skype empresarial Server. Este grupo no tiene acceso a la configuración del nivel de grupo, solo a la configuración específica de un servidor individual.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede acceso de solo lectura a la configuración de Skype empresarial Server y se coloca en el grupo de administradores locales de las aplicaciones de la sucursal que son supervivientes durante la instalación.  <br/> |

En la siguiente tabla se describen los grupos de servicios.

**Grupos de servicio creados durante la preparación del bosque**

|**Grupo de servicio**|**Descripción**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Incluye cuentas de servicio que se usan para ejecutar servidores front-end y servidores Standard Edition. Este grupo permite que los servidores tengan acceso de lectura y escritura a la configuración global de Skype empresarial Server y a los objetos de usuario de Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Incluye cuentas de servicio que se usan para ejecutar servidores de conferencia A/V, servicios Web, servidor de mediación, servidor de archivado y servidor de supervisión.  <br/> |
|RTCProxyUniversalServices  <br/> |Incluye cuentas de servicio que se usan para ejecutar servidores perimetrales de Skype empresarial Server.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Incluye servidores que pueden participar en la replicación del almacén central de administración de Skype empresarial Server.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede acceso de solo lectura a la configuración de Skype empresarial Server, pero permite la configuración de la instalación de un servidor de sucursal y una implementación de dispositivos de la aplicación que sean supervivientes.  <br/> |

La preparación del bosque, a continuación, agrega grupos de servicio y administración a los grupos de infraestructura adecuados, de la siguiente manera:

- RTCUniversalServerAdmins se agrega a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

- RTCUniversalUserAdmins se agrega como miembro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

- RTCHSUniversalServices, RTCComponentUniversalServices y RTCUniversalReadOnlyAdmins se agregan como miembros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.

La preparación del bosque también crea los siguientes grupos de control de acceso basado en roles (RBAC):

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

Para obtener más información sobre los roles RBAC y las tareas permitidas para cada uno, consulte [control de acceso basado en roles](https://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) en la documentación de planeación.

La preparación del bosque crea entradas de acceso privadas y públicas. Crea ACE privadas en el contenedor de configuración global usado por Skype empresarial Server. Este contenedor solo lo usa Skype empresarial Server y se encuentra en el contenedor configuración o en el contenedor del sistema en el dominio raíz, según dónde almacene la configuración global. Las ACE públicas creadas por la preparación del bosque se enumeran en la tabla siguiente.

**ACE públicas creadas por la preparación del bosque**


| **ENTRADA**                                                                 | **RTCUniversalGlobalReadOnlyGroup** |
|:------------------------------------------------------------------------|:------------------------------------|
| Leer el contenedor del sistema del dominio raíz (no heredado)**\\**\* <br/>        | X  <br/>                            |
| Contenedor DisplaySpecifiers de lectura de la configuración (no heredado)  <br/> | X  <br/>                            |

> [!NOTE]
> <strong>\\</strong>* Las ACE que no se heredan no conceden acceso a objetos secundarios en estos contenedores. Las ACE que se heredan otorgan acceso a objetos secundarios en estos contenedores.

En el contenedor configuración, en el contexto de nomenclatura de configuración, la preparación del bosque realiza las siguientes tareas:

- Agrega una entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para la página de **propiedades RTC** en los atributos adminContextMenu y adminPropertyPages del especificador de presentación de idioma para usuarios, contactos y InetOrgPersons (por ejemplo, CN = user-Display, CN = 409, CN = DisplaySpecifiers).

- Agrega un objeto **RTCPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases User y contact.

- Agrega un objeto **RTCUserSearchPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases User, Contact, ou y DomainDNS.

- Agrega **msRTCSIP-PrimaryUserAddress** bajo el atributo de **columnas** extracolumnas del especificador de pantalla de unidad organizativa (OU) de cada idioma (por ejemplo, CN = ORGANIZATIONALUNIT-display, CN = 409, CN = DisplaySpecifiers) y copia los valores de la el atributo de **columnas** extracolumnas de la pantalla predeterminada (por ejemplo, CN = default-display, CN = 409, CN = DisplaySpecifiers).

- Agrega **atributos msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**y **msRTCSIP-UserEnabled** en el atributo **attributeDisplayNames** de cada especificador de presentación de idioma para usuarios, contactos, y objetos InetOrgPerson (por ejemplo, en Inglés: CN = usuario-display, CN = 409, CN = DisplaySpecifiers).


