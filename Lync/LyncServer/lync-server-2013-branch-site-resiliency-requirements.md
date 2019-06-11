---
title: 'Lync Server 2013: Requisitos de resistencia de sitios de sucursal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ff969638f8c46abdd0ebcc8d11821a6a31b3c76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Requisitos de resistencia de sitios de sucursal para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-25_

Este tema le ayudará a preparar a los usuarios para la resiliencia de sitios de sucursales y la supervivencia del correo de voz, y también especifica los requisitos de hardware y software correspondientes.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Preparar usuarios de la sucursal para la resistencia a sitios de sucursales

Preparar a los usuarios para que tengan una resistencia al sitio de sucursal: Configure su grupo de registradores como el equipo de sucursales con capacidad de supervivencia (SBA) o servidor de sucursal con capacidad de supervivencia.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Registrar tareas para usuarios de la sucursal

Independientemente de la solución de resistencia que elija, tendrá que asignar un registrador principal a cada usuario. Los usuarios de un sitio de sucursal siempre deben registrarse con el registrador en el sitio de la sucursal, independientemente de si el registrador reside en el dispositivo de sucursal con la supervivencia, el servidor de sucursal con la versión superviviente o el servidor de Lync Server 2013 Standard o Enterprise Edition independiente. Se necesita un registro de recursos de servicio (SRV) de sistema de nombres de dominio (DNS) para que un cliente pueda descubrir su grupo de registradores. Si la aplicación de rama superviviente no está disponible, esta es la manera en que los clientes de sitios de sucursal detectarán automáticamente el registrador de copias de seguridad.

Si un sitio de sucursal no tiene un servidor DNS, hay dos formas alternativas de configurar el descubrimiento de la aplicación de sucursal que funciona con la supervivencia o el servidor de sucursal con la supervivencia:

  - Configure la opción de DHCP 120 en el servidor de protocolo de configuración dinámica de host (DHCP) del sitio de sucursal para que señale el nombre de dominio completo (FQDN) del equipo de sucursal o el servidor de sucursal que sea superviviente.

  - Configure la aplicación de rama superviviente o servidor de sucursal superviviente para responder a las consultas de 120 de DHCP.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>Enrutamiento de voz para usuarios de la sucursal

Le recomendamos que cree una directiva de protocolo de voz a través de Internet (VoIP) de nivel de usuario independiente para los usuarios de un sitio de sucursal. Esta Directiva debe incluir una ruta principal que use la aplicación de rama superviviente o la puerta de enlace de servidor de sucursal, y una o más rutas de copia de seguridad que usen un tronco con una puerta de enlace de red telefónica conmutada (RTC) en el sitio central. Si la ruta principal no está disponible, se usa en su lugar la ruta de la copia de seguridad que usa una o más puertas de enlace de sitio central. De esta manera, independientemente de dónde esté registrado un usuario, en el registrador de sitios de la sucursal o en el grupo de registro de la copia de seguridad del sitio central, la Directiva de VoIP del usuario siempre está activa. Esta es una consideración importante para escenarios de conmutación por error. Por ejemplo, si necesita cambiar el nombre de la aplicación de la rama que tiene la configuración o volver a configurar el dispositivo de rama que tiene la mayoría para conectarse a un grupo de registro de la copia de seguridad en el sitio central, debe mover los usuarios del sitio de la sucursal al sitio central durante el tiempo. (Para obtener detalles sobre cómo cambiar el nombre o la configuración de un dispositivo de sucursal que sea reviviente, consulte el [Apéndice B: administrar un dispositivo de sucursal con la supervivencia en Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) en la documentación de implementación). Si esos usuarios no tienen directivas de VoIP de nivel de usuario o planes de marcado de nivel de usuario, cuando se mueven los usuarios a otro sitio, las directivas de VoIP de nivel de sitio y los planes de marcado de nivel de sitio del sitio central se aplican a los usuarios de forma predeterminada, en lugar de la VoIP de nivel de sitio de sucursal directivas y planes de marcado,. En este caso, a menos que las directivas VoIP de nivel de sitio y los planes de marcado de nivel de sitio que usa el grupo de registro de la copia de seguridad también se apliquen a los usuarios de la sucursal, se producirá un error en sus llamadas. Por ejemplo, si los usuarios de un sitio de sucursal ubicado en Japón se mueven a un sitio central de Redmond, es improbable que un plan de marcado con reglas de normalización que antepongan + 1425 a todas las llamadas de 7 dígitos no sea la adecuada para traducir las llamadas de esos usuarios.

<div>


