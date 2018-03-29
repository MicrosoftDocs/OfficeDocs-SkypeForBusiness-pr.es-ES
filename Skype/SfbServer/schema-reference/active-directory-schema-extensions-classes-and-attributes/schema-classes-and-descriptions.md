---
title: Clases de esquema y descripciones en Skype para Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: Esta sección describe todas las clases de esquema utilizadas por Skype para Business Server.
ms.openlocfilehash: 20d85e879bb9bfb040150423d47836b6e6803c37
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Clases de esquema y descripciones en Skype para Business Server
 
Esta sección describe todas las clases de esquema utilizadas por Skype para Business Server. 
  
## <a name="schema-classes-and-descriptions"></a>Las descripciones y las clases de esquema

|**Clase**|**Descripción**|**Comentarios**|
|:-----|:-----|:-----|
|Destinatario de correo  <br/> |Destinatario de correo electrónico de Exchange Unified Messaging (UM).  <br/> |Esta clase auxiliar se comparte con la mensajería unificada de Exchange.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Esta clase es un contenedor para varios contactos de la aplicación y no contiene ningún atributo propio.  <br/> |Nuevo en Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Esta clase contiene la entrada para el punto de control de servicio de una instancia de servicios unificada de aplicación de comunicaciones (UCAS).  <br/> |Nuevo en Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Esta clase proporciona una asociación entre un grupo específico para su servicio de aplicación.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Esta clase auxiliar msRTCSIP-ApplicationServer contiene atributos que representan la configuración de instancias del servicio de aplicación.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con el archivado.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsoleto)  <br/> |Esta clase representa un servidor de archivado de mensajería único. Se crea una instancia de esta clase cuando se activa un equipo como un Archiving de servidor de mensajería instantánea, como un equipo con el servicio de archivado de mensajería instantánea instalado.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Esta clase es un contenedor para instancias múltiples de directorios de conferencia y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Esta clase tiene atributos que representan la configuración de un directorio de conferencia específica.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Punto de control de servicio genérico (SCP) para especificar el equipo como un servidor que ejecuta Skype para Business Server.  <br/> |Nuevo en Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Esta clase auxiliar contiene la configuración de un Skype para el banco de negocios Web App.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Esta clase tiene atributos que definen los dominios configurados del registrador SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Este contenedor de clases representa un único servicio de servidor perimetral de acceso. Porque un servicio de servidor perimetral de acceso se implementa en la red perimetral y los clientes no suelen conceder acceso a los servicios de dominio de Active Directory de la red perimetral, instancias del servicio de servidor perimetral de acceso no se unen a la red de Active Directory de la intranet. Por lo tanto, los servidores proxy de acceso no se registran automáticamente en AD DS. El administrador debe configurar manualmente la existencia de cada instancia del servicio de servidor perimetral de acceso en AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Esta clase auxiliar msRTCSIP-MCU contiene atributos que representan la configuración de servidores de conferencia.  <br/> |Nuevo en Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Esta clase auxiliar msRTCSIP-MediationServer contiene atributos que representan la configuración para los servidores de mediación.  <br/> |Nuevo en Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-Server contiene los atributos que representan la configuración de los servidores SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con la federación.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Esta clase contiene toda la configuración que se aplica a todo un Skype para la implementación de Business Server.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsoleto)  <br/> |Esta clase representa una única directiva de reunión de Office Communications Server.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |El objeto de configuración de topología global local.  <br/> |Nuevo en Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Contenedor para contener objetos de configuración de la topología global.  <br/> |Nuevo en Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Esta clase es un contenedor que representa una instancia de una regla de normalización de ubicación.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Esta clase se crea aplicando el operador de conferencia y contiene los atributos que se usan para clasificar los números de teléfono de conferencia por región.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Esta clase es un contenedor para instancias múltiples de ubicación asignaciones de contacto y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Esta clase es un contenedor que representa un perfil de ubicación específica.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsoleto)  <br/> |Esta clase es un contenedor para varios perfiles de ubicación y no contiene ningún atributo propio.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsoleto)  <br/> |Esta clase es un contenedor de varias reglas de normalización local y no contiene ningún atributo propio.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Esta clase representa un único servidor de conferencia.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Esta clase contiene varias clases msRTCSIP-MCUFactory y no tiene atributos de sí mismo.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Esta clase es un contenedor que representa una fábrica de Conferencing Server para un único tipo de medio. Cuando se activa el primer servidor de conferencia para este tipo concreto y el proveedor, se crea una instancia de esta clase.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Esta clase proporciona una asociación entre un grupo específico para su fábrica de Conferencing Server.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Esta clase contiene la entrada para el punto de control del servicio para un servidor de mediación.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-reunión (obsoleta)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración de sesión configurable.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-movilidad  <br/> |Contenedor que almacena la configuración global de movilidad.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Esta clase tiene atributos que representan la configuración de un único servidor de supervisión.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsoleto)  <br/> |Esta clase es un contenedor que representa una instancia de una ruta de menor costo a una puerta de enlace o un conjunto de puertas de enlace. Esta información es utilizada por todos los grupos de servidores Enterprise o servidores con Standard Edition para enrutar las llamadas salientes a la red telefónica pública conmutada (PSTN) de la manera más rentable.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsoleto)  <br/> |Esta clase es un contenedor para las rutas múltiples, por lo menos costo y no contiene ningún atributo propio.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-directivas (obsoletas)  <br/> |Esta clase contiene varios Lync Server clases de directivas y no tiene ningún atributo propio.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Esta clase representa un único Skype para el grupo de servidores empresariales.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Esta clase contiene varios Skype para pools de Business Server y no tiene ningún atributo propio.  <br/> |-  <br/> |
|msRTCSIP-PoolService.  <br/> |Esta clase representa el punto de control de pointservice control de servicio de un grupo. Los usuarios alojados en un grupo tienen su msRTCSIP-PrimaryHomeServer punto de atributo a una instancia de esta clase.  <br/> |-  <br/> |
|msRTCSIP-presencia  <br/> |Contenedor que almacena la configuración de presencia global.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración de usuario que mantienen los servidores registradores SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsoleto)  <br/> |Esta clase es un contenedor que representa una instancia de un uso de rutas de teléfono. Una clase de uso de teléfono ruta consta de un campo de atributo y un campo de descripción. El campo de atributo define un tipo de uso. El campo Descripción permite a los administradores describir el uso de este atributo en la ruta de teléfono.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsoleto)  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-RouteUsage y no tiene ningún atributo propio.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que limitan y controlan el alcance de los resultados de la búsqueda.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Esta clase representa un único servidor ejecuta Skype para Business Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Esta clase contiene el contenedor de configuración global y los objetos de dominio msRTCSIP.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Esta clase tiene atributos que representan la configuración de un servidor de conferencias de confianza.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-TrustedMCU y no tiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Esta clase contiene varias clases msRTCSIP-TrustedProxy y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Esta clase es un contenedor que representa a un servidor que ejecuta Proxy Server. Al activar un nuevo servidor Proxy en un equipo unido a AD DS, se crea una instancia de esta clase.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Esta clase tiene atributos que representan la configuración de un servidor de confianza.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Esta clase es un contenedor que representa un servicio de confianza es enrutable utilizando una dirección global enrutable usuario agente URI (GRUU). Cuando se activa un nuevo servidor que Skype es de confianza para Business Server, se crea una instancia de esta clase. Este el servidor debe estar unido a un dominio de Active Directory de confianza.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Esta clase es un contenedor para varios servidores GRUU y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Esta clase tiene atributos que representan la configuración de un componente web de confianza.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-TrustedWebComponentServer y no tiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos relacionados con las comunicaciones unificadas.  <br/> |Ha quedado obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Esta clase contiene el punto de control de pointservice de control de servicios de Internet Information Server (IIS). Identifica un servidor como un servidor de componentes web.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Esta clase proporciona una asociación entre un grupo específico para los componentes web que utilizará el grupo.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Esta clase auxiliar msRTCSIP-WebComponents contiene atributos que representan la configuración de componentes web.  <br/> |Nuevo en Communications Server 2007.  <br/> |
   

