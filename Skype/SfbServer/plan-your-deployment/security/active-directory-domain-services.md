---
title: Servicios de dominio de Active Directory para Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Servicios de dominio de Active Directory funciona como servicio de directorio para redes de Windows Server 2003, Windows Server 2008, Windows Server 2012 y Windows Server 2012 R2. Los Servicios de dominio de Active Directory también sirven como base para crear la infraestructura de seguridad de Skype Empresarial Server. El propósito de esta sección es describir cómo Skype Empresarial Server usa los Servicios de dominio de Active Directory para crear un entorno de confianza para mensajería instantánea, conferencias web, medios y voz. Para obtener más información sobre cómo preparar el entorno para los Servicios de dominio de Active Directory, consulte Instalar Skype Empresarial Server en la documentación sobre implementación. Para obtener más información sobre el rol de los Servicios de dominio de Active Directory en redes de Windows Server, consulte la documentación de la versión del sistema operativo que está usando.
ms.openlocfilehash: c4fea392fbabafa0852c21aa5b15118f2427319a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832330"
---
# <a name="active-directory-domain-services-for-skype-for-business-server"></a>Servicios de dominio de Active Directory para Skype Empresarial Server
 
Servicios de dominio de Active Directory funciona como servicio de directorio para redes de Windows Server 2003, Windows Server 2008, Windows Server 2012 y Windows Server 2012 R2. Los Servicios de dominio de Active Directory también sirven como base para crear la infraestructura de seguridad de Skype Empresarial Server. El propósito de esta sección es describir cómo Skype Empresarial Server usa los Servicios de dominio de Active Directory para crear un entorno de confianza para mensajería instantánea, conferencias web, medios y voz. Para obtener más información sobre cómo preparar el entorno para los Servicios de dominio de Active Directory, consulte [Instalar Skype Empresarial Server](../../deploy/install/install.md) en la documentación sobre implementación. Para obtener más información sobre el rol de los Servicios de dominio de Active Directory en redes de Windows Server, consulte la documentación de la versión del sistema operativo que está usando.
  
Skype Empresarial Server usa los Servicios de dominio de Active Directory para almacenar:
  
- Configuración global que requieren todos los servidores que ejecutan Skype Empresarial Server en un bosque.
    
- Información de servicio que identifica los roles de todos los servidores que ejecutan Skype Empresarial Server en un bosque.
    
- Algunas opciones de configuración de usuario.
    
## <a name="active-directory-infrastructure"></a>Infraestructura de Active Directory

Entre los requisitos de infraestructura para Active Directory se incluyen los siguientes:
  
- Requisitos del sistema operativo para controladores de dominio
    
- Requisitos de nivel funcional de dominio y bosque
    
- Requisitos de dominio de catálogo global
    
