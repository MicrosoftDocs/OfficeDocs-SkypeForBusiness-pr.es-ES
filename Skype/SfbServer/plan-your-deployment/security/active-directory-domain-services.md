---
title: Servicios de dominio de Active Directory para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Los servicios de dominio de Active Directory funcionan como el servicio de directorio para Windows Server 2003, Windows Server 2008, Windows Server 2012 y redes Windows Server 2012 R2. Los servicios de dominio de Active Directory también sirven como la base en la que se ha creado la infraestructura de seguridad de Skype empresarial Server. El propósito de esta sección es describir cómo Skype empresarial Server usa los servicios de dominio de Active Directory para crear un entorno digno de confianza para mensajería instantánea, conferencias web, multimedia y voz. Para obtener detalles sobre cómo preparar el entorno para los servicios de dominio de Active Directory, consulte instalar Skype empresarial Server en la documentación de implementación. Para obtener más información sobre el rol de los servicios de dominio de Active Directory en las redes de Windows Server, consulte la documentación de la versión del sistema operativo que está usando.
ms.openlocfilehash: 4458d49bf2f57284ac29c68bb40f3979761d5c50
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297011"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Servicios de dominio de Active Directory para Skype empresarial Server
 
Los servicios de dominio de Active Directory funcionan como el servicio de directorio para Windows Server 2003, Windows Server 2008, Windows Server 2012 y redes Windows Server 2012 R2. Los servicios de dominio de Active Directory también sirven como la base en la que se ha creado la infraestructura de seguridad de Skype empresarial Server. El propósito de esta sección es describir cómo Skype empresarial Server usa los servicios de dominio de Active Directory para crear un entorno digno de confianza para mensajería instantánea, conferencias web, multimedia y voz. Para obtener detalles sobre cómo preparar el entorno para los servicios de dominio de Active Directory, consulte [instalar Skype empresarial Server](../../deploy/install/install.md) en la documentación de implementación. Para obtener más información sobre el rol de los servicios de dominio de Active Directory en las redes de Windows Server, consulte la documentación de la versión del sistema operativo que está usando.
  
Skype empresarial Server usa los servicios de dominio de Active Directory para almacenar:
  
- Configuración global que necesitan todos los servidores que ejecutan Skype empresarial Server en un bosque.
    
- Información de servicio que identifica los roles de todos los servidores que ejecutan Skype empresarial Server en un bosque.
    
- Algunas configuraciones de usuario.
    
## <a name="active-directory-infrastructure"></a>Infraestructura de Active Directory

Entre los requisitos de infraestructura para Active Directory se incluyen los siguientes:
  
- Requisitos del sistema operativo para los controladores de dominio
    
- Requisitos del nivel funcional de dominio y bosque
    
- Requisitos del dominio del catálogo global
    
