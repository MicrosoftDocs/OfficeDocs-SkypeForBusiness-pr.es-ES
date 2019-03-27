---
title: Las clases de esquema y descripciones de Skype para Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: Esta sección describe todas las clases de esquema que usa Skype para Business Server.
ms.openlocfilehash: 0bb34a93ec23df67d19026e82e29769e0aeb9ab2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926563"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Las clases de esquema y descripciones de Skype para Business Server
 
Esta sección describe todas las clases de esquema que usa Skype para Business Server. 
  
## <a name="schema-classes-and-descriptions"></a>Las clases de esquema y descripciones

|**Clase**|**Descripción**|**Comentarios**|
|:-----|:-----|:-----|
|Destinatario de correo  <br/> |Destinatario de correo electrónico de mensajería unificada de Exchange (UM).  <br/> |Esta clase auxiliar se comparte con la mensajería unificada de Exchange.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Esta clase es un contenedor para varios contactos de la aplicación y no contiene ningún atributo propio.  <br/> |Nuevo en Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Esta clase contiene la entrada para el punto de control de servicio de una instancia de los servicios del aplicación de comunicaciones unificadas (UCAS).  <br/> |Nuevo en Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Esta clase proporciona una asociación de un grupo de servidores concreto a su servicio de la aplicación.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-ApplicationServer contiene los atributos que representan la configuración para instancias de la aplicación.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con el archivado.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsoleto)  <br/> |Esta clase representa un único servidor de archivado de mensajería de instantánea. Se crea una instancia de esta clase cuando se activa un equipo como un archivado servidor de mensajería instantánea, como un equipo con el servicio de archivado de mensajería instantánea instalado.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Esta clase es un contenedor para varias instancias de directorios de conferencia y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Esta clase contiene los atributos que representan la configuración de un directorio de conferencia específico.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Punto de control de servicio (SCP) para especificar el equipo como un servidor que ejecuta Skype para Business Server.  <br/> |Nuevo en Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Esta clase auxiliar contiene la configuración para un Skype para banco de aplicación Web de negocio.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Esta clase contiene atributos que definen los dominios configurados del registrador SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Este contenedor de clases representa un único servicio de servidor perimetral de acceso. Dado que un servicio de servidor perimetral de acceso se implementa en la red perimetral y los clientes normalmente no permiten el acceso de los servicios de dominio de Active Directory desde la red perimetral, instancias del servicio de servidor perimetral de acceso no se unen a la red de Active Directory de la intranet. Por lo tanto, los servidores proxy de acceso no se registran automáticamente en AD DS. El administrador debe configurar manualmente la existencia de cada instancia del servicio de servidor perimetral de acceso en AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Esta clase auxiliar de msRTCSIP-MCU contiene los atributos que representan la configuración de los servidores de conferencia.  <br/> |Nuevo en Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-MediationServer contiene los atributos que representan la configuración de los servidores de mediación.  <br/> |Nuevo en Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-Server contiene los atributos que representan la configuración de los servidores SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con la federación.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Esta clase contiene toda la configuración que se aplica a lo largo de un Skype para la implementación de Business Server.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsoleto)  <br/> |Esta clase representa una sola directiva de reunión de Office Communications Server.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |El objeto de configuración de la topología global local.  <br/> |Es una novedad en Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Contenedor para abarcar los objetos de configuración de topología global.  <br/> |Es una novedad en Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Esta clase es un contenedor que representa una instancia de una regla de normalización de ubicación.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Esta clase se crea mediante la aplicación operador de conferencia y contiene los atributos que se usan para clasificar los números de teléfono de conferencia por región.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Esta clase es un contenedor para varias instancias de ubicación de asignaciones de contacto y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Esta clase es un contenedor que representa un perfil de ubicación específica.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsoleto)  <br/> |Esta clase es un contenedor para varios perfiles de ubicación y no contiene ningún atributo propio.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsoleto)  <br/> |Esta clase es un contenedor para varias reglas de normalización local y no contiene ningún atributo propio.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Esta clase representa un único servidor de conferencia.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Esta clase contiene varias clases msRTCSIP-MCUFactory y no tiene atributos propio.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Esta clase es un contenedor que representa una fábrica de servidores de conferencia para un tipo de medio único. Se crea una instancia de esta clase cuando se activa el primer servidor de conferencia para este tipo concreto y el proveedor.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Esta clase proporciona una asociación de un grupo de servidores concreto a su fábrica de servidores de conferencia.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Esta clase contiene la entrada para el punto de control de servicio de un servidor de mediación.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración de reunión configurable.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-movilidad  <br/> |Contenedor que almacena la configuración de movilidad global.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Esta clase contiene los atributos que representan la configuración de un único servidor de supervisión.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsoleto)  <br/> |Esta clase es un contenedor que representa una instancia de una ruta de menor costo a una puerta de enlace o un conjunto de puertas de enlace. Esta información se usa por todos los grupos de servidores Enterprise o los servidores que ejecutan Standard Edition para enrutar las llamadas salientes a la red telefónica conmutada (RTC) de la manera más rentable.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsoleto)  <br/> |Esta clase es un contenedor para varias rutas de costo menor y no contiene ningún atributo propio.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Policies (obsoleto)  <br/> |Esta clase contiene varios Lync Server clases de directiva y no tiene ningún atributo propio.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Esta clase representa un único Skype para grupo de servidores empresariales.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Esta clase contiene varios Skype para grupos de servidores empresarial y no tiene ningún atributo propio.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Esta clase representa el punto de control de pointservice de control de servicio de un grupo de servidores. Los usuarios alojados en un grupo de servidores tienen su msRTCSIP-PrimaryHomeServer de atributo punto a una instancia de esta clase.  <br/> |-  <br/> |
|msRTCSIP-presencia  <br/> |Contenedor que almacena la configuración de presencia global.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración de usuario que mantienen los servidores registradores SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsoleto)  <br/> |Esta clase es un contenedor que representa una instancia de un uso de la ruta de teléfono. Una clase de uso de ruta de teléfono consta de un campo de atributo y un campo de descripción. El campo de atributo define un tipo de uso. El campo de descripción permite a los administradores describir el uso de este atributo en la ruta de teléfono.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsoleto)  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-RouteUsage y no tiene ningún atributo propio.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que limitan y controlan el ámbito de resultados de búsqueda.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Esta clase representa un único servidor que ejecuta Skype para Business Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Esta clase contiene el contenedor de configuración global y los objetos msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Esta clase contiene los atributos que representan la configuración de un servidor de conferencia de confianza.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-TrustedMCU y no tiene ningún atributo propio.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Esta clase contiene varias clases msRTCSIP-TrustedProxy y no contiene ningún atributo propio.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Esta clase es un contenedor que representa un servidor que ejecuta el servidor Proxy. Se crea una instancia de esta clase al activar un nuevo servidor Proxy en un equipo unido a AD DS.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Esta clase contiene los atributos que representan la configuración de un servidor de confianza.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Esta clase es un contenedor que representa un servicio de confianza que es enrutable mediante una dirección globalmente enrutable usuario agente URI (GRUU). Cuando se activa un servidor nuevo que sea de confianza por Skype para Business Server, se crea una instancia de esta clase. Esto de confianza de servidor debe estar unido a un dominio de Active Directory.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Esta clase es un contenedor para varios servidores GRUU y no contiene ningún atributo propio.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Esta clase contiene los atributos que representan la configuración de un componente web de confianza.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-TrustedWebComponentServer y no tiene ningún atributo propio.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos relacionados con las comunicaciones unificadas.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Esta clase contiene el punto de control de pointservice de control de servicio de Internet Information Server (IIS). Identifica un servidor como un servidor de componentes web.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Esta clase proporciona una asociación de un grupo de servidores concreto a los componentes web que usará el grupo de servidores.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Esta clase auxiliar de msRTCSIP-WebComponents contiene los atributos que representan la configuración de componentes web.  <br/> |Es una novedad en Communications Server 2007.  <br/> |
   

