---
title: "Lync Server 2013 : Conf. requise pour la résistance des sites de succursale"
TOCTitle: Requisitos de resistencia de sitios de sucursal
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48276191
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de resistencia de sitios de sucursal para Lync Server 2013

 

_**Última modificación del tema:** 2015-03-09_

En este tema se proporciona información sobre cómo preparar a los usuarios para la resistencia de sitios de sucursal y para la supervivencia de correo de voz, asimismo, se especifican los requisitos de hardware y software pertinentes.

## Preparación de los usuarios de sucursal para la resistencia de sitios de sucursal

Prepare a los usuarios para la resistencia de sitios de sucursal mediante la configuración de su grupo de registrador como Aplicación de sucursal con funciones de supervivencia (SBA) o Servidor de sucursal con funciones de supervivencia.

## Asignaciones de registrador para usuarios de sucursal

Sea cual sea la solución de resistencia de sitios de sucursal que elija, deberá asignar un registrador principal a cada usuario. Los usuarios de sitios de sucursal deben registrarse siempre con el registrador en el sitio de sucursal, independientemente de si el registrador se encuentra en la Aplicación de sucursal con funciones de supervivencia, en el Servidor de sucursal con funciones de supervivencia o en el Lync Server 2013 Standard o Enterprise Edition Server independiente. Se necesita un registro de servicio (SRV) de sistema de nombres de dominio (DNS) para que los clientes puedan detectar su grupo de servidores de registrador. Si la Aplicación de sucursal con funciones de supervivencia deja de estar disponible, este es el método que usarán los clientes de sucursales para detectar automáticamente el registrador de reserva.

Si un sitio de sucursal no dispone de un servidor DNS, existen dos métodos alternativos para configurar la detección de la Aplicación de sucursal con funciones de supervivencia o del Servidor de sucursal con funciones de supervivencia:

  - Configurar la opción de DHCP 120 en el servidor DHCP del sitio de sucursal para que apunte al nombre de dominio completo (FQDN) de Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia.

  - Configurar Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia para que responda a las consultas de DHCP 120.

## Enrutamiento de voz para usuarios de sucursal

Se recomienda crear otra directiva de VoIP a nivel de usuario para usuarios de un sitio de sucursal. Esta directiva debe incluir una ruta principal que utilice la Aplicación de sucursal con funciones de supervivencia o una pasarela de servidor de sucursal y una o más rutas secundarias que utilicen una puerta de enlace RTC del sitio central. Si la ruta principal no está disponible, se usará en su lugar la ruta de reserva que usa una o más puertas de enlace de sitio central. De esta forma, independientemente de dónde esté registrado el usuario, ya sea en el registrador del sitio de sucursal o en el grupo de servidores de registrador de reserva en el sitio central, siempre estará en vigor la directiva VoIP del usuario. Esta consideración es importante en los escenarios de conmutación por error. Por ejemplo, si necesita cambiar el nombre de Aplicación de sucursal con funciones de supervivencia o volver a configurar la Aplicación de sucursal con funciones de supervivencia para conectarse a un grupo de registradores de reserva en el sitio central, tendrá que trasladar a los usuarios del sitio de sucursal al sitio central mientras tanto. (Si desea información sobre cómo cambiar el nombre de Aplicación de sucursal con funciones de supervivencia o cómo reconfigurarla, vea [Apéndice B: Administración de una aplicación de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) en la documentación sobre implementación). Si estos usuarios no tienen directivas de VoIP a nivel de usuario o planes de marcado a nivel de usuario, cuando los usuarios se trasladen a otro sitio, se aplicarán, de manera predeterminada, las directivas VoIP de nivel de sitio y los planes de marcado de nivel de sitio del sitio central, en lugar de las directivas VoIP y los planes de marcado de nivel de usuario. En este escenario, las llamadas causarían errores, a menos que las directivas VoIP y los planes de marcado de nivel de sitio que usa el grupo de registradores de reserva también puedan aplicarse a los usuarios del sitio de sucursal. Por ejemplo, si los usuarios de un sitio de sucursal localizados en Japón se trasladan a un sitio de central en Redmond, es poco probable que un plan de marcado con reglas de normalización que añada +1425 antes de todas las llamadas de 7 dígitos traduzca correctamente las llamadas de estos usuarios.

> [!IMPORTANT]  
> Cuando se crea una ruta de reserva de sucursal, se recomienda agregar dos registros de uso de teléfono de RTC a la directiva de usuario de sucursal y asignar rutas distintas a cada uno de ellos. La primera ruta, o ruta principal, dirigirá las llamadas a la puerta de enlace asociada con el Aplicación de sucursal con funciones de supervivencia (SBA) o servidor de sucursal; la segunda ruta, o ruta de reserva, dirigirá las llamadas a la puerta de enlace del sitio central. Al dirigir las llamadas, el SBA o servidor de sucursal probará todas las rutas asignadas al primer registro de uso de RTC antes de probar el segundo registro de uso.



