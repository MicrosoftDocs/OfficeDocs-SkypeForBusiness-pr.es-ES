---
title: Servicios de dominio de Active Directory para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
description: Los servicios de dominio de Active Directory funciona como el servicio de directorio para las redes de Windows Server 2003, Windows Server 2008, Windows Server 2012 y Windows Server 2012 R2. Los servicios de dominio de Active Directory también sirve como la base en la que se basa el Skype para la infraestructura de seguridad de Business Server 2015. El propósito de esta sección es describir cómo Skype para Business Server 2015 usa los servicios de dominio de Active Directory para crear un entorno de confianza para la mensajería instantánea, conferencia Web, medios y voz. Para obtener información detallada sobre la preparación de su entorno para los servicios de dominio de Active Directory, consulte instalar Skype for Business Server 2015 en la documentación de implementación. Para obtener información detallada acerca de la función de los servicios de dominio de Active Directory en redes de Windows Server, vea la documentación de la versión del sistema operativo que se está utilizando.
ms.openlocfilehash: d0beaeba36db02e7b0e4ad76bfefa27a9a49a09d
ms.sourcegitcommit: 4eae947e339e728e5e1f338677860b910aafc029
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="active-directory-domain-services-for-skype-for-business-server-2015"></a>Servicios de dominio de Active Directory para Skype Empresarial Server 2015
 
Los servicios de dominio de Active Directory funciona como el servicio de directorio para las redes de Windows Server 2003, Windows Server 2008, Windows Server 2012 y Windows Server 2012 R2. Los servicios de dominio de Active Directory también sirve como la base en la que se basa el Skype para la infraestructura de seguridad de Business Server 2015. El propósito de esta sección es describir cómo Skype para Business Server 2015 usa los servicios de dominio de Active Directory para crear un entorno de confianza para la mensajería instantánea, conferencia Web, medios y voz. Para obtener información detallada sobre la preparación de su entorno para los servicios de dominio de Active Directory, vea [Instalar Skype para Business Server 2015](../../deploy/install/install.md) en la documentación de implementación. Para obtener información detallada acerca de la función de los servicios de dominio de Active Directory en redes de Windows Server, vea la documentación de la versión del sistema operativo que se está utilizando.
  
Skype para Business Server 2015 usa los servicios de dominio de Active Directory para almacenar:
  
- Configuración global que requieren todos los servidores que ejecuta Skype para Business Server 2015 en un bosque.
    
- Información de servicio que identifica las funciones de todos los servidores que ejecutan Skype para Business Server 2015 en un bosque.
    
- Algunas configuraciones de usuario.
    
## <a name="active-directory-infrastructure"></a>Infraestructura de Active Directory

Requisitos de infraestructura para Active Directory incluyen lo siguiente:
  
- Requisitos del sistema operativo para los controladores de dominio
    
- Requisitos del nivel funcional de dominio y bosque
    
- Requisitos del dominio del catálogo global
    
Para obtener información detallada, vea [requisitos de entorno para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) en la documentación de implementación.
  
## <a name="universal-groups"></a>Grupos universales

Durante la preparación del bosque, Skype para Business Server 2015 crea varios grupos universales dentro de servicios de dominio de Active Directory que tienen permiso para tener acceso y administrar los servicios y la configuración global. Entre estos grupos universales se incluyen:
  
- **Grupos administrativos**. Estos grupos definen los roles de administrador fundamental para un Skype para red Business Server. Durante la preparación del bosque, se agregan estos grupos administrativos a Skype para grupos de infraestructura de Business Server.
    
- **Grupos de servicio**. Estos grupos son cuentas de servicio que requieren acceso a diversos servicios proporcionados por Skype para Business Server.
    
- **Grupos de infraestructura**. Estos grupos proporcionan permiso para tener acceso a áreas específicas de la Skype para infraestructura de Business Server. Funcionan como componentes de los grupos administrativos y no deben modificarse ni se deben agregar directamente usuarios a esos grupos. Durante la preparación del bosque, se añaden grupos de servicio y administración específicos a los grupos de infraestructura correspondientes.
    
