---
title: Clases de esquema y descripciones en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: En esta sección se describen todas las clases de esquema usadas por Skype Empresarial Server.
ms.openlocfilehash: 6c4b5d12baf85a1e9f168940fc889f6f18063616
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813560"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Clases de esquema y descripciones en Skype Empresarial Server
 
En esta sección se describen todas las clases de esquema usadas por Skype Empresarial Server. 
  
## <a name="schema-classes-and-descriptions"></a>Clases de esquema y descripciones

|**Clase**|**Descripción**|**Comments**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Destinatario de correo electrónico de mensajería unificada (MU) de Exchange.  <br/> |Esta clase auxiliar se comparte con la mensajería unificada de Exchange.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Esta clase es un contenedor para varios contactos de aplicación y no contiene ningún atributo propio.  <br/> |Nuevo en Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Esta clase contiene la entrada del punto de control de servicio de una instancia de los servicios de aplicación de comunicaciones unificadas (UCAS).  <br/> |Nuevo en Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Esta clase proporciona una asociación de un grupo específico a su servicio de aplicación.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-ApplicationServer contiene atributos que representan la configuración de instancias del servicio de aplicación.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con el archivado.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsoleto)  <br/> |Esta clase representa un único servidor de archivado de mensajería instantánea. Cuando un equipo se activa como servidor de archivado de mensajería instantánea (por ejemplo, un equipo que tiene instalado el servicio de archivado de mensajería instantánea), se crea una instancia de esta clase.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Esta clase es un contenedor para varias instancias de directorios de conferencia y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Esta clase contiene los atributos que representan la configuración de un directorio de conferencia específico.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Punto de control de servicio genérico (SCP) para especificar el equipo como un servidor que ejecuta Skype Empresarial Server.  <br/> |Nuevo en Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Esta clase auxiliar contiene la configuración de un banco de aplicaciones web de Skype Empresarial.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Esta clase contiene atributos que definen los dominios configurados del registrador SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Este contenedor de clase representa un único servicio perimetral de acceso. Dado que se implementa un servicio perimetral de acceso en la red perimetral y los clientes normalmente no permiten el acceso a los Servicios de dominio de Active Directory desde la red perimetral, las instancias del servicio perimetral de acceso no se unen a la red de Active Directory de la intranet. En consecuencia, los servidores proxy de acceso no se registran automáticamente en AD DS. El administrador debe configurar manualmente la existencia de cada instancia del servicio perimetral de acceso en AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Esta clase auxiliar de msRTCSIP-MCU contiene los atributos que representan la configuración de los servidores de conferencia.  <br/> |Nuevo en Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-MediationServer contiene los atributos que representan la configuración de los servidores de mediación.  <br/> |Nuevo en Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-Server contiene los atributos que representan la configuración de los servidores SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con la federación.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Esta clase contiene todas las configuraciones que se aplican en toda una implementación de Skype Empresarial Server.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsoleto)  <br/> |Esta clase representa una única directiva de reunión de Office Communications Server.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |El objeto de configuración de la topología global local.  <br/> |Nuevo en Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Contenedor para abarcar los objetos de configuración de topología global.  <br/> |Nuevo en Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Esta clase es un contenedor que representa una instancia de una regla de normalización de ubicación.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Esta clase se crea mediante la aplicación Operador de conferencia y contiene los atributos usados para clasificar los números de teléfono de conferencia por región.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Esta clase es un contenedor para varias instancias de asignaciones de contacto de ubicación y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Esta clase es un contenedor que representa un perfil de ubicación concreto.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsoleto)  <br/> |Esta clase es un contenedor para varios perfiles de ubicación y no contiene ningún atributo propio.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsoleto)  <br/> |Esta clase es un contenedor para varias reglas de normalización local y no contiene ningún atributo propio.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Esta clase representa un único servidor de conferencia.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Esta clase contiene varias clases msRTCSIP-MCUFactory y no tiene atributos propios.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Esta clase es un contenedor que representa una fábrica de servidores de conferencia de un solo tipo de medio. Se crea una instancia de esta clase cuando se activa el primer servidor de conferencia para este tipo y proveedor.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Esta clase proporciona una asociación de un grupo de servidores específico con su fábrica de servidores de conferencia.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Esta clase contiene la entrada del punto de control de servicio de un servidor de mediación.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene atributos que representan las opciones de configuración de reunión que se pueden configurar.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Contenedor que almacena la configuración de movilidad global.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Esta clase contiene atributos que representan la configuración de un único servidor de supervisión.  <br/> |Nuevo en Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsoleto)  <br/> |Esta clase es un contenedor que representa una instancia de una ruta de menor coste a una puerta de enlace o a un conjunto de puertas de enlace. Todos los grupos de servidores Enterprise o servidores que ejecutan Standard Edition usan esta información para enrutar las llamadas realizadas a la red telefónica conmutada (RTC) de la manera más rentable.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsoleto)  <br/> |Esta clase es un contenedor para varias rutas de menor coste y no contiene ningún atributo propio.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Policies (obsoleto)  <br/> |Esta clase contiene varias clases de directiva de Lync Server y no tiene ningún atributo en sí.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Esta clase representa un único grupo de servidores de Skype Empresarial Server.  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |Esta clase contiene varios grupos de Skype Empresarial Server y no tiene ningún atributo en sí.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Esta clase representa el punto de control de servicio de un grupo de servidores. El atributo msRTCSIP-PrimaryHomeServer de los usuarios hospedados en un grupo de servidores apunta a una instancia de esta clase.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |Contenedor que almacena la configuración de presencia global.  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración del usuario que mantienen los servidores registradores SIP.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsoleto)  <br/> |Esta clase es un contenedor que representa una instancia de un uso de la ruta del teléfono. El uso de la clase del teléfono está compuesto de un campo de atributo y un campo de descripción. El campo de atributo define un tipo de uso. El campo de descripción permite a los administradores describir el uso de este atributo en la ruta del teléfono.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsoleto)  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-RouteUsage y no tiene ningún atributo propio.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que limitan y controlan el ámbito de los resultados de la búsqueda.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Esta clase representa un único servidor que ejecuta Skype Empresarial Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Esta clase contiene el contenedor de configuración global y los objetos msRTCSIP-Domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Esta clase contiene atributos que representan la configuración de un servidor de conferencia de confianza.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-TrustedMCU y no tiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Esta clase contiene varias clases msRTCSIP-TrustedProxy y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Esta clase es un contenedor que representa un servidor que ejecuta el servidor proxy. Se crea una instancia de esta clase al activar un nuevo servidor proxy en un equipo unido a AD DS.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Esta clase contiene atributos que representan la configuración de un servidor de confianza.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Esta clase es un contenedor que representa un servidor de confianza que es enrutable mediante una dirección URI de agente de usuario globalmente enrutable (GRUU). Se crea una instancia de esta clase cuando se activa un nuevo servidor de confianza para Skype Empresarial Server. Este servidor de confianza debe estar unido a un dominio de Active Directory.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Esta clase es un contenedor para varios servidores GRUU y no contiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Esta clase contiene atributos que representan la configuración de un componente web de confianza.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-TrustedWebComponentServer y no tiene ningún atributo propio.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene atributos relacionados con las comunicaciones unificadas.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-WebComponents  <br/> |Esta clase contiene el punto de control de servicio para Internet Information Services (IIS). Identifica a un servidor como servidor de componentes web.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Esta clase proporciona una asociación de un grupo de servidores concreto a los componentes web que el grupo de servidores usará.  <br/> |Nuevo en Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Esta clase auxiliar de msRTCSIP-WebComponents contiene los atributos que representan la configuración de los componentes web.  <br/> |Nuevo en Communications Server 2007.  <br/> |
   

