---
title: 'Lync Server 2013: requisitos de resistencia de sitios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1e8fb2cdbf2b9192411f74c5099930d8bd7d7a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Requisitos de resistencia de sitios de sucursal para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-25_

Este tema le ayudará a preparar a los usuarios para la resistencia del sitio de sucursal y la supervivencia del correo de voz, y también especifica los requisitos de hardware y software relevantes.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparación de usuarios de sucursal para la resistencia de sitios de sucursal

Preparar a los usuarios para la resistencia de sitios de sucursal mediante la configuración de su grupo de registrador como aplicación de sucursal con funciones de supervivencia (SBA) o servidor de sucursal con funciones de supervivencia.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Registrar asignaciones para usuarios de sucursal

Independientemente de la solución de resistencia de sitios de sucursal que elija, tendrá que asignar un registrador principal a cada usuario. Los usuarios de sitios de sucursal siempre deben registrarse con el registrador en el sitio de sucursal, independientemente de si el registrador reside en la aplicación de sucursal con funciones de supervivencia, en un servidor de sucursal con funciones de supervivencia o en un servidor de Lync Server 2013 Standard o Enterprise Edition independiente. Se necesita un registro de recursos de servicio (SRV) de sistema de nombres de dominio (DNS) para que un cliente pueda detectar su grupo de registradores. Si la aplicación de sucursal con funciones de supervivencia deja de estar disponible, este es el modo en que los clientes del sitio de sucursal detectarán automáticamente el registrador de reserva.

Si un sitio de sucursal no tiene un servidor DNS, hay dos formas alternativas de configurar la detección de la aplicación de sucursal con funciones de supervivencia o del servidor de sucursal con funciones de supervivencia:

  - Configure la opción de DHCP 120 en el servidor de protocolo de configuración dinámica de host (DHCP) del sitio de sucursal para que apunte al nombre de dominio completo (FQDN) de la aplicación de sucursal con funciones de supervivencia o del servidor de sucursal con funciones de supervivencia.

  - Configure la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia para responder a las consultas DHCP 120.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>Enrutamiento de voz para usuarios de sucursal

Le recomendamos que cree una directiva de protocolo de voz sobre IP (VoIP) de nivel de usuario independiente para los usuarios de un sitio de sucursal. Esta Directiva debe incluir una ruta principal que use la aplicación de sucursal con funciones de supervivencia o la puerta de enlace del servidor de sucursal, y una o varias rutas de copia de seguridad que usen un tronco con una puerta de enlace de red telefónica conmutada (RTC) en el sitio central. Si la ruta principal no está disponible, se usa en su lugar la ruta de la copia de seguridad que usa una o más puertas de enlace de sitio central. De este modo, independientemente de dónde esté registrado un usuario (en el registrador de sitios de sucursal o del grupo de registrador de reserva en el sitio central), la Directiva de VoIP del usuario siempre está en vigor. Esta es una consideración importante para los escenarios de conmutación por error. Por ejemplo, si necesita cambiar el nombre de la aplicación de sucursal con funciones de supervivencia o reconfigurar la aplicación de sucursal con funciones de supervivencia para conectarse a un grupo de registradores de copia de seguridad en el sitio central, debe mover a los usuarios del sitio de sucursal al sitio central durante el período de tiempo. (Para obtener más información sobre cómo cambiar el nombre o volver a configurar una aplicación de sucursal con funciones de supervivencia, consulte [Apéndice B: administración de una aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) en la documentación de implementación). Si esos usuarios no tienen directivas de VoIP en el nivel de usuario o planes de marcado de nivel de usuario, cuando los usuarios se mueven a otro sitio, las directivas VoIP de nivel de sitio y los planes de marcado de nivel de sitio del sitio central se aplican a los usuarios de forma predeterminada, en lugar de los planes de marcado y las directivas VoIP de nivel de sitio de sucursal. En este escenario, a menos que las directivas VoIP de nivel de sitio y los planes de marcado de nivel de sitio que usa el grupo de registrador de reserva también se apliquen a los usuarios del sitio de sucursal, se producirá un error en sus llamadas. Por ejemplo, si los usuarios de un sitio de sucursal ubicados en Japón se mueven a un sitio central en Redmond, un plan de marcado con reglas de normalización que anteponga + 1425 a todas las llamadas de 7 dígitos es improbable que las llamadas a dichos usuarios se traduzcan correctamente.

<div>


> [!IMPORTANT]  
> Al crear una ruta de copia de seguridad de sucursal, se recomienda agregar dos registros de uso de teléfono RTC a la Directiva de usuario de sucursal y asignar rutas independientes a cada uno de ellos. La primera, o principal, dirige las llamadas a la puerta de enlace asociada con la aplicación de sucursal con funciones de supervivencia (SBA) o el servidor de sucursal; la segunda, o la ruta de la copia de seguridad, dirige las llamadas a la puerta de enlace en el sitio central. En las llamadas directas, el servidor SBA o Branch intentará todas las rutas asignadas al primer registro de uso de RTC antes de intentar el segundo registro de uso.