Para obtener información detallada acerca de los grupos universales específicos creados cuando preparación de AD para Skype para Business Server, así como los grupos de servicio y administración que se agregan a los grupos de infraestructura, vea [los cambios realizados por la preparación del bosque en Skype para la empresa Servidor](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación.
  
> [!NOTE]
> Skype para Business Server 2015 es compatible con los grupos universales en el Windows Server 2012, así como los sistemas operativos de Windows Server 2003 para controladores de dominio. Los miembros de grupos universales pueden incluir otros grupos y cuentas de cualquier dominio en el árbol de dominio o bosque, y se les pueden asignar permisos en cualquier dominio en el árbol de dominio o bosque. Compatibilidad de grupo universal, combinada con la delegación de administrador, simplifica la administración de una Skype para la implementación de Business Server. Por ejemplo, no es necesario agregar un dominio a otro para que un administrador pueda administrar ambos. 
  
## <a name="role-based-access-control"></a>Control de acceso basado en roles

Además de crear grupos universales de servicio y administración y añadir grupos de servicio y administración a los grupos universales correspondientes, la preparación del bosque también crea grupos de control de acceso basado en roles (RBAC). Para obtener información detallada acerca de los grupos específicos de RBAC creados por la preparación del bosque, vea [cambios realizados por la preparación del bosque en Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) en la documentación de implementación. Para obtener más información acerca de los grupos RBAC, vea [control de acceso basado en roles (RBAC) para Skype para Business Server 2015](role-based-access-control-rbac.md).
  
## <a name="access-control-entries-aces-and-inheritance"></a>Entradas de control de acceso (ACE) y herencia

La preparación del bosque crea ACE privadas y públicas, y añade ACE en los grupos universales que crea. Crea entradas ACE privadas específicas en el contenedor de configuración global utilizado por Skype para Business Server. Este contenedor se utiliza sólo por Skype para Business Server y se encuentra en el contenedor de configuración o en el contenedor del sistema en el dominio raíz, dependiendo de dónde almacenar la configuración global.
  
El paso de preparación del dominio agrega las entradas de control de acceso (ACE) necesarias a los grupos universales que conceden permisos para hospedar y administrar los usuarios dentro del dominio. La preparación del dominio crea entradas ACE en la raíz del dominio y tres contenedores integrados: usuarios, equipos y controladores de dominio.
  
Para obtener información detallada acerca de las entradas ACE públicas creadas y añadidas la preparación del bosque y la preparación del dominio, vea [cambios realizados por la preparación del bosque en Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-forest-preparation.md) y [los cambios realizaron por la preparación del dominio en Skype para Business Server](../../schema-reference/active-directory-schema-extensions-classes-and-attributes/changes-made-by-domain-preparation.md) en el Documentación de implementación.
  
Las organizaciones bloquean a menudo los servicios de dominio de Active Directory (AD DS) para ayudar a mitigar los riesgos de seguridad. Sin embargo, un entorno de Active Directory bloqueado puede limitar los permisos que necesita Skype para Business Server 2015. Puede incluir la eliminación de ACE de contenedores y unidades organizativas y la deshabilitación de la herencia de permisos en los objetos User, Contact, InetOrgPerson o Computer. En un bloqueo hacia abajo el entorno de Active Directory, se deben establecer permisos manualmente en contenedores y unidades organizativas que les exige.
  
## <a name="server-information"></a>Información sobre el servidor

Durante la activación, Skype para Business Server 2015 publica información de servidor en las tres ubicaciones siguientes en los servicios de dominio de Active Directory:
  
- Una conexión de servicio punto (SCP) de cada objeto de equipo de Active Directory correspondiente a un equipo físico en el que está instalado Skype para Business Server 2015.
    
- Objetos de servidor creados en el contenedor de la clase **msRTCSIP-Pools**.
    
- Servidores de confianza especificados en el generador de topología.
    
## <a name="service-connection-points"></a>Puntos de conexión de servicio

Cada Skype para objeto Business Server 2015 en servicios de dominio de Active Directory tiene un SCP denominado Servicios de RTC, que a su vez contiene un número de atributos que identifican cada equipo y especificar los servicios que proporciona. Entre la SCP más importante atributos son *serviceDNSName* , *conexión* , *serviceClassname* y *serviceBindingInformation* . Las aplicaciones de administración de activos de otro fabricante pueden recuperar la información de servidor de una implementación consultando estos y otros atributos de los SCP.
  
## <a name="active-directory-server-objects"></a>Objetos de servidor de Active Directory

Cada Skype para rol de servidor de Business Server 2015 tiene un Active Directory correspondiente objeto cuyos atributos definen los servicios proporcionados por dicha función. Además, cuando se activa un servidor Standard Edition o cuando se crea un grupo de servidores Enterprise Edition, Skype para Business Server 2015 crea un nuevo objeto **msRTCSIP-Pool** en el contenedor **msRTCSIP-Pools** . La clase **msRTCSIP-Pool** especifica el nombre de dominio completo (FQDN) del grupo, junto con la asociación entre los componentes front-end y back-end del grupo de servidores. (Un servidor Standard Edition se considera como un grupo de servidores lógico cuyo front y back-end se combina en un único equipo).
  
## <a name="trusted-servers"></a>Servidores de confianza

En Skype para Business Server 2015, servidores de confianza son los que se especifica al ejecutar el generador de topología y publicar su topología. La topología publicada, incluida toda la información del servidor, se almacena en el almacén de administración central. Solo los servidores definidos en el almacén de administración central son de confianza. En Skype para Business Server 2015, un servidor de confianza es uno que cumple los criterios siguientes:
  
- El FQDN del servidor se produce en la topología almacenada en el almacén de administración central.
    
- El servidor presenta un certificado válido de una CA de confianza. Para obtener información detallada, vea [requisitos de entorno para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
    
Si no se cumple alguno de estos criterios, el servidor no se considera de confianza y se rechaza la conexión con dicho servidor. Este requisito doble evita que un ataque posible, aunque poco probable, en el que un servidor no autorizado intenta adoptar el FQDN de un servidor válido.
  
Además, para habilitar implementaciones de Microsoft Office Communications Server 2007 y Microsoft Office Communications Server 2007 R2 a comunicarse con Skype para servidores Business Server 2015, Skype para Business Server 2015 crea contenedores durante del bosque preparación para las listas de servidores de confianza para las versiones anteriores. La siguiente tabla describe los contenedores creados para habilitar la compatibilidad con implementaciones anteriores.
  
**Listas de servidores y sus contenedores de Active Directory de confianza para la compatibilidad con versiones anteriores**

|**Lista de servidores de confianza**|**Contenedor de Active Directory**|
|:-----|:-----|
|Servidores de Standard Edition y servidores front-end del grupo Enterprise Edition  <br/> |Servicio RTC/Configuración global  <br/> |
|Servidores de conferencia  <br/> |Servicio RTC/MCU de confianza  <br/> |
|Servidores de componentes web  <br/> |Servicio RTC/Servidores de componentes web de confianza  <br/> |
|Servidores de mediación y servidores de Communicator Web Access, Servidor de aplicaciones, Registrador con QoE, Servicio de conferencia A/V (también servidores SIP de otros fabricantes)  <br/> |Servicio RTC/Servicios de confianza  <br/> |
|Servidores proxy  <br/> |Skype para Business Server 2015 no admite la compatibilidad con versiones anteriores de los servidores proxy  <br/> |
   

## <a name="see-also"></a>Vea también

#### 
[Preparar Active Directory para Skype para Business Server 2015](../../deploy/install/prepare-active-directory.md)