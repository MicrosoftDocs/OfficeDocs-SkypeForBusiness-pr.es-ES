---
title: Clases y descripciones de esquema en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: En esta sección se describen todas las clases de esquema usadas por Skype empresarial Server.
ms.openlocfilehash: 6cb67c47c20ecb9cc6af79e51ebc05c332fd0bf3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815478"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Clases y descripciones de esquema en Skype empresarial Server
 
En esta sección se describen todas las clases de esquema usadas por Skype empresarial Server. 
  
## <a name="schema-classes-and-descriptions"></a>Clases y descripciones de esquema

|**Las**|**Descripción**|**Comentarios**|
|:-----|:-----|:-----|
|Destinatario de correo  <br/> |Destinatario de correo electrónico de mensajería unificada (UM) de Exchange.  <br/> |Esta clase auxiliar se comparte con la mensajería unificada de Exchange.  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |Esta clase es un contenedor para varios contactos de la aplicación y no contiene ningún atributo.  <br/> |Novedades de Microsoft Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServer  <br/> |Esta clase contiene la entrada del punto de control de servicio para una instancia de servicios de aplicaciones de comunicaciones unificadas (UCAS).  <br/> |Novedades de Office Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |Esta clase proporciona una asociación de un grupo específico a su servicio de aplicación.  <br/> |Novedades de Communications Server 2007 R2.  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-ApplicationServer contiene los atributos que representan la configuración de las instancias del servicio de aplicación.  <br/> |Novedades de Communications Server 2007 R2.  <br/> |
|msRTCSIP-Archive (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con el archivado.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-ArchivingServer (obsoleto)  <br/> |Esta clase representa un único servidor de archivado de mensajería instantánea. Se crea una instancia de esta clase cuando un equipo se activa como servidor de archivado de mensajería instantánea, como un equipo con el servicio de archivado de mensajería instantánea instalado.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |Esta clase es un contenedor para varias instancias de directorios de conferencia y no contiene ningún atributo.  <br/> |Novedades de Communications Server 2007 R2.  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |Esta clase contiene los atributos que representan la configuración de un directorio de conferencia específico.  <br/> |Novedades de Communications Server 2007 R2.  <br/> |
|msRTCSIP-coma  <br/> |Punto de control de servicio genérico (SCP) para especificar el equipo como servidor que ejecuta Skype empresarial Server.  <br/> |Novedades de Lync 2010.  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |Esta clase auxiliar contiene la configuración de un banco de la aplicación Web de Skype empresarial.  <br/> |Novedades de Communications Server 2007 R2.  <br/> |
|msRTCSIP-Domain  <br/> |Esta clase contiene atributos que definen los dominios configurados del registrador SIP.  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |Este contenedor de clase representa un servicio perimetral de acceso único. Como un servicio perimetral de acceso se implementa en la red perimetral y los clientes no suelen permitir el acceso a los servicios de dominio de Active Directory desde la red perimetral, las instancias de servicio perimetral de Access no se unen a la red de Active Directory de la intranet. Por lo tanto, los servidores proxy de acceso no se registran automáticamente en AD DS. El administrador debe configurar manualmente la existencia de cada instancia de servicio perimetral de acceso en AD DS.  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |Esta clase auxiliar de msRTCSIP-MCU mantiene atributos que representan la configuración de los servidores de conferencia.  <br/> |Novedades de Microsoft Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-MediationServer contiene los atributos que representan la configuración de los servidores de mediación.  <br/> |Novedades de Office Communications Server 2007.  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |Esta clase auxiliar de msRTCSIP-Server contiene los atributos que representan la configuración de los servidores SIP.  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con la Federación.  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |Esta clase contiene toda la configuración que se aplica en una implementación de Skype empresarial Server.  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (obsoleto)  <br/> |Esta clase representa una sola directiva de reunión de Office Communications Server.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Objeto de configuración de la topología global local.  <br/> |Novedades de Lync Server 2010.  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |Contenedor que contiene los objetos de configuración de la topología global.  <br/> |Novedades de Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalization  <br/> |Esta clase es un contenedor que representa una instancia de una regla de normalización de ubicación.  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |Esta clase la crea la aplicación de operador de conferencia y contiene los atributos usados para clasificar los números de teléfono de conferencia por región.  <br/> |Novedades de Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |Esta clase es un contenedor para varias instancias de asignaciones de contactos de ubicación y no contiene ningún atributo.  <br/> |Novedades de Communications Server 2007 R2.  <br/> |
|msRTCSIP-LocationProfile  <br/> |Esta clase es un contenedor que representa un perfil de ubicación específico.  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (obsoleto)  <br/> |Esta clase es un contenedor de varios perfiles de ubicación y no contiene ningún atributo.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-LocalNormalizations (obsoleto)  <br/> |Esta clase es un contenedor de varias reglas de normalización locales y no contiene ningún atributo.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-MCU  <br/> |Esta clase representa un único servidor de conferencia.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactories  <br/> |Esta clase contiene varias clases msRTCSIP-MCUFactory y no tiene atributos en sí.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactory  <br/> |Esta clase es un contenedor que representa un generador de servidor de conferencia para un único tipo de medio. Se crea una instancia de esta clase cuando se activa el primer servidor de conferencia para este tipo y proveedor en particular.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |Esta clase proporciona una asociación de un grupo específico a su fábrica de servidores de conferencias.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-MediationServer  <br/> |Esta clase contiene la entrada del punto de control de servicio para un servidor de mediación.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-Meeting (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración de reunión configurable.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Mobility  <br/> |Contenedor que almacena la configuración de movilidad global.  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |Esta clase contiene los atributos que representan la configuración de un único servidor de supervisión.  <br/> |Novedades de Communications Server 2007 R2.  <br/> |
|msRTCSIP-PhoneRoute (obsoleto)  <br/> |Esta clase es un contenedor que representa una instancia de una ruta de menor costo a una puerta de enlace o un conjunto de puertas de enlace. Esta información la usan todos los servidores o servidores de la versión Standard Edition para enrutar las llamadas salientes a la red de telefonía pública conmutada (RTC) de la manera más rentable.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-PhoneRoutes (obsoleto)  <br/> |Esta clase es un contenedor para varias rutas de menor costo y no contiene ningún atributo.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Policies (obsoleto)  <br/> |Esta clase contiene varias clases de directivas de Lync Server y no tiene ningún atributo en sí.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Pool  <br/> |Esta clase representa un único grupo de servidores de Skype empresarial.  <br/> |-  <br/> |
|msRTCSIP-pools  <br/> |Esta clase contiene varios grupos de servidores de Skype empresarial y no tiene ningún atributo en sí.  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |Esta clase representa el punto de control pointservice de control de servicio de un grupo. Los usuarios alojados en un grupo tienen el atributo msRTCSIP-PrimaryHomeServer apuntar a una instancia de esta clase.  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |Contenedor que almacena la configuración de presencia global.  <br/> |-  <br/> |
|msRTCSIP-registrar  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración de usuario que mantienen los servidores SIP del registrador.  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (obsoleto)  <br/> |Esta clase es un contenedor que representa una instancia del uso de una ruta telefónica. Una clase de uso de ruta de teléfono consta de un campo de atributo y un campo de descripción. El campo de atributo define un tipo de uso. El campo Descripción permite a los administradores describir el uso de este atributo en la ruta telefónica.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-RouteUsages (obsoleto)  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-RouteUsage y no tiene ningún atributo por sí mismo.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-Search  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene atributos que limitan y controlan el alcance de los resultados de la búsqueda.  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |Esta clase representa un único servidor que ejecuta Skype empresarial Server.  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |Esta clase contiene el contenedor configuración global y los objetos msRTCSIP-domain.  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |Esta clase contiene atributos que representan la configuración de un servidor de conferencia de confianza.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-TrustedMCU y no tiene ningún atributo por sí mismo.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxies  <br/> |Esta clase contiene varias clases msRTCSIP-TrustedProxy y no contiene ningún atributo.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedProxy  <br/> |Esta clase es un contenedor que representa un servidor que ejecuta Proxy Server. Se crea una instancia de esta clase al activar un nuevo servidor proxy en un equipo unido a AD DS.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServer  <br/> |Esta clase contiene atributos que representan la configuración de un servidor de confianza.  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |Esta clase es un contenedor que representa un servicio de confianza que se pueda enrutar mediante una dirección URI de un agente de usuario enrutable globalmente. Se crea una instancia de esta clase cuando se activa un nuevo servidor en el que confía Skype empresarial Server. Este servidor de confianza debe unirse a un dominio de Active Directory.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedServices  <br/> |Esta clase es un contenedor de varios servidores de GRUU y no contiene ningún atributo.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |Esta clase contiene atributos que representan la configuración de un componente Web de confianza.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |Esta clase contiene varias instancias de la clase msRTCSIP-TrustedWebComponentServer y no tiene ningún atributo por sí mismo.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-UnifiedCommunications (obsoleto)  <br/> |Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos relacionados con las comunicaciones unificadas.  <br/> |Obsoleto en Lync Server 2010.  <br/> |
|msRTCSIP-webcomponents  <br/> |Esta clase contiene el punto de control pointservice de control de servicio para Internet Information Server (IIS). Identifica un servidor como un servidor de componentes Web.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentsService  <br/> |Esta clase proporciona una asociación de un grupo específico a los componentes Web que usará el grupo.  <br/> |Novedades de Communications Server 2007.  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Esta clase auxiliar de msRTCSIP-webcomponents contiene los atributos que representan la configuración de los componentes Web.  <br/> |Novedades de Communications Server 2007.  <br/> |
   