Para ayudar a garantizar que los usuarios de sucursales reciban las llamadas entrantes cuando la puerta de enlace de sitio de sucursal o el componente de Windows del sitio de la Aplicación de sucursal con funciones de supervivencia no están disponibles (lo cual ocurriría, por ejemplo, si la Aplicación de sucursal con funciones de supervivencia o la puerta de enlace de la sucursal estuvieran inactivas por la realización de tareas de mantenimiento), cree una ruta de conmutación por error en la puerta de enlace o trabaje con su proveedor de llamada directa (DID) para redirigir las llamadas entrantes al grupo de registradores de reserva en el sitio central. Desde este, las llamadas se enrutarán a través del vínculo WAN a los usuarios de sucursales. Compruebe que la ruta traduce los números de acuerdo con las normas de la puerta de enlace RTC u otros formatos de número de teléfono aceptados por otros pares de tronco. Si desea información sobre cómo crear una ruta de conmutación por error, consulte [Configurar una ruta de conmutación por error en Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Cree también planes de marcado a nivel de servicio para el tronco asociado con la puerta de enlace del sitio de sucursal con el fin de normalizar las llamadas entrantes. Si tiene dos Aplicaciones de sucursal con funciones de supervivencia con funciones de supervivencia en un sitio de sucursal, puede crear un plan de marcado a nivel de sitio para ambas, a menos que necesite un plan de nivel de servicio diferente para cada una.


> [!NOTE]
> Para tener en cuenta el consumo de los recursos del sitio central a través de los usuarios de cualquier sitio de sucursal que confíen en el sitio central para fines de presencia, conferencia o conmutación por error, se aconseja considerar cada usuario de sitio de sucursal teniendo en cuenta que el usuario es un usuario registrado en el sitio central. Actualmente no hay límites con respecto al número de usuarios de sitios de sucursal, incluidos los usuarios registrados con una Aplicación de sucursal con funciones de supervivencia.



También se recomienda crear un plan de marcado y una directiva de voz de nivel de usuario que asignará a los usuarios de sitio de sucursal. Para obtener más información, consulte “[Crear un plan de marcado en Lync Server 2013](lync-server-2013-create-a-dial-plan.md)” y “[Crear la directiva de enrutamiento VoIP para usuarios de sucursal en Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md)” en la documentación sobre implementación.

## Enrutamiento de los números de extensión

Cuando prepare planes de marcado y directivas de voz para los usuarios de sitios de sucursal, no olvide incluir reglas de normalización y de traducción que contrasten las cadenas con los formatos de números utilizados en el atributo msRTCSIP-line (o URI de línea) de modo que las llamadas de Lync 2013 habilitadas entre los usuarios del sitio de sucursal y los usuarios del sitio central se enruten correctamente. En particular, cuando las llamadas se tienen que enrutar por RTC porque el vínculo de WAN no está disponible. Existen algunas consideraciones especiales más para los números marcados que contienen números de extensión, en lugar de números de teléfono solamente.

Las reglas de normalización y de traducción que contrastan los URI de línea que contienen un número de extensión, ya sea en exclusiva o junto con un número de teléfono E.164 completo, tienen requisitos adicionales. En esta sección se describen algunos escenarios de ejemplo para enrutar las llamadas para un URI de línea con un número de extensión.

Si su organización no tiene números de teléfono de llamada directa de extensión (DID) configurados para usuarios individuales y el URI de línea de cada usuario está configurado con *solo* un número de extensión, los usuarios internos pueden llamarse entre sí marcando tan solo el número de extensión. Sin embargo, deberá configurar reglas de configuración que puedan aplicarse a llamadas procedentes de un usuario de sitio de sucursal a un usuario de sitio central que contrasten los números de extensión.

En un escenario en el que haya disponible un vínculo WAN entre un sitio de sucursal y un sitio central, las llamadas de los usuarios de un sitio de sucursal a los usuarios del sitio central no necesitan que la regla de normalización correspondiente traduzca el número, ya que la llamada no se enruta por el RTC. Por ejemplo:


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
<th>Traducción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>No traduce números de 5 dígitos</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>$1</p></td>
<td><p>No traduce 10001</p></td>
</tr>
</tbody>
</table>


También debe afrontar escenarios como cuando el vínculo WAN entre un sitio de sucursal y un sitio central no se encuentra disponible y una llamada desde un sitio de sucursal se debe enrutar por el RTC. Durante la interrupción del vínculo WAN, si un usuario de un sitio de sucursal llama a un usuario del sitio central marcando la extensión del mismo, tendrá que tener una regla de traducción de llamadas salientes que añada el número de teléfono completo del usuario del sitio central. Si el URI de línea de un usuario contiene el número de teléfono completo de la organización y el número de extensión único del usuario en lugar de un número de teléfono completo único para el usuario, necesitará una regla de traducción de llamadas salientes que añada, en su lugar, el número de teléfono completo de la organización. Por ejemplo:


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
<th>Patrón de comprobación</th>
<th>Traducción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Traduce números de 5 dígitos al número de teléfono y la extensión de un usuario</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>+14255550123;ext=$1</p></td>
<td><p>10001 se traduce a +14255550123;ext=10001</p></td>
</tr>
<tr class="even">
<td><p>Traduce números de cinco dígitos al número de teléfono de la organización y la extensión de un usuario</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>+14255550100;ext=$1</p></td>
<td><p>10001 se traduce a +14255550100;ext=10001</p></td>
</tr>
</tbody>
</table>


En este escenario, si el par de tronco que se encarga de volver a enrutar hacia el RTC no admite los números de extensión, la regla de traducción de llamadas salientes también tendrá que quitar el número de extensión. Por ejemplo:


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
<th>Patrón de comprobación</th>
<th>Traducción</th>
<th>Ejemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Quita la extensión de los números de teléfono con extensiones</p></td>
<td><p>^\+(\d*);ext=(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>+14255550123;ext=10001 se traduce a +14255550123</p></td>
</tr>
</tbody>
</table>


Independientemente de si hay o no un vínculo WAN disponible, si la organización no tiene configurados números de llamada directa de extensión (DID) para usuarios individuales y el URI de línea de un usuario contiene el número de teléfono de la organización y el número de extensión único de un usuario, deberá configurar el URI de línea del número de teléfono de la organización con un número al que pueda alcanzar el par de tronco o la puerta de enlace RTC en el sitio de sucursal. También debe configurar el URI de línea del número de teléfono de la organización para incluir su extensión única para llamadas que se enrutarán a ese número.

Si desea más información sobre las llamadas que realiza un usuario del sitio central cuando el vínculo WAN entre los sitios no está disponible, consulte Preparación de la supervivencia de correo de voz, a continuación. Si desea información sobre los planes de marcado y las reglas de normalización, incluidas otras reglas de muestra, consulte [Planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) en la documentación sobre planeamiento y [Configurar planes de marcado en Lync Server 2013](lync-server-2013-configuring-dial-plans.md) en la documentación de implementación. Si desea más detalles sobre las reglas de traducción de llamadas salientes, vea [Reglas de traducción en Lync Server 2013](lync-server-2013-translation-rules.md) en la documentación sobre planeamiento y [Definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.

## Preparación de la supervivencia de correo de voz

Normalmente Mensajería unificada de Exchange (UM) se instala solo en el sitio central y no en los sitios de sucursal. El autor de la llamada debe poder dejar un mensaje de correo de voz, aunque el vínculo WAN entre el sitio de sucursal y el sitio central no esté disponible. En consecuencia, configurar el URI de línea para el número de teléfono del operador automático de Mensajería unificada de Exchange que ofrece mensajería de voz para los usuarios de correo de voz requiere algunas consideraciones especiales, así como la directiva de voz, el plan de marcado y las reglas de normalización aplicables a ese número de correo de voz.

Las Aplicaciones de sucursal con funciones de supervivencia (SBA) y los Servidores de sucursal con funciones de supervivencia ofrecen la supervivencia del correo de voz para los usuarios de sucursales durante la interrupción del vínculo WAN. Concretamente, si se utiliza una Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia y la WAN deja de estar disponible, la SBA o Servidor de sucursal con funciones de supervivencia vuelve a enrutar las llamadas no contestadas realizadas a través del RTC a Mensajería unificada de Exchange en el sitio central. Con una SBA o un Servidor de sucursal con funciones de supervivencia, los usuarios también pueden recuperar los mensajes de correo de voz a través del RTC durante la interrupción de la WAN. Por último, durante la interrupción de la WAN, la Aplicación de sucursal con funciones de supervivencia o Servidor de sucursal con funciones de supervivencia pone en cola las notificaciones de llamadas perdidas y, a continuación, las carga en el servidor Mensajería unificada de Exchange cuando se restablece la conexión WAN. Para ayudar a garantizar que el nuevo enrutamiento del correo de voz es resistente, no olvide agregar una entrada para el nombre de dominio completo del grupo de servidores del sitio central y una entrada para el nombre de dominio completo del Servidor perimetral que hospeda el archivo en el Servidor de sucursal con funciones de supervivencia. Si no lo hace, la resolución de DNS puede exceder el tiempo dado, a no ser que se tenga un servidor de DNS en el sitio de sucursal.

Para configurar la supervivencia de correo de voz para usuarios de sitio de sucursal, se recomiendan las configuraciones siguientes:

  - Un administrador de Microsoft Exchange debe configurar un operador automático de Mensajería unificada de Exchange para aceptar únicamente mensajes. Esta configuración deshabilita el resto de funciones genéricas, como la transferencia a un usuario o a un operador, y limita el operador automático para que solo acepte mensajes. El administrador de Exchange también puede usar un operador automático genérico o personalizado para enrutar la llamada a un operador.

  - El administrador de Lync Server debe usar el número de teléfono del operador automático como número de **Operador automático de mensajería unificada de Exchange** en la configuración usada para volver a enrutar el correo de voz de la Aplicación de sucursal con funciones de supervivencia o del servidor de sucursal.

  - El administrador de Lync Server debe obtener el número de teléfono de acceso de suscriptor de la Mensajería unificada de Exchange y usarlo como número de **acceso de suscriptor** en la configuración usada para volver a enrutar el correo de voz en la Aplicación de sucursal con funciones de supervivencia o en el Servidor de sucursal con funciones de supervivencia.

  - El administrador de Lync Server debe configurar la Mensajería unificada de Exchange de modo que solo se asocie un plan de marcado con todos los usuarios de sucursal que necesiten obtener acceso al correo de voz durante una interrupción de la red WAN.

  - Cuando el vínculo de WAN no está disponible, las llamadas a los usuarios de un sitio de sucursal se pueden enrutar hacia el buzón de voz de mensajería unificada de Exchange del usuario, pero solo si la directiva de voz aplicada a la llamada especifica un número de teléfono de mensajería de voz que sea única y no incluya un número de extensión.

## Requisitos de hardware y software para la resistencia de sitios de sucursal

Los requisitos de hardware y software pueden variar según la solución de resistencia de que disponga.

## Requisitos para aplicaciones de sucursal con funciones de supervivencia

El hardware y software necesarios están integrados en la Aplicación de sucursal con funciones de supervivencia. No obstante, también se recomienda que cada sitio de sucursal implemente un servidor DHCP para obtener direcciones IP de cliente; de lo contrario, cuando la concesión DHCP caduque, los clientes no tendrán conectividad IP.

Si los servidores de DNS de la empresa están ubicados solamente en sitios centrales, los usuarios de sitios de sucursal no podrán conectarse a ellos durante las interrupciones de la WAN y, por tanto, la detección de Lync Server que usa SRV (registro de recursos de servicio) de DNS dará un error. Para garantizar que las llamadas se vuelvan a enrutar rápidamente durante una interrupción de la WAN, los registros de DNS deben guardarse en la memoria caché del sitio de sucursal. Si el enrutador de la sucursal lo permite, active la memoria caché de DNS. O puede implementar un servidor de DNS en la sucursal. Puede tratarse de un servidor independiente o una versión de la Aplicación de sucursal con funciones de supervivencia que admita las funcionalidades de DNS. Para obtener más detalles, póngase en contacto con su proveedor de Aplicación de sucursal con funciones de supervivencia.


> [!NOTE]
> No es necesario tener un controlador de dominio en cada sitio de sucursal. La Aplicación de sucursal con funciones de supervivencia autentica clientes mediante un certificado especial que envía al cliente como respuesta a la solicitud de certificado del cliente cuando este inicia sesión.



Los clientes de Lync pueden detectar Lync Server mediante la opción de DHCP 120 (opción de registrador de SIP). Se puede configurar de dos formas distintas:

  - Configure el servidor DHCP en el sitio de sucursal para responder a las consultas de DHCP 120, que devuelven el FQDN del registrador en la Aplicación de sucursal con funciones de supervivencia o en el Servidor de sucursal con funciones de supervivencia.

  - Active el DHCP de Lync Server. Cuando esté activado, el registrador de Lync Server responderá a las consultas de las opción DHCP 120. Observe que el registrador no responde a las consultas de DHCP que no sean de la opción 120.

Asimismo, para sitios de sucursal más grandes que tengan varias subredes, deben habilitarse agentes de retransmisión DHCP para reenviar las consultas de la opción DHCP 120 al servidor DHCP (configuración 1) o al registrador (configuración 2).

Por último, los usuarios de sitios de sucursal deben configurarse para Telefonía IP empresarial y se les debe proporcionar un extremo de comunicaciones unificadas apropiado.

## Requisitos para servidores de sucursal con funciones de supervivencia

Los requisitos para Servidores de sucursal con funciones de supervivencia son los mismos que para un Servidor front-end. Para obtener más información, consulte [Plataformas de hardware de servidor para Lync Server 2013](lync-server-2013-server-hardware-platforms.md) en la documentación sobre planeamiento.

## Requisitos para implementaciones de sitio de sucursal de Lync Server a escala completa

Para obtener más información, consulte [Determinar los requisitos de infraestructura para Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) en la documentación sobre planeamiento.