Para obtener más información, consulte Requisitos del entorno [para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o Requisitos de servidor para Skype Empresarial Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
  
## <a name="universal-groups"></a>Grupos universales

Durante la preparación del bosque, Skype Empresarial Server crea varios grupos universales dentro de los Servicios de dominio de Active Directory que tienen permiso para acceder y administrar la configuración global y los servicios. Estos grupos universales incluyen:
  
- **Grupos administrativos**. Estos grupos definen los roles de administrador fundamentales para una red de Skype Empresarial Server. Durante la preparación del bosque, estos grupos de administradores se agregan a los grupos de infraestructura de Skype Empresarial Server.
    
- **Grupos de servicios**. Estos grupos son cuentas de servicio necesarias para acceder a varios servicios proporcionados por Skype Empresarial Server.
    
- **Grupos de infraestructura**. Estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Skype Empresarial Server. Funcionan como componentes de grupos administrativos y no se deben modificar ni agregar usuarios directamente. Durante la preparación del bosque, se agregan grupos de servicio y administración específicos a los grupos de infraestructura adecuados.
    
Para obtener más información sobre los grupos universales específicos creados al preparar AD para Skype Empresarial Server, así como los grupos de servicio y administración que se agregan a los grupos de infraestructura, consulte Los cambios realizados por la preparación del bosque en [Skype Empresarial Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación sobre implementación.
  
> [!NOTE]
> Skype Empresarial Server admite los grupos universales de Windows Server 2012, así como los sistemas operativos Windows Server 2003 para controladores de dominio. Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque. La compatibilidad de grupo universal, combinada con la delegación de administrador, simplifica la administración de una implementación de Skype Empresarial Server. Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos. 
  
## <a name="role-based-access-control"></a>Role-Based control de acceso

Además de crear grupos de servicio y administración universales y agregar grupos de servicio y administración a los grupos universales adecuados, la preparación del bosque también crea grupos de control de acceso Role-Based (RBAC). Para obtener más información sobre los grupos RBAC específicos creados por la preparación del bosque, consulte Los cambios realizados por la preparación del bosque [en Skype Empresarial Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación sobre implementación. Para obtener más información acerca de los grupos RBAC, consulte Control de acceso basado en [roles (RBAC) para Skype Empresarial Server.](role-based-access-control-rbac.md)
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de control de acceso (ACE) y herencia

La preparación del bosque crea ACE privadas y públicas, y agrega ACE para los grupos universales que crea. Crea ACE privadas específicas en el contenedor de configuración global usado por Skype Empresarial Server. Este contenedor solo lo usa Skype Empresarial Server y se encuentra en el contenedor de configuración o en el contenedor del sistema en el dominio raíz, en función de dónde almacene la configuración global.
  
El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.
  
Para obtener más información sobre las ACE públicas creadas y agregadas por la preparación del bosque y la preparación del dominio, consulte Los cambios realizados por la preparación del bosque en [Skype Empresarial Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) y los cambios realizados por la preparación del dominio en Skype Empresarial [Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) en la documentación sobre implementación.
  
A menudo, las organizaciones bloquean los Servicios de dominio de Active Directory (AD DS) para ayudar a mitigar los riesgos de seguridad. Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que necesita Skype Empresarial Server. Esto puede incluir la eliminación de ACE de contenedores y us y la deshabilitación de la herencia de permisos en objetos User, Contact, InetOrgPerson o Computer. En un entorno de Active Directory bloqueado, los permisos deben establecerse manualmente en contenedores y us que los requieran.
  
## <a name="server-information"></a>Información del servidor

Durante la activación, Skype Empresarial Server publica información del servidor en las tres ubicaciones siguientes de los Servicios de dominio de Active Directory:
  
- Un punto de conexión de servicio (SCP) en cada objeto de equipo de Active Directory correspondiente a un equipo físico en el que está instalado Skype Empresarial Server.
    
- Objetos de servidor creados en el contenedor de la **clase msRTCSIP-Pools.**
    
- Servidores de confianza especificados en el Generador de topologías.
    
## <a name="service-connection-points"></a>Puntos de conexión de servicio

Cada objeto de Skype Empresarial Server de los Servicios de dominio de Active Directory tiene un SCP denominado Servicios RTC, que a su vez contiene una serie de atributos que identifican cada equipo y especifican los servicios que proporciona. Entre los atributos scp más importantes se  *encuentran serviceDNSName*  , *serviceDNSNameType*  , *serviceClassname*  y *serviceBindingInformation*  . Las aplicaciones de administración de activos de terceros pueden recuperar información del servidor en una implementación mediante consultas con estos y otros atributos scp.
  
## <a name="active-directory-server-objects"></a>Objetos de servidor de Active Directory

Cada rol de servidor de Skype Empresarial Server tiene un objeto de Active Directory correspondiente cuyos atributos definen los servicios proporcionados por ese rol. Además, cuando se activa un servidor Standard Edition o cuando se crea un grupo de servidores Enterprise Edition, Skype Empresarial Server crea un nuevo objeto **msRTCSIP-Pool** en el contenedor **msRTCSIP-Pools.** La **clase msRTCSIP-Pool** especifica el nombre de dominio completo (FQDN) del grupo de servidores, junto con la asociación entre los componentes front-end y back-end del grupo. (Un servidor Standard Edition se considera un grupo lógico cuyos front-end y back-end están instalados en un único equipo).
  
## <a name="trusted-servers"></a>Servidores de confianza

En Skype Empresarial Server, los servidores de confianza son los que se especifican al ejecutar el Generador de topologías y publicar la topología. La topología publicada, incluida toda la información del servidor, se almacena en el almacén de administración central. Solo los servidores definidos en el almacén de administración central son de confianza. En Skype Empresarial Server, un servidor de confianza es aquel que cumple los siguientes criterios:
  
- El FQDN del servidor se produce en la topología almacenada en el almacén de administración central.
    
- El servidor presenta un certificado válido de una CA de confianza. Para obtener más información, consulte Requisitos del entorno [para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o requisitos del sistema para Skype Empresarial Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
    
Si falta alguno de estos criterios, el servidor no es de confianza y se rechaza la conexión con él. Este doble requisito evita un posible ataque, si es poco probable, en el que un servidor no autorizado intenta asumir el FQDN de un servidor válido.
  
Además, para permitir que las implementaciones de Microsoft Office Communications Server 2007 R2 y Microsoft Office Communications Server 2007 se comuniquen con los servidores de Skype Empresarial Server, Skype Empresarial Server crea contenedores durante la preparación del bosque para contener listas de servidores de confianza para versiones anteriores. En la tabla siguiente se describen los contenedores creados para habilitar la compatibilidad con implementaciones anteriores.
  
**Listas de servidores de confianza y sus contenedores de Active Directory para compatibilidad con versiones anteriores**

|**Lista de servidores de confianza**|**Contenedor de Active Directory**|
|:-----|:-----|
|Servidores Standard Edition y servidores front-end de grupo de servidores enterprise  <br/> |Servicio RTC/Configuración global  <br/> |
|Servidores de conferencia  <br/> |Servicio RTC/M MCUs de confianza  <br/> |
|Servidores de componentes web  <br/> |Servicio RTC/TrustedWebComponentsServers  <br/> |
|Servidores de mediación y Communicator de acceso web, servidor de aplicaciones, registrador con QoE, servicio de conferencia A/V (también servidores SIP de terceros)  <br/> |Servicio RTC/Servicios de confianza  <br/> |
|Servidores proxy  <br/> |Skype Empresarial Server no admite la compatibilidad con versiones anteriores de servidores proxy  <br/> |
   

## <a name="see-also"></a>Ver también

[Preparar Active Directory para Skype Empresarial Server](../../deploy/install/prepare-active-directory.md)
