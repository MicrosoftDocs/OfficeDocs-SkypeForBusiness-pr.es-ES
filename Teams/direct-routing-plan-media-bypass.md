---
title: Planear desvío de medios con enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Lea este tema para obtener información sobre cómo planear el desvío de medios con el enrutamiento directo teléfono del sistema.
ms.openlocfilehash: b3a31e23ef065840d830c111c64e0618d90aa71b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232803"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planear desvío de medios con enrutamiento directo

## <a name="about-media-bypass-with-direct-routing"></a>Acerca de la omisión de medios con el enrutamiento directo

Desvío de medios le permite acortar la ruta de acceso del tráfico de medios y reducir el número de saltos en tránsito para mejorar el rendimiento. Con el desvío de medios, medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviar a través del sistema de teléfono de Microsoft. Para configurar medios desvío, los SBC y el cliente deben ser en la misma ubicación o la red.

Puede controlar el desvío de medios para cada SBC mediante el comando **Set-CSOnlinePSTNGateway** con el parámetro **- MediaBypass** establecido en true o false. Si habilita el desvío de medios, esto no significa que todo el tráfico de medios permanecerá en la red corporativa. En este artículo se describe el flujo de llamadas en distintos escenarios.    

Los siguientes diagramas ilustran la diferencia en el flujo de llamadas con y sin desvío de medios.

Sin desvío de medios, cuando un cliente realiza o recibe una llamada, señalización y medios fluyen entre la SBC, el sistema de teléfono de Microsoft y el cliente de los equipos, tal como se muestra en el siguiente diagrama:

![Fluyen de muestra de señalización y medios sin desvío de medios](media/direct-routing-media-bypass-1.png)


Pero supongamos que un usuario está en el mismo edificio o red como la SBC. Por ejemplo, supongamos que un usuario que se encuentra en un edificio en hace de Frankfurt una llamada a un usuario de RTC: 

- **Sin medios de desvío**, medios fluirá a través de Ámsterdam o Dublin (donde se implementan los centros de datos de Microsoft) y volver a la SBC en Frankfurt. 

  El centro de datos en Europa está seleccionado porque la SBC se encuentra en Europa, y Microsoft utiliza el centro de datos más cercano a la SBC. Aunque este método no afecta a la calidad de la llamada debido a la optimización del flujo de tráfico dentro de redes de Microsoft en la mayoría de ubicaciones geográficas, el tráfico tiene un bucle innecesario.     

- **En discos de desvío**, se mantienen los medios directamente entre el usuario de los equipos y la SBC tal como se muestra en el siguiente diagrama:

![Fluyen de muestra de señalización y medios con desvío de medios](media/direct-routing-media-bypass-2.png)

Protocolos de aprovecha denominados establecimiento interactivo de conectividad (ICE) en el cliente de los equipos y ICE claro en la SBC el desvío de medios. Estos protocolos permiten el enrutamiento directo usar la ruta de medios más directa para una calidad óptima. HIELO y ICE Lite son los estándares de WebRTC. Para obtener información detallada acerca de estos protocolos, consulte RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Flujo de llamadas y planeación de firewall

Flujo de llamadas y planeación de firewall depende de si el usuario tiene acceso directo a la dirección IP pública de la SBC y, si el usuario está dentro o fuera de la red.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flujo de llamadas si el usuario tiene acceso directo a la dirección IP pública de la SBC

Si el usuario tiene acceso directo a la dirección IP pública de la SBC, el flujo de llamadas es como sigue:

- Desvío de medios, el cliente de los equipos debe tener acceso a la dirección IP pública de la SBC incluso desde una red interna. Si no se desean medios directa, pueden flujo de los medios a través de transmisiones de transporte.

- Ésta es la solución recomendada cuando un usuario se encuentra en el mismo edificio o la red como la SBC: quitar componentes de Microsoft Cloud de la ruta de acceso de medios.

- Señalización siempre fluye a través de la nube de Microsoft.

El siguiente diagrama muestra el flujo de llamada cuando el desvío de medios está habilitado, el cliente es interno y el cliente puede llegar a la dirección IP pública de la SBC (medios directas): 