</div>

Para ayudar a garantizar que las llamadas entrantes a los usuarios de sitios de sucursal llegarán a los usuarios cuando la puerta de enlace de sucursal o el componente de Windows del sitio de aplicación de sucursal con funciones de supervivencia no estén disponibles (lo que ocurriría, por ejemplo, si la aplicación de sucursal o sucursal con funciones de supervivencia la puerta de enlace no estaba disponible para el mantenimiento), cree una ruta de conmutación por error en la puerta de enlace (o trabaje con su proveedor de marcado hacia adentro directo) para redirigir las llamadas entrantes al grupo de registrador de reserva en el sitio central. Desde allí, las llamadas se enrutarán a través del vínculo WAN a los usuarios de la sucursal. Asegúrese de que la ruta traduce los números para que se ajusten a la puerta de enlace RTC o a otros formatos de número de teléfono aceptado del interlocutor del tronco. Para obtener información detallada sobre cómo crear una ruta de conmutación por error, consulte [configuración de una ruta de conmutación por error en Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Cree también planes de marcado de nivel de servicio para el tronco asociado con la puerta de enlace en el sitio de sucursal para normalizar las llamadas entrantes. Si tiene dos aplicaciones de sucursal con funciones de supervivencia en un sitio de sucursal, puede crear un plan de marcado de nivel de sitio para ambas, a menos que sea necesario un plan de nivel de servicio independiente para cada uno de ellos.

<div>


> [!NOTE]  
> Para tener en cuenta el consumo de recursos del sitio central por parte de los usuarios de sitios de sucursal que dependen del sitio central para la presencia, la Conferencia o la conmutación por error, se recomienda considerar a cada usuario del sitio de sucursal como si el usuario estuviera registrado en el sitio central. Actualmente no hay ningún límite en el número de usuarios del sitio de sucursal, incluidos los usuarios registrados con una aplicación de sucursal con funciones de supervivencia.



</div>

También se recomienda crear un plan de marcado de nivel de usuario y una directiva de voz y, a continuación, asignarlo a los usuarios del sitio de sucursal. Para obtener más información, consulte [crear un plan de marcado en Lync server 2013](lync-server-2013-create-a-dial-plan.md) y [crear la Directiva de enrutamiento VoIP para usuarios de sucursal en Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) en la documentación de implementación.

<div>

## <a name="routing-extension-numbers"></a>Números de extensión de enrutamiento

Al preparar planes de marcado y directivas de voz para usuarios de sitios de sucursal, asegúrese de incluir reglas de normalización y reglas de conversión que coinciden con las cadenas y el formato de número que se usan en el atributo msRTCSIP-line (o URI de línea), de modo que las llamadas de Lync 2013 a habilitada entre bifurcación los usuarios del sitio y los usuarios del sitio central se enrutarán correctamente, especialmente cuando las llamadas se deben desviar a través de la RTC porque el vínculo WAN no está disponible. Además, hay consideraciones especiales para los números marcados que incluyen números de extensión, en lugar de números de teléfono.

Reglas de normalización y traducciones que coinciden con los URI de línea que contienen un número de extensión, ya sea en exclusiva o además de un número de teléfono E. 164 completo, tienen requisitos adicionales. En esta sección se describen varios escenarios de ejemplo para enrutar las llamadas de URI de línea con un número de extensión.

Si su organización no tiene números de teléfono de marcado directo (DID) configurados para usuarios individuales y el URI de línea de cada usuario está configurado *solo* con un número de extensión, los usuarios internos pueden llamarse a otro marcando solo un número de extensión. Sin embargo, debe configurar las reglas de normalización que se pueden aplicar a las llamadas de un usuario de sitio de sucursal a un usuario del sitio central, que coinciden con los números de extensión.

En un escenario en el que el vínculo WAN entre un sitio de sucursal y un sitio central está disponible, las llamadas de los usuarios de sitios de sucursal a los usuarios de sitios centrales no requieren la regla de normalización de coincidencia para traducir el número, ya que la llamada no se enruta a través de la RTC. Por ejemplo:


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre de regla</th>
<th>Descripción</th>
<th>Modelo de número</th>
<th>Translation</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>No traduce números de 5 dígitos</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>$1</p></td>
<td><p>10001 no se traduce</p></td>
</tr>
</tbody>
</table>


También debe acomodar los números de extensión para escenarios específicos, como cuando el vínculo WAN entre un sitio de sucursal y el sitio central no está disponible y una llamada desde un sitio de sucursal debe enrutarse a través de la RTC. Durante una interrupción de la WAN, si un usuario del sitio de sucursal solo llama a un usuario del sitio central mediante la marcación de la extensión del usuario del sitio central, debe tener una regla de conversión de salida que agregue el número de teléfono completo del usuario del sitio central. Si el URI de línea de un usuario contiene el número de teléfono completo de la organización y el número de extensión único del usuario en lugar de un número de teléfono completo único para el usuario, debe tener una regla de conversión de salida que agregue el número de teléfono completo de la organización en su lugar. . Por ejemplo:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Modelo de coincidencia</th>
<th>Translation</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Traduce números de 5 dígitos al número de teléfono y la extensión de un usuario</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550123; EXT = $1</p></td>
<td><p>10001 se convierte en + 14255550123; ext = 10001</p></td>
</tr>
<tr class="even">
<td><p>Traduce números de 5 dígitos al número de teléfono de la organización y a la extensión de un usuario</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550100; EXT = $1</p></td>
<td><p>10001 se convierte en + 14255550100; ext = 10001</p></td>
</tr>
</tbody>
</table>


En este escenario, si el tronco del mismo nivel que controla el redireccionamiento a la RTC no admite números de extensión, la regla de conversión de salida también debe quitar el número de extensión. Por ejemplo:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Descripción</th>
<th>Modelo de coincidencia</th>
<th>Translation</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Quita la extensión de los números de teléfono con extensiones</p></td>
<td><p>^\+(\d *); EXT = (\d*) $</p></td>
<td><p>+ $1</p></td>
<td><p>+ 14255550123; ext = 10001 se convierte en + 14255550123</p></td>
</tr>
</tbody>
</table>


Si un vínculo WAN está o no disponible, si la organización no tiene los números realizados para usuarios individuales y el URI de línea de un usuario contiene el número de teléfono de la organización y el número de extensión único del usuario, debe configurar el URI de línea de número de teléfono de la organización con un número que es accesible para el tronco del mismo nivel o la puerta de enlace RTC en el sitio de sucursal. También debe configurar el URI de línea de número de teléfono de la organización para que incluya su propia extensión única para que las llamadas se enruten a ese número.

Para obtener información detallada sobre las llamadas realizadas desde un usuario del sitio central a un usuario de un sitio de sucursal cuando no está disponible el vínculo WAN entre los sitios, consulte "preparación para la supervivencia del correo de voz" más adelante en este tema. Para obtener más información sobre los planes de marcado y las reglas de normalización, incluidas otras reglas de ejemplo, consulte [planes de marcado y reglas de normalización en Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación de planeación y [configuración de planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md) en la documentación sobre implementación. Para obtener más información sobre las reglas de conversión de salida, consulte [reglas de traducción en Lync server 2013](lync-server-2013-translation-rules.md) en la documentación de planeación y [definición de reglas de conversión en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Preparación para la supervivencia del correo de voz

La mensajería unificada (MU) de Exchange suele instalarse únicamente en un sitio central y no en sitios de sucursal. Un autor de llamada debe poder dejar un mensaje de correo de voz, incluso si el vínculo WAN entre el sitio de sucursal y el sitio central no está disponible. Como resultado, la configuración del URI de línea para el número de teléfono del operador automático de mensajería unificada de Exchange que proporciona correo de voz para los usuarios del sitio de sucursal requiere consideraciones especiales, además de la Directiva de voz, el plan de marcado y las reglas de normalización que se aplican a ese correo de voz números.

Las aplicaciones de sucursal con funciones de supervivencia (las) y servidores de sucursal con funciones de supervivencia proporcionan supervivencia de correo de voz para usuarios de sucursal durante una interrupción de la WAN. En concreto, si está usando una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia y la WAN deja de estar disponible, el servidor de sucursal o el servidor de sucursal con funciones de supervivencia redirige las llamadas no respondidas a través de la RTC a la mensajería unificada de Exchange en el sitio central. Con una SBA o un servidor de sucursal con funciones de supervivencia, los usuarios también pueden recuperar los mensajes de correo de voz a través de la RTC durante una interrupción de la WAN. Por último, durante una interrupción de la WAN, la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia colocan en cola las notificaciones de llamadas perdidas y, después, las carga en el servidor de mensajería unificada de Exchange cuando se restaura la WAN. Para ayudar a garantizar que el reenrutamiento del correo de voz sea resistente, asegúrese de agregar una entrada para el FQDN del grupo de sitios central y una entrada para el FQDN del servidor perimetral al archivo de hosts en el servidor de sucursal con funciones de supervivencia. De lo contrario, la resolución de DNS puede agotar el tiempo de espera si no dispone de un servidor DNS en el sitio de sucursal.

Se recomiendan las siguientes configuraciones para la supervivencia del correo de voz para los usuarios de sitios de sucursal:

  - Un administrador de Microsoft Exchange debe configurar el operador automático de mensajería unificada (AA) de Exchange para que sólo acepte mensajes. Esta configuración deshabilita todas las demás funcionalidades genéricas, como la transferencia a un usuario o la transferencia a un operador, y limita el AA para que solo acepte mensajes. Como alternativa, el administrador de Exchange puede usar un AA genérico o un AA personalizado para enrutar la llamada a un operador.

  - El administrador de Lync Server debe tomar el número de teléfono y usarlo como el número de **operador automático de mensajería unificada de Exchange** en la configuración de reenrutamiento del correo de voz para la aplicación de sucursal o el servidor de sucursal con funciones de supervivencia.

  - El administrador de Lync Server debe obtener el número de teléfono de acceso de suscriptor de mensajería unificada de Exchange y usar ese número como el número de **acceso de suscriptor** en la configuración de reenrutamiento del correo de voz para la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.

  - El administrador de Lync Server debe configurar la mensajería unificada de Exchange para que solo se asocie un plan de marcado a todos los usuarios de la sucursal que necesiten obtener acceso al correo de voz durante una interrupción de la WAN.

  - Cuando el vínculo WAN no está disponible, las llamadas a los usuarios de un sitio de sucursal se pueden enrutar al buzón de voz de mensajería unificada (MU) de Exchange del usuario, pero solo si la Directiva de voz aplicada a la llamada especifica un número de teléfono de correo de voz que es único y no incluye una extensión números.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware y software para la resistencia de sitios de sucursal

Los requisitos de hardware y software varían en función de la solución de resistencia.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para aplicaciones de sucursal con funciones de supervivencia

El hardware y el software necesarios están integrados en la aplicación de sucursal con funciones de supervivencia. Sin embargo, también se recomienda que cada sitio de sucursal implemente un servidor DHCP para obtener las direcciones IP de cliente; de lo contrario, cuando expire la concesión DHCP, los clientes no tendrán conectividad IP.

Si los servidores DNS de empresa solo se encuentran en sitios centrales, los usuarios de sitios de sucursal no podrán conectarse a ellos durante una interrupción de la WAN y, por lo tanto, se producirá un error en la detección de Lync Server que usa el registro de recursos SRV (servicio (SRV) de DNS. Para garantizar el reenrutamiento de la solicitud durante una interrupción de la WAN, los registros DNS deben almacenarse en caché en el sitio de sucursal. Si el enrutador de sucursal lo admite, active el almacenamiento en caché de DNS. O bien, puede implementar un servidor DNS en la sucursal. Puede ser un servidor independiente o una versión de la aplicación de sucursal con funciones de supervivencia que admita capacidades DNS. Para obtener más información, póngase en contacto con su proveedor de aplicación de sucursal con funciones de supervivencia.

<div>


> [!NOTE]  
> No es necesario tener un controlador de dominio en un sitio de sucursal. La aplicación de sucursal con funciones de supervivencia autentica a los clientes con un certificado especial que envía al cliente en respuesta a la solicitud del certificado del cliente cuando inicia sesión.



</div>

Los clientes de Lync pueden detectar el servidor Lync mediante la opción DHCP 120 (opción registrador SIP). Esto se puede configurar de dos maneras:

  - Configure el servidor DHCP en el sitio de sucursal para responder a las consultas de DHCP 120, que devuelven el FQDN del registrador en la aplicación de sucursal con funciones de supervivencia o el servidor de sucursal con funciones de supervivencia.

  - Active el DHCP de Lync Server. Cuando esta opción está activada, el registrador de Lync Server responde a la opción DHCP 120 consultas. Tenga en cuenta que el registrador no responde a ninguna consulta DHCP distinta de las opciones de DHCP 120.

Además, en el caso de sitios de sucursal más grandes con varias subredes, los agentes de retransmisión DHCP deben estar habilitados para reenviar la opción DHCP 120 consultas al servidor DHCP (configuración 1) o al registrador (configuración 2).

Por último, los usuarios de sitios de sucursal deben estar configurados para telefonía IP empresarial y aprovisionados con un extremo de comunicaciones unificadas adecuado.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Requisitos para servidores de sucursal con funciones de supervivencia

Los requisitos de los servidores de sucursal con funciones de supervivencia son los mismos que para un servidor front-end. Para obtener más información, consulte [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación referente a la planeación.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Requisitos para implementaciones de sitio de sucursal de Lync Server a escala completa

Para obtener más información, consulte [determining Your Infrastructure Requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) en la documentación referente a la planeación.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

