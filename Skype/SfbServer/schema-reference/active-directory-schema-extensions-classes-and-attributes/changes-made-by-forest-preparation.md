---
title: Cambios realizados por la preparación del bosque en Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
description: Esta sección describe la configuración global y los objetos y los grupos universales de servicio y administración que son creados por el paso de preparación del bosque.
ms.openlocfilehash: 3e37948cae33412ac028d5190c780d6bee5aeeb2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="changes-made-by-forest-preparation-in-skype-for-business-server"></a>Cambios realizados por la preparación del bosque en Skype para Business Server
 
Esta sección describe la configuración global y los objetos y los grupos universales de servicio y administración que son creados por el paso de preparación del bosque.
  
## <a name="active-directory-global-settings-and-objects"></a>Objetos y la configuración Global de active Directory

Si almacena la configuración global en el contenedor de configuración (como es el caso de todos los nuevos Skype para implementaciones de servidores empresariales), la preparación del bosque utiliza el contenedor de servicios existente y agrega un objeto **RTC Service** bajo el Configuración\Servicios objeto. Preparación del bosque agrega un objeto **Global Settings** de tipo msRTCSIP-GlobalContainer bajo el objeto RTC Service. El objeto global settings contiene toda la configuración que se aplican a la Skype para la implementación de Business Server. Si almacena la configuración global en el contenedor del sistema, la preparación del bosque utiliza un contenedor de Microsoft bajo el contenedor del sistema de dominio raíz y un objeto RTC Service bajo el objeto System\Microsoft.
  
Preparación del bosque también agrega un nuevo objeto **msRTCSIP-Domain** para el dominio raíz en el que se ejecuta el procedimiento.
  
## <a name="active-directory-universal-service-and-administration-groups"></a>Servicio Universal de Active Directory y grupos de administración

Preparación del bosque crea grupos universales basándose en el dominio especificado y agrega las entradas de control de acceso (ACE) para estos grupos. Este paso crea los grupos universales en los contenedores de usuarios del dominio especificado. 
  
Los grupos universales permiten a los administradores tener acceso y administrar servicios y configuración global. Preparación del bosque agrega los siguientes tipos de grupos universales:
  
- **Grupos administrativos** Estos grupos de definen las funciones de administrador de un Skype para red Business Server.
    
- **Grupos de infraestructura** Estos grupos proporcionan el permiso de acceso a áreas específicas de la Skype para infraestructura de servidores empresariales. Funcionan como componentes de los grupos administrativos. No debe modificar estos grupos o agregar usuarios directamente a ellos.
    
- **Grupos de servicio** Estos grupos son cuentas de servicio que requieren acceso a varios Skype para Business Server services.
    
La tabla siguiente describen los grupos administrativos.
  
**Grupos administrativos creados durante la preparación del bosque**

|**Grupo administrativo**|**Descripción**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> |Permite a los miembros administrar el servidor y configuración del grupo, incluyendo todos los roles de servidor, la configuración global y los usuarios.  <br/> |
|RTCUniversalUserAdmins  <br/> |Permite administrar la configuración de usuario y mover usuarios desde un servidor o un grupo a otro.  <br/> |
|RTCUniversalReadOnlyAdmins  <br/> |Permite a los miembros al leer la configuración del servidor, grupo y usuario.  <br/> |
   
En la tabla siguiente se describe los grupos de infraestructura.
  
**Grupos de infraestructura durante la preparación del bosque**

|**Grupo de infraestructura**|**Descripción**|
|:-----|:-----|
|RTCUniversalGlobalWriteGroup  <br/> |Concede acceso de escritura a los objetos de configuración global de Skype para Business Server.  <br/> |
|RTCUniversalGlobalReadOnlyGroup  <br/> |Concede acceso de sólo lectura a los objetos de configuración global de Skype para Business Server.  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |Concede acceso de sólo lectura a Skype para la configuración de usuario de Business Server.  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |Concede acceso de sólo lectura a Skype para la configuración del servidor de empresa. Este grupo no tiene acceso a la configuración de nivel de grupo, sólo a valores específicos de un servidor individual.  <br/> |
|RTCUniversalSBATechnicians  <br/> |Concede acceso de sólo lectura a Skype para la configuración del servidor de la empresa y se colocan en el grupo de administradores locales de los dispositivos de la rama que puede perdurar durante la instalación.  <br/> |
   
En la tabla siguiente se describe los grupos de servicio.
  