- Las flechas y los valores numéricos de las rutas de acceso son conformidad con el artículo [flujos de llamadas de los equipos de Microsoft](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .

- La señalización SIP siempre tiene las rutas de acceso 4 y 4' (dependiendo de la dirección del tráfico). Permanece local y toma 5b de la ruta de acceso de medios.

![Muestra el flujo de llamadas con el desvío de medios habilitado, cliente es interno y puede llegar a la dirección IP pública del controlador de borde de sesión (medios directas)](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flujo de llamadas si el usuario no tiene acceso a la dirección IP pública de la SBC

A continuación describen flujo de llamada si el usuario no tiene acceso a la dirección IP pública de la SBC. 

Por ejemplo, suponga que el usuario es externo y el Administrador de inquilinos decidido no abrir la dirección IP pública de la SBC para todos los usuarios de Internet, pero sólo para el Microsoft Cloud. Los componentes internos de tráfico pueden transmitir a través de las transmisiones de transporte de los equipos. Esta es la configuración recomendada para los usuarios fuera de la red corporativa. Tenga en cuenta lo siguiente:

- Se utilizan transmisiones de transporte de los equipos.

- Desvío de medios, Microsoft utiliza una versión de transmisiones de transporte que requiere la apertura de puertos 50 000 para 59 999 entre las transmisiones de transporte de los equipos y la SBC (en el futuro que se va a mover a la versión que requiere puertos sólo 3478 y 3479).

- Por motivos de optimización de medios, Microsoft recomienda abriendo la dirección IP pública de la SBC únicamente a los equipos de transporte multifase. Para los clientes de fuera de la red corporativa, Microsoft recomienda el uso de transmisiones de transporte en lugar de llegar a la dirección IP pública de la SBC directamente.

El siguiente diagrama muestra el flujo de llamada cuando el desvío de medios está habilitado, el cliente es externo y el cliente no puede acceder a la dirección IP pública del controlador de borde de sesión (medios se retransmitan mediante la retransmisión de transporte de los equipos).

- Las flechas y los valores numéricos de las rutas de acceso son conformidad con el artículo [flujos de llamadas de los equipos de Microsoft](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .

- Medios se retransmiten a través de las rutas de acceso 3, 3', 4 y 4'

![Muestra el flujo de llamada si el usuario no tiene acceso a la dirección IP pública de la SBC)](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flujo de llamadas si un usuario está fuera de la red y tiene acceso a la dirección IP pública de la SBC

> [!NOTE]
> No es una configuración recomendada porque no permite aprovechar de transmisiones de transporte de los equipos. En su lugar, debe tener en cuenta el escenario anterior, donde el usuario no tiene acceso a la dirección IP pública de la SBC. 

El siguiente diagrama muestra el flujo de llamada cuando el desvío de medios está habilitado, el cliente es externo y el cliente puede llegar a la dirección IP pública de la SBC (medios directas).

- Las flechas y los valores numéricos de las rutas de acceso son conformidad con el artículo [flujos de llamadas de los equipos de Microsoft](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows) .

- La señalización SIP siempre tiene 3 las rutas de acceso y 3' (dependiendo de la dirección del tráfico). Flujos de medios con la ruta de acceso de 2.

![Muestra el flujo de llamada si el usuario no tiene acceso a la dirección IP pública de la SBC)](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Uso de los procesadores de medios y retransmisiones de transporte

Hay dos componentes en el Cloud Microsoft que puede estar en la ruta de acceso del tráfico de medios: procesadores de medios y retransmisiones de transporte. 

- El procesador de medios es un componente de orientado al público que controla los medios en los casos sin desvío y controla los medios para aplicaciones de voz.

   Procesadores de medios siempre están en la ruta de acceso para las llamadas que no sean pasó de usuario final, pero nunca en la ruta de acceso para las llamadas omitidas. Procesadores de medios siempre están en la ruta de acceso para todas las aplicaciones de voz, como estacionamiento de llamadas, organizativa operador automático y las colas de llamadas.

- La retransmisión de transporte se usa para conectar con el servicio de transporte más cercano para enviar el tráfico en tiempo real.

   Transmisiones de transporte podrían o es posible que no estén en la ruta de acceso de las llamadas omitidas--procedentes de o destinados a los usuarios finales--dependiendo de que el usuario es y cómo se configura la red.

El siguiente diagrama muestra dos flujos de llamadas: uno con desvío de medios habilitado y el segundo con medios desvío deshabilitado. Nota el diagrama ilustra únicamente el tráfico procedente de--o destinado a--los usuarios finales.  
- El controlador de medios es un microservice en Azure que asigna procesadores de medios y crea ofertas de protocolo de descripción de sesión (SDP).

- El servidor Proxy SIP es un componente que traduce señalización de REST de HTTP usados en los equipos para SIP.    

![Muestra dos flujos de llamadas: uno con desvío de medios habilitado y el segundo con desvío de medios deshabilitado)](media/direct-routing-media-bypass-6.png)


En la tabla siguiente se resume las diferencias entre los procesadores de medios y retransmisiones de transporte.

|    | Procesadores de medios | Transmisiones de transporte|
| :--------------|:---------------|:------------|
En la ruta de medios para las llamadas que no sean pasó para los usuarios finales | Siempre | Nunca | 
En la ruta de medios para las llamadas omitidas para los usuarios finales | Nunca | Si el cliente no puede acceder a la SBC en la dirección IP pública | 
En la ruta de medios para aplicaciones de voz | Siempre | Nunca | 
Puede hacer transcodificación (B2BUA)\* | Sí | No, sólo retransmite audio entre extremos | 
Número de instancias en todo el mundo y ubicación | 8 total: 2 en nosotros este y oeste; 2 en Ámsterdam y Dublin; 2 en Hong Kong y Singapur; 2 en Japón (que se agrega en Q1CY2019)  | Varios

El intervalo IP es 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254). 

\*Explicación de transcodificación: 

- Procesador de medios es B2BUA, lo que significa que puede cambiar un códecs (por ejemplo, SEDA desde el cliente de los equipos a MP y G.711 entre MP y SBC).

- Transmisiones de transporte no son B2BUA, lo que significa que nunca se cambia el códec entre el cliente y el SBC--incluso si el tráfico fluye a través de retransmisiones.

### <a name="use-of-teams-transport-relays-in-escalation-scenarios-if-trunk-is-configured-for-media-bypass"></a>Desvío de retransmisiones de transporte de los equipos de su uso en escenarios de escalación si tronco está configurado para los medios

Los equipos transporte multifase siempre están en la ruta de acceso de medios en los siguientes escenarios:

- Llamada se remite de 1:1 a una llamada de grupo
- Llamada se va a un usuario federado de equipos
- Llamada se reenvía o se transfiere a un Skype para usuarios de empresa

Asegúrese de que su SBC tiene acceso a las transmisiones de transporte, tal y como se describe a continuación.    


## <a name="sip-signaling-fqdns-and-firewall-ports"></a>Señalización SIP: Los puertos de firewall y los FQDN

Para la señalización SIP, los requisitos de FQDN y el servidor de seguridad son los mismos que para los casos que no sean pasó. 

Los puntos de conexión para el enrutamiento directo son los FQDN de tres los siguientes:

- **sip.pstnhub.microsoft.com** – FQDN Global – debe intentar en primer lugar. Cuando la SBC envía una solicitud para resolver este nombre, los servidores DNS de Microsoft Azure devolución una dirección IP que apunta al centro de datos de Azure principal asignada a la SBC. La asignación se basa en las métricas de rendimiento de los centros de datos y la proximidad geográfica a la SBC. La dirección IP devuelta corresponde al FQDN principal.

- **sip2.pstnhub.microsoft.com** – secundario FQDN – geográficamente se asigna a la segunda región de prioridad.

- **sip3.pstnhub.microsoft.com** – terciario FQDN – geográficamente se asigna a la región de prioridad de terceros.

Se deben colocar estos tres nombres de dominio completos con el fin:

- Proporcionar una experiencia óptima (menos cargada y más cercana al centro de datos SBC asignada por consultar el primer nombre de dominio completo).

- Proporcionar conmutación por error cuando se establece una conexión desde una SBC para un centro de datos que está experimentando un problema temporal. Para obtener más información, vea el mecanismo de conmutación por error que aparece a continuación.


El **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com**y **sip3.pstnhub.microsoft.com** de nombres de dominio completos se resolverá en una de las siguientes direcciones IP:
- 52.114.148.0
- 52.114.132.46
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

Debe abrir los puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente a y desde las direcciones de señalización. Si el servidor de seguridad es compatible con nombres DNS, el FQDN del **sip all.pstnhub.microsoft.com** se resuelve en todas las direcciones IP anterior. Debe usar los siguientes puertos:

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| Proxy SIP | SBC | 1024 - 65535 | Definidos en la SBC |
| SIP/TLS | SBC | Proxy SIP | Definidos en la SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>El tráfico de medios: intervalos IP y puerto

El tráfico de medios fluye entre el SBC y los equipos cliente si está disponible la conectividad directa o a través de los equipos de transporte multifase si el cliente no puede acceder a la SBC utilizando la dirección IP pública.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Requisitos para el tráfico de medios directa (entre el cliente de los equipos y la SBC) 

El cliente debe tener acceso a los puertos especificados (vea la tabla) en la dirección IP pública de la SBC. 

Nota: Si el cliente está en una red interna, la comunicación se transmite a la dirección IP pública de la SBC. Puede configurar hairpinning en su dispositivo NAT para que tráfico nunca abandona el equipamiento de red de empresa.

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Cliente | SBC | 50 000 – 50 019  | Definidos en la SBC |
| UDP/SRTP | SBC | Cliente | Definidos en la SBC | 50 000 – 50 019  |


Nota: Si tiene un dispositivo de red que traduce los puertos de origen del cliente, por favor, asegúrese de que se abren puertos traducidos entre los equipos de la red y el SBC. 

### <a name="requirements-for-using-transport-relays"></a>Requisitos para el uso de transmisiones de transporte

Transmisiones de transporte se encuentran en el mismo intervalo que procesadores de medios (para casos sin desvío): 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254).

