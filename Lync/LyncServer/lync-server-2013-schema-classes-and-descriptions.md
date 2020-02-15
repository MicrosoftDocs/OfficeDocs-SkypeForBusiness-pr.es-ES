---
title: 'Lync Server 2013: clases de esquema y descripciones'
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
ms.openlocfilehash: 3063e0dd6288f4b9248c93de57a6182a7ab20a8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Clases de esquema y descripciones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-30_

En esta sección se describen todas las clases de esquema que usa Lync Server 2013.

<div>

## <a name="schema-classes-and-descriptions"></a>Clases de esquema y descripciones


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Clase</th>
<th>Descripción</th>
<th>Comentarios</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>Destinatario de correo electrónico de mensajería unificada (MU) de Exchange.</p></td>
<td><p>Esta clase auxiliar se comparte con la mensajería unificada de Exchange.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>Esta clase es un contenedor para varios contactos de aplicación y no contiene ningún atributo propio.</p></td>
<td><p>Novedad en Microsoft Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>Esta clase contiene la entrada del punto de control de servicio de una instancia de los servicios de aplicación de comunicaciones unificadas (UCAS).</p></td>
<td><p>Nuevo en Office Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>Esta clase proporciona una asociación de un grupo de servidores específico a su servicio de aplicación.</p></td>
<td><p>Nuevo en Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-ApplicationServer contiene los atributos que representan la configuración de las instancias del servicio de aplicación.</p></td>
<td><p>Nuevo en Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (obsoleto)</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con el archivado.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (obsoleto)</p></td>
<td><p>Esta clase representa un único servidor de archivado de mensajería instantánea. Cuando un equipo se activa como servidor de archivado de mensajería instantánea (por ejemplo, un equipo que tiene instalado el servicio de archivado de mensajería instantánea), se crea una instancia de esta clase.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>Esta clase es un contenedor para varias instancias de directorios de conferencia y no contiene ningún atributo propio.</p></td>
<td><p>Nuevo en Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>Esta clase contiene los atributos que representan la configuración de un directorio de conferencia específico.</p></td>
<td><p>Nuevo en Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-pines</p></td>
<td><p>Punto de control de servicio (SCP) genérico para especificar el equipo como un servidor que ejecuta Lync Server.</p></td>
<td><p>Nuevo en Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Esta clase auxiliar contiene la configuración de un banco de Microsoft Lync Web App.</p></td>
<td><p>Nuevo en Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>Esta clase contiene atributos que definen los dominios configurados del registrador SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>Este contenedor de clase representa un servicio perimetral de acceso único. Como un servicio perimetral de acceso se implementa en la red perimetral y los clientes no suelen permitir el acceso de servicios de dominio de Active Directory desde la red perimetral, las instancias del servicio perimetral de acceso no se unen a la red de Active Directory de la intranet. En consecuencia, los servidores proxy de acceso no se registran automáticamente en AD DS. El administrador debe configurar manualmente la existencia de cada instancia del servicio perimetral de acceso en AD DS.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-MCU contiene los atributos que representan la configuración de los servidores de conferencia.</p></td>
<td><p>Nuevo en Microsoft Office Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-MediationServer contiene los atributos que representan la configuración de los servidores de mediación.</p></td>
<td><p>Nuevo en Office Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-Server contiene los atributos que representan la configuración de los servidores SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federation</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene toda la configuración relacionada con la federación.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Esta clase contiene toda la configuración que se aplica en una implementación de Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (obsoleto)</p></td>
<td><p>Esta clase representa una única directiva de reunión de Office Communications Server.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>El objeto de configuración de la topología global local.</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>Contenedor para abarcar los objetos de configuración de topología global.</p></td>
<td><p>Nuevo en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>Esta clase es un contenedor que representa una instancia de una regla de normalización de ubicación.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>Esta clase se crea mediante la aplicación operador de conferencia y contiene los atributos usados para clasificar los números de teléfono de conferencia por región.</p></td>
<td><p>Nuevo en Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>Esta clase es un contenedor para varias instancias de asignaciones de contacto de ubicación y no contiene ningún atributo propio.</p></td>
<td><p>Nuevo en Communications Server 2007 R2.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>Esta clase es un contenedor que representa un perfil de ubicación concreto.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (obsoleto)</p></td>
<td><p>Esta clase es un contenedor para varios perfiles de ubicación y no contiene ningún atributo propio.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (obsoleto)</p></td>
<td><p>Esta clase es un contenedor para varias reglas de normalización local y no contiene ningún atributo propio.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>Esta clase representa un único servidor de conferencia.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>Esta clase contiene varias clases msRTCSIP-MCUFactory y no tiene atributos propios.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>Esta clase es un contenedor que representa una fábrica de servidores de conferencia de un solo tipo de medio. Se crea una instancia de esta clase cuando se activa el primer servidor de conferencia para este tipo y proveedor.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>Esta clase proporciona una asociación de un grupo de servidores específico con su fábrica de servidores de conferencia.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>Esta clase contiene la entrada del punto de control de servicio de un servidor de mediación.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (obsoleto)</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene atributos que representan las opciones de configuración de reunión que se pueden configurar.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>Contenedor que almacena la configuración de movilidad global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>Esta clase contiene atributos que representan la configuración de un único servidor de supervisión.</p></td>
<td><p>Nuevo en Communications Server 2007 R2.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (obsoleto)</p></td>
<td><p>Esta clase es un contenedor que representa una instancia de una ruta de menor coste a una puerta de enlace o a un conjunto de puertas de enlace. Todos los grupos de servidores Enterprise o servidores que ejecutan Standard Edition usan esta información para enrutar las llamadas realizadas a la red telefónica conmutada (RTC) de la manera más rentable.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (obsoleto)</p></td>
<td><p>Esta clase es un contenedor para varias rutas de menor coste y no contiene ningún atributo propio.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (obsoleto)</p></td>
<td><p>Esta clase contiene varias clases de directivas de Lync Server y no tiene ningún atributo propio.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>Esta clase representa un único grupo de Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-pools</p></td>
<td><p>Esta clase contiene varios grupos de Lync Server y no tiene ningún atributo propio.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>Esta clase representa el punto de control de servicio de un grupo de servidores. El atributo msRTCSIP-PrimaryHomeServer de los usuarios hospedados en un grupo de servidores apunta a una instancia de esta clase.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Presence</p></td>
<td><p>Contenedor que almacena la configuración de presencia global.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-registrar</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que representan la configuración del usuario que mantienen los servidores registradores SIP.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (obsoleto)</p></td>
<td><p>Esta clase es un contenedor que representa una instancia de un uso de la ruta del teléfono. El uso de la clase del teléfono está compuesto de un campo de atributo y un campo de descripción. El campo de atributo define un tipo de uso. El campo de descripción permite a los administradores describir el uso de este atributo en la ruta del teléfono.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (obsoleto)</p></td>
<td><p>Esta clase contiene varias instancias de la clase msRTCSIP-RouteUsage y no tiene ningún atributo propio.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Search</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene los atributos que limitan y controlan el ámbito de los resultados de la búsqueda.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Esta clase representa un único servidor que ejecuta Lync Server.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Service</p></td>
<td><p>Esta clase contiene el contenedor de configuración global y los objetos msRTCSIP-Domain.</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>Esta clase contiene atributos que representan la configuración de un servidor de conferencia de confianza.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>Esta clase contiene varias instancias de la clase msRTCSIP-TrustedMCU y no tiene ningún atributo propio.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>Esta clase contiene varias clases msRTCSIP-TrustedProxy y no contiene ningún atributo propio.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>Esta clase es un contenedor que representa un servidor que ejecuta el servidor proxy. Se crea una instancia de esta clase al activar un nuevo servidor proxy en un equipo unido a AD DS.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>Esta clase contiene atributos que representan la configuración de un servidor de confianza.</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>Esta clase es un contenedor que representa un servidor de confianza que es enrutable mediante una dirección URI de agente de usuario globalmente enrutable (GRUU). Se crea una instancia de esta clase cuando se activa un nuevo servidor en el que se confía en Lync Server. Este servidor de confianza debe estar unido a un dominio de Active Directory.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>Esta clase es un contenedor para varios servidores GRUU y no contiene ningún atributo propio.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>Esta clase contiene atributos que representan la configuración de un componente web de confianza.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-confianza</p></td>
<td><p>Esta clase contiene varias instancias de la clase msRTCSIP-TrustedWebComponentServer y no tiene ningún atributo propio.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (obsoleto)</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-GlobalContainer contiene atributos relacionados con las comunicaciones unificadas.</p></td>
<td><p>Obsoleto en Lync Server 2010.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-webcomponents</p></td>
<td><p>Esta clase contiene el punto de control de servicio para Internet Information Services (IIS). Identifica a un servidor como servidor de componentes web.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>Esta clase proporciona una asociación de un grupo de servidores concreto a los componentes web que el grupo de servidores usará.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Esta clase auxiliar de msRTCSIP-WebComponents contiene los atributos que representan la configuración de los componentes web.</p></td>
<td><p>Nuevo en Communications Server 2007.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