**Grupos de servicio creados durante la preparación del bosque**

|**Grupo de servicio**|**Descripción**|
|:-----|:-----|
|RTCHSUniversalServices  <br/> |Incluye las cuentas de servicio utilizadas para ejecutar el servidor Front-End y servidores Standard Edition. Este grupo permite acceso de lectura y escritura de servidores a Skype para configuración global Business Server y objetos de usuario de Active Directory.  <br/> |
|RTCComponentUniversalServices  <br/> |Incluye cuentas de servicio utilizadas para ejecutar A / V servidores de conferencia, servicios Web, servidor de mediación, servidor de archivado y el servidor de supervisión.  <br/> |
|RTCProxyUniversalServices  <br/> |Incluye cuentas de servicio utilizadas para ejecutar Skype para servidores de borde de servidor empresariales.  <br/> |
|RTCUniversalConfigReplicator  <br/> |Incluye servidores que pueden participar en Skype para replicación de almacén de Administración Central de servidores empresariales.  <br/> |
|RTCSBAUniversalServices  <br/> |Concede acceso de sólo lectura a Skype para la configuración del servidor de la empresa, pero permite la configuración de la instalación de un servidor de sucursal que sobreviven y la implementación de dispositivos de la rama que sobreviven.  <br/> |
   
Preparación del bosque agrega grupos de administración y servicio a los grupos de infraestructura adecuada, como sigue:
  
- RTCUniversalServerAdmins se agrega a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.
    
- RTCUniversalUserAdmins se agrega como un miembro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.
    
- RTCHSUniversalServices, RTCComponentUniversalServices y RTCUniversalReadOnlyAdmins se agregan como miembros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.
    
Preparación del bosque también crea los siguientes grupos de acceso basado en roles (RBAC) de control:
  
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
    
Para obtener más información acerca de funciones RBAC y las tareas permitidas para cada uno, consulte [Role-Based Access Control](http://technet.microsoft.com/library/41204ba3-ce5b-41a8-a6c3-b444468fa328.aspx) en la documentación de planeamiento.
  
Preparación del bosque crea ACE privadas y públicas. Crea en el contenedor de configuración global utilizado por Skype para Business Server privadas ACE. Este contenedor sólo utiliza Skype para Business Server y se encuentra en el contenedor de configuración o en el contenedor del sistema en el dominio raíz, dependiendo de dónde guardar la configuración global. Las ACE públicas creadas por la preparación del bosque se enumeran en la tabla siguiente.
  
**ACE públicas creadas por la preparación del bosque**

|**ACE**|**RTCUniversalGlobalReadOnlyGroup**|
|:-----|:-----|
|Leer el dominio raíz del contenedor del sistema (no heredado)**\*** <br/> |X  <br/> |
|Contenedor de configuración de lectura DisplaySpecifiers (no heredado)  <br/> |X  <br/> |
   
> [!NOTE]
> **\***Las ACE que no son heredadas no conceden acceso a los objetos secundarios en estos contenedores. Las ACE heredadas conceden acceso a los objetos secundarios en estos contenedores. 
  
En el contenedor Configuración, bajo el contexto de nomenclatura de configuración, la preparación del bosque realiza las siguientes tareas:
  
- Agrega una entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para la página de **propiedades RTC** en la correspondiente y especificador para usuarios, contactos y objetos InetOrgPerson de presentación de atributos adminPropertyPages del lenguaje (por ejemplo, CN = user-Display, CN = 409, CN = DisplaySpecifiers).
    
- Agrega un objeto **RTCPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases de usuario y contacto.
    
- Agrega un objeto **RTCUserSearchPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases de usuario, contacto, OU y DomainDNS.
    
- Agrega **msRTCSIP-PrimaryUserAddress** bajo el atributo **extraColumns** de cada especificador de presentación de la unidad organizativa (OU) de idioma (por ejemplo, CN = organizationalUnit-Display, CN = 409, CN = DisplaySpecifiers) y copia los valores de la atributo **extraColumns** de la presentación predeterminada (por ejemplo, CN = predeterminado-Display, CN = 409, CN = DisplaySpecifiers).
    
- Agrega **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**y **msRTCSIP-UserEnabled** filtrado de atributos bajo el atributo **attributeDisplayNames** de cada idioma mostrar especificador para usuarios, contactos, y objetos InetOrgPerson (por ejemplo, en inglés: CN = user-Display, CN = 409, CN = DisplaySpecifiers).
    