> [!IMPORTANT]  
> Al crear una ruta de copia de seguridad de una sucursal, le recomendamos que agregue dos registros de uso de teléfono RTC a la Directiva de usuario de la sucursal y asigne rutas distintas a cada uno de ellos. La primera ruta, o la principal, dirigirían llamadas a la puerta de enlace asociada con el dispositivo de rama con la supervivencia (SBA) o el servidor de sucursal; la ruta del segundo, o de la copia de seguridad, dirigirá las llamadas a la puerta de enlace en el sitio central. En las llamadas directas, el servidor de SBA o de sucursal intentará todas las rutas asignadas al primer registro de uso de RTC antes de intentar el segundo registro de uso.



</div>

Para asegurarse de que las llamadas entrantes a los usuarios de un sitio de sucursal llegarán a esos usuarios cuando la puerta de enlace o el componente de Windows del sitio de la aplicación de sucursal superviviente no esté disponible (esto sucede, por ejemplo, si la sucursal o rama superviviente la puerta de enlace estuvo fuera de servicio por el mantenimiento), cree una ruta de conmutación por error en la puerta de enlace (o en el proveedor de marcado interno directo) para redirigir las llamadas entrantes al grupo de registro de la copia de seguridad en el sitio central. Desde allí, las llamadas se redirigirán a través del vínculo WAN a los usuarios de la sucursal. Asegúrese de que la ruta traduce los números para que cumplan con la puerta de enlace PSTN u otros formatos de número de teléfono aceptados del interlocutor del mismo nivel. Para obtener detalles sobre cómo crear una ruta de conmutación por error, vea [configurar una ruta de conmutación por error en Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Además, cree planes de marcado de nivel de servicio para el tronco asociado a la puerta de enlace del sitio de la sucursal para normalizar las llamadas entrantes. Si tiene dos dispositivos de sucursal con la supervivencia en un sitio de sucursal, puede crear un plan de marcado de nivel de sitio para ambos, a menos que sea necesario un plan de nivel de servicio diferente para cada uno.

<div>


> [!NOTE]  
> Para tener en cuenta el consumo de recursos del sitio central por parte de los usuarios de un sitio de sucursal que dependen del sitio central para la presencia, la Conferencia o la conmutación por error, le recomendamos que considere a cada usuario del sitio de sucursal como si el usuario se hubiera registrado con el sitio central. Por el momento, no hay límites en el número de usuarios de la sucursal, incluidos los registrados en un equipo de sucursales con la supervivencia.



</div>

También le recomendamos crear un plan de marcado y una directiva de voz de nivel de usuario y, a continuación, asignarla a los usuarios de un sitio de sucursal. Para obtener más información, consulte [crear un plan de marcado en Lync server 2013](lync-server-2013-create-a-dial-plan.md) y [crear la Directiva de enrutamiento de VoIP para usuarios de sucursal en Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) en la documentación de implementación.

<div>

## <a name="routing-extension-numbers"></a>Números de extensión de enrutamiento

Al preparar planes de marcado y directivas de voz para usuarios de sitios de sucursal, asegúrese de incluir reglas de normalización y reglas de traducción que coincidan con las cadenas y el formato de número que se usan en el atributo msRTCSIP-line (o URI de línea), para que las llamadas de Lync 2013 entre sucursales los usuarios del sitio y del sitio central se enrutarán correctamente, especialmente cuando las llamadas se deben desviar a través de la RTC porque el vínculo WAN no está disponible. Además, existen consideraciones especiales para los números marcados que incluyen números de extensión, en lugar de números de teléfono.

Reglas de normalización y traducciones que coinciden con los identificadores URI que contienen un número de extensión, ya sea de forma exclusiva o adicional a un número de teléfono E. 164 completo, tienen requisitos adicionales. En esta sección se describen varios escenarios de ejemplo para enrutar llamadas de identificadores URI con un número de extensión.

Si su organización no tiene números de teléfono de marcado directo (sí) configurados para usuarios individuales y el URI de línea de cada usuario ** se configura con un número de extensión, los usuarios internos pueden llamarse solo por un número de extensión. Sin embargo, debe configurar las reglas de normalización que se pueden aplicar a las llamadas de un usuario del sitio de la sucursal a un usuario del sitio central, que coincidan con los números de extensión.

En un escenario en el que está disponible el vínculo WAN entre un sitio de sucursal y un sitio central, las llamadas de usuarios de sitios de sucursales a usuarios de sitios centrales no requieren la regla de normalización correspondiente para traducir el número, porque la llamada no se enruta a través de la RTC. Por ejemplo:


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
<th>Nombre de la regla</th>
<th>Descripción</th>
<th>Patrón de números</th>
<th>Conversión</th>
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


También debe acomodar los números de extensión para escenarios específicos, como cuando el vínculo WAN entre un sitio de sucursal y el sitio central no está disponible y una llamada de un sitio de sucursal debe enrutarse a través de la RTC. Durante una interrupción de la WAN, si un usuario de un sitio de sucursal solo llama a un usuario del sitio central marcando la extensión del usuario del sitio central, debe tener una regla de traducción de salida que agregue el número de teléfono completo del usuario del sitio central. Si el identificador URI de línea de un usuario contiene el número de teléfono completo de su organización y el número de extensión único del usuario, en lugar de un número de teléfono completo que es exclusivo para el usuario, debe tener una regla de traducción de salida que agregue el número de teléfono completo de su organización en su lugar. . Por ejemplo:


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
<th>Patrón de coincidencia</th>
<th>Conversión</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Traduce números de 5 dígitos al número de teléfono y a la extensión de un usuario.</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550123; EXT = $1</p></td>
<td><p>10001 se traduce a + 14255550123; ext = 10001</p></td>
</tr>
<tr class="even">
<td><p>Traduce números de 5 dígitos al número de teléfono de la organización y a la extensión de un usuario</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550100; EXT = $1</p></td>
<td><p>10001 se traduce a + 14255550100; ext = 10001</p></td>
</tr>
</tbody>
</table>


En este caso, si el punto de conexión del mismo nivel que controla el redireccionamiento a la RTC no admite números de extensión, la regla de traducción saliente también debe quitar el número de extensión. Por ejemplo:


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
<th>Patrón de coincidencia</th>
<th>Conversión</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Quita la extensión de los números de teléfono con extensiones</p></td>
<td><p>^\+(\d *); EXT = (\d*) $</p></td>
<td><p>+$1</p></td>
<td><p>+ 14255550123; ext = 10001 se traduce a + 14255550123</p></td>
</tr>
</tbody>
</table>


Si un vínculo WAN está disponible o no, si su organización no tiene números realizados para usuarios individuales y el URI de línea para un usuario contiene el número de teléfono de la organización y el número de extensión exclusivo del usuario, debe configurar el URI de la línea del número de teléfono de la organización con un número al que se puede alcanzar la puerta de enlace troncal o la puerta de enlace RTC en el sitio de la sucursal. También debe configurar el URI de la línea de número de teléfono de su organización para que incluya su propia extensión exclusiva para que las llamadas se enruten a ese número.

Para más información sobre las llamadas de un usuario del sitio central a un usuario de un sitio de sucursal cuando el vínculo WAN entre los sitios no está disponible, consulte "prepararse para la supervivencia del correo de voz" más adelante en este tema. Para obtener más información sobre los planes de marcado y las reglas de normalización, incluidas otras reglas de ejemplo, consulte [planes de marcado y reglas de normalización en Lync server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación de planeación y [configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md) en la implementación documentación. Para obtener detalles sobre las reglas de traducción salientes, vea [reglas de traducción en Lync server 2013](lync-server-2013-translation-rules.md) en la documentación de planeación y [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Prepararse para la supervivencia del correo de voz

La mensajería unificada de Exchange (UM) suele instalarse únicamente en un sitio central y no en sitios de sucursales. La persona que llama debe poder dejar un mensaje de correo de voz, incluso si el vínculo WAN entre el sitio de la sucursal y el sitio central no está disponible. Como resultado, la configuración del URI de línea para el operador automático de mensajería unificada de Exchange que proporciona el correo de voz para los usuarios del sitio de sucursal requiere consideraciones especiales, además de la Directiva de voz, el plan de marcado y las reglas de normalización que se aplican a ese correo de voz. mero.

Los dispositivos de sucursal (SBAs) y los servidores de sucursales supervivientes proporcionan la supervivencia del correo de voz para los usuarios de la sucursal durante una interrupción de la WAN. En concreto, si está usando un dispositivo de sucursal o un servidor de sucursal supervivientes y la WAN deja de estar disponible, el servidor de sucursal de SBA o de supervivencia redirige las llamadas no contestadas a través de la RTC a la mensajería unificada de Exchange en el sitio central. Con un servidor de sucursal SBA o que sea reviviente, los usuarios también pueden recuperar los mensajes de correo de voz a través de la RTC durante una interrupción de WAN. Por último, durante una interrupción de la WAN, el equipo de sucursales que puede ser superviviente o el servidor de sucursal con la supervivencia, notifica y luego los carga en el servidor de mensajería unificada de Exchange cuando se restaura la WAN. Para ayudar a garantizar que el redireccionamiento del correo de voz sea resistente, asegúrese de agregar una entrada para el FQDN del grupo de sitios central y una entrada para el FQDN del servidor perimetral al archivo hosts en el servidor de sucursal con la supervivencia. En caso contrario, la resolución DNS puede agotar el tiempo si no tiene un servidor DNS en el sitio de la sucursal.

Recomendamos las siguientes configuraciones para los usuarios de sitios de sucursal de la supervivencia del correo de voz:

  - Un administrador de Microsoft Exchange debe configurar el operador automático de mensajería unificada de Exchange (AA) para que solo acepte mensajes. Esta configuración deshabilita todas las demás funcionalidades genéricas, como la transferencia a un usuario o la transferencia a un operador, y limita el AA para aceptar solo los mensajes. Como alternativa, el administrador de Exchange puede usar un AA genérico o un AA personalizado para enrutar la llamada a un operador.

  - El administrador de Lync Server debe tomar el número de teléfono AA y usarlo como el número de **operador automático de mensajería unificada de Exchange** en la configuración de redireccionamiento del correo de voz para el dispositivo de sucursal o el servidor de sucursal.

  - El administrador de Lync Server debe obtener el número de teléfono de acceso a la mensajería unificada de Exchange y usar ese número como el número de **acceso** del suscriptor en la configuración de redireccionamiento del correo de voz para el equipo de la sucursal o el servidor de sucursal con la supervivencia.

  - El administrador de Lync Server debe configurar la mensajería unificada de Exchange para que solo se asocie un plan de marcado a todos los usuarios de la sucursal que necesiten acceso al correo de voz durante una interrupción de la WAN.

  - Cuando el vínculo WAN no está disponible, las llamadas a usuarios de un sitio de sucursal se pueden enrutar al buzón de voz de mensajería unificada (UM) del usuario, pero solo si la Directiva de voz aplicada a la llamada especifica un número de teléfono de correo de voz que es único y no incluye una extensión mero.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Requisitos de hardware y software para la resistencia a sitios de sucursal

Los requisitos de hardware y software varían según la solución de resistencia.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Requisitos para las sucursales con disvivientes

El hardware y el software necesarios están incorporados en el equipo con la sucursal de supervivencia. Sin embargo, también recomendamos que cada sitio de la sucursal implemente un servidor DHCP para obtener las direcciones IP de los clientes; de lo contrario, cuando la concesión DHCP expira, los clientes no tendrán conectividad IP.

Si los servidores DNS empresariales solo se encuentran en sitios centrales, los usuarios del sitio de la sucursal no podrán conectarse a ellos durante una interrupción de WAN y, por lo tanto, se producirá un error en la detección de Lync Server que usa el registro de recursos SRV (SRV) de DNS. Para asegurar el redireccionamiento de la solicitud durante una interrupción de WAN, los registros DNS deben almacenarse en caché en el sitio de la sucursal. Si el enrutador de bifurcación lo admite, active el almacenamiento en caché de DNS. O bien, puede implementar un servidor DNS en la sucursal. Puede ser un servidor independiente o una versión de la aplicación de la rama superviviente que admita capacidades DNS. Para obtener más información, póngase en contacto con el proveedor de su equipo de sucursales.

<div>


> [!NOTE]  
> No es necesario tener un controlador de dominio en un sitio de sucursal. El dispositivo de sucursal con supervivencia autentica los clientes mediante un certificado especial que envía al cliente en respuesta a la solicitud de certificado del cliente cuando inicia sesión.



</div>

Los clientes de Lync pueden descubrir el servidor de Lync mediante la opción DHCP 120 (opción de registrador SIP). Puede configurarse de dos maneras:

  - Configure el servidor DHCP en el sitio de la sucursal para responder a las consultas de DHCP 120, que devolverán el FQDN del registrador en la sucursal superviviente o en el servidor de sucursal superviviente.

  - Active el DHCP de Lync Server. Cuando esta opción está activada, el registrador de Lync Server responde a la opción DHCP 120 consultas. Tenga en cuenta que el registrador no responde a ninguna consulta DHCP distinta de las opciones de DHCP 120.

Además, en el caso de sitios de sucursales más grandes que tienen varias subredes, los agentes de retransmisión DHCP deben estar habilitados para reenviar las consultas de la opción DHCP 120 al servidor DHCP (configuración 1) o al registrador (configuración 2).

Por último, los usuarios de sitios de sucursal deben estar configurados para telefonía IP empresarial y aprovisionar un extremo de comunicaciones unificado adecuado.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Requisitos para servidores de sucursal revivientes

Los requisitos para servidores de sucursal revivientes son los mismos que los de un servidor front-end. Para obtener más información, vea [plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación de planeación.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Requisitos para implementaciones de sitio de Lync Server de escala completa

Para obtener más información, consulte [determinar los requisitos de infraestructura para Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) en la documentación de planeación.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