El intervalo de puertos de las transmisiones de transporte de los equipos se muestra en la siguiente tabla:


| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Retransmisión de transporte | SBC | 50 000-59 999    | Definidos en la SBC |
| UDP/SRTP | SBC | Retransmisión de transporte | Definidos en la SBC | 50 000 – 59 999, 3478, 3479     |


Nota: Microsoft recomienda al menos dos puertos por llamada simultánea en la SBC. Debido a que Microsoft tiene dos versiones de transmisiones de transporte, se necesita lo siguiente:

- v4, que sólo puede trabajar con el intervalo de puertos 50 000 a 59 999

- V6, que funciona con puertos 3478, 3479

En este momento, el desvío de medios sólo admite v4 versión de transmisiones de transporte. Soporte técnico de v6 se explicará en el futuro. 

Debe abrir los puertos 3478 y 3479 para realizar la transición. Cuando Microsoft introduce la compatibilidad con transmisiones de transporte v6 con desvío de medios, no necesitará volver a configurar los equipos de la red o SBCs. 

### <a name="requirements-for-using-media-processors"></a>Requisitos para el uso de procesadores de medios

Procesadores de medios siempre están en la ruta de acceso de medios para aplicaciones de voz. Los requisitos son los mismos que para la configuración sin desvío.


