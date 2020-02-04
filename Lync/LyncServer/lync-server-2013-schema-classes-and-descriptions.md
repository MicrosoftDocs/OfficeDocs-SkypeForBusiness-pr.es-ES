---
title: 'Lync Server 2013: descripciones y clases de esquema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5080af0977457f5c4a75d2f121e75560b0f24524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Clases y descripciones de esquema en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En esta sección se describen todas las clases de esquema usadas por Lync Server 2013.

<div>

## <a name="schema-classes-and-descriptions"></a>Clases y descripciones de esquema


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Las</th>
<th>Descripción</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Destinatario de correo</p></td>
<td><p>Destinatario de correo electrónico de mensajería unificada (UM) de Exchange.</p></td>
<td><p>Esta clase auxiliar se comparte con la mensajería unificada de Exchange.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>Esta clase es un contenedor para varios contactos de la aplicación y no contiene ningún atributo.</p></td>
<td><p>Novedades de Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>Esta clase contiene la entrada del punto de control de servicio para una instancia de servicios de aplicaciones de comunicaciones unificadas (UCAS).</p></td>
<td><p>Novedades de Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>Esta clase proporciona una asociación de un grupo específico a su servicio de aplicación.</p></td>
<td><p>Novedades de Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-ApplicationServer contiene los atributos que representan la configuración de las instancias del servicio de aplicación.</p></td>
<td><p>Novedades de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (obsoleto)</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con el archivado.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (obsoleto)</p></td>
<td><p>Esta clase representa un único servidor de archivado de mensajería instantánea. Se crea una instancia de esta clase cuando un equipo se activa como servidor de archivado de mensajería instantánea, como un equipo con el servicio de archivado de mensajería instantánea instalado.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>Esta clase es un contenedor para varias instancias de directorios de conferencia y no contiene ningún atributo.</p></td>
<td><p>Novedades de Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>Esta clase contiene los atributos que representan la configuración de un directorio de conferencia específico.</p></td>
<td><p>Novedades de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-coma</p></td>
<td><p>Punto de control de servicio genérico (SCP) para especificar el equipo como servidor que ejecuta Lync Server.</p></td>
<td><p>Novedades de Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Esta clase auxiliar contiene la configuración de un banco de Microsoft Lync Web App.</p></td>
<td><p>Novedades de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>Esta clase contiene atributos que definen los dominios configurados del registrador SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Este contenedor de clase representa un servicio perimetral de acceso único. Como un servicio perimetral de acceso se implementa en la red perimetral y los clientes no suelen permitir el acceso a los servicios de dominio de Active Directory desde la red perimetral, las instancias de servicio perimetral de Access no se unen a la red de Active Directory de la intranet. Por lo tanto, los servidores proxy de acceso no se registran automáticamente en AD DS. El administrador debe configurar manualmente la existencia de cada instancia de servicio perimetral de acceso en AD DS.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-MCU mantiene atributos que representan la configuración de los servidores de conferencia.</p></td>
<td><p>Novedades de Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-MediationServer contiene los atributos que representan la configuración de los servidores de mediación.</p></td>
<td><p>Novedades de Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-Server contiene los atributos que representan la configuración de los servidores SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federation</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con la Federación.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Esta clase contiene toda la configuración que se aplica en una implementación de Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (obsoleto)</p></td>
<td><p>Esta clase representa una sola directiva de reunión de Office Communications Server.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>Objeto de configuración de la topología global local.</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Contenedor que contiene los objetos de configuración de la topología global.</p></td>
<td><p>Novedades de Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Esta clase es un contenedor que representa una instancia de una regla de normalización de ubicación.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Esta clase la crea la aplicación de operador de conferencia y contiene los atributos usados para clasificar los números de teléfono de conferencia por región.</p></td>
<td><p>Novedades de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>Esta clase es un contenedor para varias instancias de asignaciones de contactos de ubicación y no contiene ningún atributo.</p></td>
<td><p>Novedades de Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>Esta clase es un contenedor que representa un perfil de ubicación específico.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (obsoleto)</p></td>
<td><p>Esta clase es un contenedor de varios perfiles de ubicación y no contiene ningún atributo.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (obsoleto)</p></td>
<td><p>Esta clase es un contenedor de varias reglas de normalización locales y no contiene ningún atributo.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>Esta clase representa un único servidor de conferencia.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>Esta clase contiene varias clases msRTCSIP-MCUFactory y no tiene atributos en sí.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>Esta clase es un contenedor que representa un generador de servidor de conferencia para un único tipo de medio. Se crea una instancia de esta clase cuando se activa el primer servidor de conferencia para este tipo y proveedor en particular.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>Esta clase proporciona una asociación de un grupo específico a su fábrica de servidores de conferencias.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>Esta clase contiene la entrada del punto de control de servicio para un servidor de mediación.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (obsoleto)</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración de reunión configurable.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>Contenedor que almacena la configuración de movilidad global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Esta clase contiene los atributos que representan la configuración de un único servidor de supervisión.</p></td>
<td><p>Novedades de Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (obsoleto)</p></td>
<td><p>Esta clase es un contenedor que representa una instancia de una ruta de menor costo a una puerta de enlace o un conjunto de puertas de enlace. Esta información la usan todos los servidores o servidores de la versión Standard Edition para enrutar las llamadas salientes a la red de telefonía pública conmutada (RTC) de la manera más rentable.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (obsoleto)</p></td>
<td><p>Esta clase es un contenedor para varias rutas de menor costo y no contiene ningún atributo.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (obsoleto)</p></td>
<td><p>Esta clase contiene varias clases de directivas de Lync Server y no tiene ningún atributo en sí.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>Esta clase representa un único grupo de servidores de Lync.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-pools</p></td>
<td><p>Esta clase contiene varios grupos de servidores de Lync y no tiene ningún atributo en sí.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Esta clase representa el punto de control pointservice de control de servicio de un grupo. Los usuarios alojados en un grupo tienen el atributo msRTCSIP-PrimaryHomeServer apuntar a una instancia de esta clase.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Presence</p></td>
<td><p>Contenedor que almacena la configuración de presencia global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-registrar</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración de usuario que mantienen los servidores SIP del registrador.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (obsoleto)</p></td>
<td><p>Esta clase es un contenedor que representa una instancia del uso de una ruta telefónica. Una clase de uso de ruta de teléfono consta de un campo de atributo y un campo de descripción. El campo de atributo define un tipo de uso. El campo Descripción permite a los administradores describir el uso de este atributo en la ruta telefónica.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (obsoleto)</p></td>
<td><p>Esta clase contiene varias instancias de la clase msRTCSIP-RouteUsage y no tiene ningún atributo por sí mismo.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Search</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene atributos que limitan y controlan el alcance de los resultados de la búsqueda.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Esta clase representa un único servidor que ejecuta Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Service</p></td>
<td><p>Esta clase contiene el contenedor configuración global y los objetos msRTCSIP-domain.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>Esta clase contiene atributos que representan la configuración de un servidor de conferencia de confianza.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>Esta clase contiene varias instancias de la clase msRTCSIP-TrustedMCU y no tiene ningún atributo por sí mismo.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>Esta clase contiene varias clases msRTCSIP-TrustedProxy y no contiene ningún atributo.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>Esta clase es un contenedor que representa un servidor que ejecuta Proxy Server. Se crea una instancia de esta clase al activar un nuevo servidor proxy en un equipo unido a AD DS.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>Esta clase contiene atributos que representan la configuración de un servidor de confianza.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>Esta clase es un contenedor que representa un servicio de confianza que se pueda enrutar mediante una dirección URI de un agente de usuario enrutable globalmente. Se crea una instancia de esta clase cuando se activa un nuevo servidor en el que confía Lync Server. Este servidor de confianza debe unirse a un dominio de Active Directory.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>Esta clase es un contenedor de varios servidores de GRUU y no contiene ningún atributo.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Esta clase contiene atributos que representan la configuración de un componente Web de confianza.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>Esta clase contiene varias instancias de la clase msRTCSIP-TrustedWebComponentServer y no tiene ningún atributo por sí mismo.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (obsoleto)</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos relacionados con las comunicaciones unificadas.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-webcomponents</p></td>
<td><p>Esta clase contiene el punto de control pointservice de control de servicio para Internet Information Server (IIS). Identifica un servidor como un servidor de componentes Web.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>Esta clase proporciona una asociación de un grupo específico a los componentes Web que usará el grupo.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-webcomponents contiene los atributos que representan la configuración de los componentes Web.</p></td>
<td><p>Novedades de Communications Server 2007.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