Para obtener más información, consulte [requisitos ambientales para Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos de servidor para skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
## <a name="universal-groups"></a>Grupos universales

Durante la preparación del bosque, Skype empresarial Server crea varios grupos universales dentro de los servicios de dominio de Active Directory que tienen permiso para acceder y administrar la configuración global y los servicios. Entre estos grupos universales se incluyen:
  
- **Grupos administrativos**. Estos grupos definen los roles de administrador fundamentales para una red de Skype empresarial Server. Durante la preparación del bosque, estos grupos de administradores se agregan a los grupos de infraestructura de Skype empresarial Server.
    
- **Grupos de servicio**. Estos grupos son cuentas de servicio necesarias para acceder a diversos servicios proporcionados por Skype empresarial Server.
    
- **Grupos de infraestructura**. Estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Skype empresarial Server. Funcionan como componentes de los grupos administrativos y no deben modificarse ni se deben agregar directamente usuarios a esos grupos. Durante la preparación del bosque, se añaden grupos de servicio y administración específicos a los grupos de infraestructura correspondientes.
    
Para obtener más información sobre los grupos universales específicos que se han creado al preparar AD para Skype empresarial Server, así como los grupos de servicio y administración que se agregan a los grupos de infraestructura, consulte [cambios realizados por la preparación del bosque en Skype empresarial Servidor](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.
  
> [!NOTE]
> Skype empresarial Server es compatible con los grupos universales de Windows Server 2012, así como con los sistemas operativos Windows Server 2003 para controladores de dominio. Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque, y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque. La compatibilidad con los grupos universales, junto con la delegación de administrador, simplifica la administración de una implementación de Skype empresarial Server. Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos. 
  
## <a name="role-based-access-control"></a>Control de acceso basado en roles

Además de crear grupos universales de servicio y administración y añadir grupos de servicio y administración a los grupos universales correspondientes, la preparación del bosque también crea grupos de control de acceso basado en roles (RBAC). Para obtener más información sobre los grupos RBAC específicos creados por la preparación del bosque, consulte [Changes made by forest preparation in Skype for Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación sobre implementación. Para obtener más información sobre los grupos RBAC, consulte [control de acceso basado en roles (RBAC) para Skype empresarial Server](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de control de acceso (ACE) y herencia

La preparación del bosque crea ACE privadas y públicas, y añade ACE en los grupos universales que crea. Crea ACE privadas específicas en el contenedor de configuración global usado por Skype empresarial Server. Este contenedor solo lo usa Skype empresarial Server y se encuentra en el contenedor configuración o en el contenedor del sistema en el dominio raíz, según dónde almacene la configuración global.
  
El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.
  
Para obtener detalles sobre las ACE públicas creadas y agregadas por la preparación del bosque y la preparación del dominio, consulte [los cambios realizados por la preparación del bosque en Skype empresarial Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) y [los cambios realizados por la preparación del dominio en Skype empresarial Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) en el Documentación de implementación.
  
Las organizaciones suelen bloquear los servicios de dominio de Active Directory (AD DS) para ayudar a mitigar los riesgos de seguridad. Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que requiere Skype empresarial Server. Puede incluir la eliminación de ACE de contenedores y unidades organizativas y la deshabilitación de la herencia de permisos en los objetos User, Contact, InetOrgPerson o Computer. En un entorno de Active Directory bloqueado, los permisos deben establecerse manualmente en contenedores y unidades organizativas que los requieran.
  
## <a name="server-information"></a>Información sobre el servidor

Durante la activación, Skype empresarial Server publica la información del servidor en las tres siguientes ubicaciones de los servicios de dominio de Active Directory:
  
- Un punto de conexión de servicio (SCP) en cada objeto de equipo de Active Directory correspondiente a un equipo físico en el que está instalado Skype empresarial Server.
    
- Objetos de servidor creados en el contenedor de la clase **msRTCSIP-Pools**.
    
- Servidores de confianza especificados en el generador de topología.
    
## <a name="service-connection-points"></a>Puntos de conexión de servicio

Cada objeto de Skype empresarial Server de los servicios de dominio de Active Directory tiene un SCP denominado servicios de RTC, que a su vez contiene una serie de atributos que identifican cada equipo y especifican los servicios que proporciona. Entre los atributos SCP más importantes están *serviceDNSName* , *serviceDNSNameType* , *serviceClassname* y *serviceBindingInformation* . Las aplicaciones de administración de activos de otro fabricante pueden recuperar la información de servidor de una implementación consultando estos y otros atributos de los SCP.
  
## <a name="active-directory-server-objects"></a>Objetos de servidor de Active Directory

Cada rol de servidor de Skype empresarial Server tiene un objeto de Active Directory correspondiente cuyos atributos definen los servicios proporcionados por ese rol. Además, cuando se activa un servidor Standard Edition o cuando se crea un grupo de servidores Enterprise Edition, Skype empresarial Server crea un nuevo objeto **msRTCSIP-Pool** en el contenedor **msRTCSIP-pools** . La clase **msRTCSIP-Pool** especifica el nombre de dominio completo (FQDN) del grupo, junto con la asociación entre los componentes front-end y back-end del grupo de servidores. (Un servidor Standard Edition se considera un grupo lógico cuyos extremos frontal y posterior se colocan en un solo equipo).
  
## <a name="trusted-servers"></a>Servidores de confianza

En Skype empresarial Server, los servidores de confianza son los que se especifican al ejecutar Topology Builder y publicar su topología. La topología publicada, incluida toda la información del servidor, se almacena en el almacén de administración central. Solo los servidores definidos en el almacén de administración central son de confianza. En Skype empresarial Server, un servidor de confianza es aquel que cumple los siguientes criterios:
  
- El FQDN del servidor se produce en la topología almacenada en el almacén de administración central.
    
- El servidor presenta un certificado válido de una CA de confianza. Para obtener más información, consulte [requisitos ambientales para Skype empresarial server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos del sistema para skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
Si no se cumple alguno de estos criterios, el servidor no se considera de confianza y se rechaza la conexión con dicho servidor. Este doble requisito evita un ataque posible, si no lo es improbable, en el que un servidor malicioso intenta tomar el control de nombre completo de un servidor válido.
  
Además, para permitir que las implementaciones de Microsoft Office Communications Server 2007 R2 y Microsoft Office Communications Server 2007 se comuniquen con los servidores de Skype empresarial, Skype empresarial Server crea contenedores durante la preparación del bosque para almacenar listas de servidores de confianza para versiones anteriores. La siguiente tabla describe los contenedores creados para habilitar la compatibilidad con implementaciones anteriores.
  
**Listas de servidores de confianza y sus contenedores de Active Directory para la compatibilidad con versiones anteriores**

|**Listas de servidores de confianza**|**Contenedor de Active Directory**|
|:-----|:-----|
|Servidores de Standard Edition y servidores front-end del grupo Enterprise Edition  <br/> |Servicio RTC/Configuración global  <br/> |
|Servidores de conferencia  <br/> |Servicio RTC/MCU de confianza  <br/> |
|Servidores de componentes web  <br/> |Servicio RTC/Servidores de componentes web de confianza  <br/> |
|Servidores de mediación y servidores de Communicator Web Access, Servidor de aplicaciones, Registrador con QoE, Servicio de conferencia A/V (también servidores SIP de otros fabricantes)  <br/> |Servicio RTC/Servicios de confianza  <br/> |
|Servidores proxy  <br/> |Skype empresarial Server no admite compatibilidad con versiones anteriores para servidores proxy  <br/> |
   

## <a name="see-also"></a>Vea también

[Preparar Active Directory para Skype empresarial Server](../../deploy/install/prepare-active-directory.md)