El intervalo IP para el tráfico de medios es 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254).

El intervalo de puertos de los procesadores de medios se muestra en la siguiente tabla:

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Procesador de medios | SBC | 49 152 – 53 247    | Definidos en la SBC |
| UDP/SRTP | SBC | Procesador de medios | Definidos en la SBC | 49 152 – 53 247     |

## <a name="considerations-if-you-have-skype-for-business-phones-in-your-network"></a>Consideraciones sobre si tiene Skype para teléfonos de negocio en la red  

Si tiene cualquier Skype para puntos finales profesionales en la red que está utilizando enrutamiento directo--por ejemplo, un usuario puede tener un teléfono de 3PIP que se basa en Skype para clientes empresariales--los equipos de la omisión de medios en el tronco que sirve de estos usuarios debe desactivarse.

Puede crear un tronco independiente para estos usuarios y asignar una directiva de enrutamiento de voz en línea.

Pasos de configuración de alto nivel:

- Dividir los usuarios por tipo – dependiendo de si el usuario tiene un teléfono 3PIP o no.

- Crear dos troncos independientes con diferentes nombres de dominio completos: uno habilitado el desvío de medios; los otro no. 

  Elija el mismo SBC ambos troncos. Los puertos para la señalización SIP TLS deben ser distintos. Los puertos de medios deben ser el mismo.

- Asignar el tronco correcto según el tipo de usuario en la directiva de enrutamiento de voz en línea.

En el ejemplo siguiente ilustra esta lógica.

| Conjunto de usuarios | Número de usuarios | Tronco FQDN asignado en OVRP | Desvío de medios habilitado |
| :------------ |:----------------- |:--------------|:--------------|
Usuarios con los clientes de los equipos y los teléfonos de 3PIP | 20 | sbc1.contoso.com:5061 | falso | 
Usuarios con sólo puntos finales los equipos (incluidos los nuevos teléfonos de certificados para los equipos) | 980 | sbc2.contoso.com:5060 | verdadero

Ambos troncos pueden apuntar a la misma SBC con la misma dirección IP pública. La señalización de puertos en el SBC de TLS deben ser distintos, como se muestra en el siguiente diagrama. Tenga en cuenta que tendrá para asegurarse de que su certificado admite tanto los troncos. En SAN, debe tener dos nombres (**sbc1.contoso.com** y **sbc2.contoso.com**) o tener un certificado de comodín.


![Muestra que ambas troncos pueden apuntar a la misma SBC con la misma dirección IP pública)](media/direct-routing-media-bypass-7.png)

Para obtener información acerca de cómo configurar dos troncos en el mismo SBC, vea la documentación proporcionada por el proveedor SBC:

- AudioCodes
- Cinta de opciones
- TE-Systems (Anynode)   

## <a name="client-endpoints-supported-with-media-bypass"></a>El desvío de los extremos de cliente compatibles con medios

Desvío de medios es compatible con todos los extremos de los equipos, excepto los clientes Web de los equipos hasta aviso aún más. 

Si los usuarios prefieren la aplicación Web de los equipos en Microsoft Edge, Google Chrome o Mozilla Firefox, debe desactivarse el desvío de medios para dichos usuarios. Se le presentarán llamadas utilizando un tronco habilitado el desvío de medios en el futuro.   
 
## <a name="see-also"></a>Vea también

[Configurar el desvío de medios con enrutamiento directo](direct-routing-configure-media-bypass.md)



