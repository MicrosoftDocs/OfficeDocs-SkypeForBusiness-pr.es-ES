---
title: Planear desvío de medios con enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprende a planear la omisión multimedia con enrutamiento directo del sistema telefónico, lo que te permite acortar la ruta del tráfico multimedia y mejorar el rendimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea92103789927d35ae8bdd317987f32863d4d74e
ms.sourcegitcommit: e09591a0df9848b50bfeda29650e91e9d35724af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2023
ms.locfileid: "69981795"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planear desvío de medios con enrutamiento directo

## <a name="about-media-bypass-with-direct-routing"></a>Acerca de la omisión multimedia con enrutamiento directo

La omisión multimedia le permite acortar la ruta de acceso del tráfico multimedia y reducir el número de saltos en tránsito para mejorar el rendimiento. Con la omisión de medios, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviarlo a través de Microsoft Phone System. Para configurar la omisión de medios, el SBC y el cliente deben estar en la misma ubicación o red.

Puede controlar la omisión de medios para cada SBC mediante el comando **Set-CSOnlinePSTNGateway** con el parámetro **-MediaBypass** establecido en true o false. Si habilita la omisión de medios, esto no significa que todo el tráfico multimedia permanecerá dentro de la red corporativa. En este artículo se describe el flujo de llamadas en diferentes escenarios.

Los diagramas siguientes ilustran la diferencia en el flujo de llamadas con y sin omisión de medios.

Sin omisión multimedia, cuando un cliente realiza o recibe una llamada, la señalización y el flujo multimedia entre el SBC, Microsoft Phone System y el cliente de Teams, como se muestra en el siguiente diagrama:

> [!div class="mx-imgBorder"]
> ![Muestra la señalización y el flujo de medios sin derivación de medios.](media/direct-routing-media-bypass-1.png)


Pero supongamos que un usuario está en la misma compilación o red que el SBC. Por ejemplo, supongamos que un usuario que está en un edificio de Frankfurt realiza una llamada a un usuario de RTC: 

- **Sin omisión de medios**, los medios fluirán a través de Amsterdam o Dublín (donde se implementan los centros de datos de Microsoft) y de vuelta al SBC en Frankfurt. 

  El centro de datos en Europa se selecciona porque el SBC está en Europa y Microsoft usa el centro de datos más cercano al SBC. Aunque este enfoque no afecta a la calidad de las llamadas debido a la optimización del flujo de tráfico dentro de las redes de Microsoft en la mayoría de las geografías, el tráfico tiene un bucle innecesario.     

- **Con la omisión de medios**, los elementos multimedia se mantienen directamente entre el usuario de Teams y el SBC, tal y como se muestra en el siguiente diagrama:

  > [!div class="mx-imgBorder"]
  > ![Muestra la señalización y el flujo de medios con la omisión de medios.](media/direct-routing-media-bypass-2.png)

La omisión de medios aprovecha protocolos denominados Establecimiento de conectividad interactiva (ICE) en el cliente de Teams y ICE Lite en el SBC. Estos protocolos permiten que el enrutamiento directo use la ruta de acceso multimedia más directa para obtener una calidad óptima. ICE y ICE Lite son estándares WebRTC. Para obtener información detallada sobre estos protocolos, vea RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Flujo de llamadas y planeamiento del firewall

El flujo de llamadas y la planificación del firewall dependen de si el usuario tiene acceso directo a la dirección IP pública del SBC y de si el usuario se encuentra dentro o fuera de la red.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flujo de llamadas si el usuario tiene acceso directo a la dirección IP pública de la SBC

Si el usuario tiene acceso directo a la dirección IP pública del SBC, el flujo de llamadas es el siguiente:

- Para la omisión de medios, el cliente de Teams debe tener acceso a la dirección IP pública del SBC incluso desde una red interna. Si no se desea un medio directo, los medios pueden fluir a través de los relés de transporte.

- Esta es la solución recomendada cuando un usuario está en la misma compilación o red que el SBC: quite los componentes de Microsoft Cloud de la ruta de acceso multimedia.

- La señalización siempre fluye a través de la nube de Microsoft.

El siguiente diagrama muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es interno y el cliente puede alcanzar la dirección IP pública del SBC (medios directos): 

- Las flechas y los valores numéricos de las rutas de acceso se ajustan a [los flujos de llamada de Microsoft Teams](./microsoft-teams-online-call-flows.md).

- La señalización SIP siempre toma las rutas 4 y 4' (dependiendo de la dirección del tráfico). Los medios se mantienen locales y toma la ruta 5b.

> [!div class="mx-imgBorder"]
> ![Muestra el flujo de llamadas con la omisión de medios habilitada; el cliente es interno.](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC

A continuación se describe el flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC. 

Por ejemplo, supongamos que el usuario es externo y el administrador de inquilinos ha decidido no abrir la dirección IP pública del SBC a todos los usuarios de Internet, sino solo a Microsoft Cloud. Los componentes internos del tráfico pueden fluir a través de los relés de transporte de Teams. Tenga en cuenta lo siguiente:

- Se utilizan relés de transporte de Teams.

- Para la omisión multimedia, Microsoft usa una versión de retransmisiones de transporte que requiere abrir los puertos 50 000 a 59 999 entre los relés de transporte de Teams y el SBC (en el futuro tenemos previsto pasar a la versión que requiere 3478-3481 puertos).


El siguiente diagrama muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente no puede alcanzar la dirección IP pública del controlador de borde de sesión (el relé de transporte de Teams retransmite multimedia).

- Las flechas y los valores numéricos de las rutas de acceso se ajustan a [los flujos de llamada de Microsoft Teams](./microsoft-teams-online-call-flows.md).

- Los medios se retransmiten a través de las rutas 3, 3', 4 y 4'

> [!div class="mx-imgBorder"]
> ![Muestra el flujo de llamadas si el usuario no tiene acceso a la DIRECCIÓN IP pública del SBC.](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flujo de llamadas si un usuario está fuera de la red y tiene acceso a la DIRECCIÓN IP pública del SBC

> [!NOTE]
> Esta no es una configuración recomendada porque no aprovecha las ventajas de los relés de transporte de Teams. En su lugar, debe tener en cuenta el escenario anterior en el que el usuario no tiene acceso a la dirección IP pública del SBC. 

El siguiente diagrama muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente puede alcanzar la dirección IP pública del SBC (medios directos).

- Las flechas y los valores numéricos de las rutas de acceso se ajustan al artículo [Flujos de llamadas de Microsoft Teams](./microsoft-teams-online-call-flows.md) .

- La señalización SIP siempre toma las rutas 3 y 3' (dependiendo de la dirección del tráfico). Flujos de medios mediante la ruta de acceso 2.

> [!div class="mx-imgBorder"]
> ![Muestra el flujo de llamadas si el usuario no tiene acceso a la DIRECCIÓN IP pública del SBC.](media/direct-routing-media-bypass-5.png)



## <a name="use-of-media-processors-and-transport-relays"></a>Uso de procesadores multimedia y relés de transporte

Hay dos componentes en la nube de Microsoft que pueden estar en la ruta de acceso del tráfico multimedia: procesadores multimedia y relés de transporte. 

- El procesador multimedia es un componente orientado al público que controla los medios en casos que no se omiten y controla los medios de las aplicaciones de voz.

   Los procesadores multimedia siempre están en la ruta de acceso para las llamadas que no se omiten del usuario final, pero nunca en la ruta de acceso para las llamadas omitida. Los procesadores multimedia siempre están en la ruta de acceso para todas las aplicaciones de voz, como el parque de llamadas, el operador automático de organización y las colas de llamadas.

- El relé de transporte se utiliza para conectar con el servicio de transporte más cercano para enviar el tráfico en tiempo real.

   Las retransmisiones de transporte pueden estar o no en la ruta de acceso para llamadas omitida (que provienen de usuarios finales o se destinan a ellas) en función de dónde se encuentre el usuario y cómo esté configurada la red.

El siguiente diagrama muestra dos flujos de llamada: uno con la omisión de medios habilitada y la segunda con la omisión de medios deshabilitada.

> [!NOTE]
> El diagrama solo muestra el tráfico que proviene de usuarios finales o que se destina a ellos.  

- El controlador multimedia es un microservicio de Azure que asigna procesadores multimedia y crea ofertas de Protocolo de descripción de sesión (SDP).

- El proxy SIP es un componente que traduce la señalización HTTP REST usada en Teams a SIP.    

> [!div class="mx-imgBorder"]
> ![Muestra los flujos de llamada con la omisión de medios habilitada y deshabilitada.](media/direct-routing-media-bypass-6.png)


En la tabla siguiente se resume la diferencia entre los procesadores multimedia y los relés de transporte.

|  &nbsp; | Procesadores multimedia | Relés de transporte|
| :--------------|:---------------|:------------|
|En la ruta de acceso multimedia para las llamadas no omitida para los usuarios finales | Siempre | Si el cliente no puede acceder directamente al procesador multimedia |
|En la ruta de acceso multimedia para llamadas omitida para usuarios finales | Nunca | Si el cliente no puede alcanzar el SBC en la dirección IP pública |
|En la ruta de acceso multimedia para aplicaciones de voz | Siempre | Nunca |
|Puede realizar la transcodificación (B2BUA)\* | Sí | No, solo retransmite audio entre puntos de conexión |

Los intervalos IP son:
- 52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254)
- 52.122.0.0/15 (direcciones IP de 52.122.0.1 a 52.123.255.254)

\* Explicación de la transcodificación: 

- El procesador multimedia es B2BUA, lo que significa que puede cambiar un códec (por ejemplo, SILK del cliente de Teams a MP y G.711 entre MP y SBC).

- Los relés de transporte no son B2BUA, lo que significa que el códec nunca se cambia entre el cliente y el SBC -- incluso si el tráfico fluye vía los relés.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Uso de procesadores multimedia de Teams si el tronco está configurado para omisión multimedia

Los procesadores multimedia de Teams siempre se insertan en la ruta de acceso multimedia en los siguientes escenarios:

- La llamada se escala de 1:1 a una llamada grupal
- La llamada va a un usuario federado de Teams
- La llamada se desvía o se transfiere a un usuario de Skype Empresarial

Asegúrese de que su SBC tiene acceso a los rangos procesadores de medios y relés de transporte como se describe a continuación.    


## <a name="sip-signaling-fqdns"></a>Señalización SIP: FQDN

Para la señalización SIP, los requisitos de FQDN y firewall son los mismos que para los casos sin omitir. 

Direct Routing se ofrece en los siguientes entornos de Microsoft 365 o Office 365:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD Obtenga más información sobre [Office 365 y entornos gubernamentales de ESTADOS Unidos](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) como GCC, GCC High y DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Entornos GCC de Microsoft 365, Office 365 y Office 365

Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:

- **sip.pstnhub.microsoft.com** , FQDN global, debe probarse primero. Cuando el SBC envía una solicitud para resolver este nombre, los servidores DNS de Microsoft Azure devuelven una dirección IP que apunta al centro de datos de Azure principal asignado al SBC. La asignación se basa en métricas de rendimiento de los centros de datos y la proximidad geográfica al SBC. La dirección IP devuelta corresponde al FQDN principal.

- **sip2.pstnhub.microsoft.com** ( FQDN secundario ) se asigna geográficamente a la región de segunda prioridad.

- **sip3.pstnhub.microsoft.com** ( FQDN terciario ) se asigna geográficamente a la tercera región de prioridad.

Debe colocar estos tres FQDN para:

- Ofrezca una experiencia óptima (menos cargada y más cercana al centro de datos SBC asignado consultando el primer FQDN).

- Proporcionar conmutación por error cuando se establece una conexión desde un SBC a un centro de datos que experimenta un problema temporal. Para obtener más información, consulte mecanismo de conmutación por error a continuación.


Los FQDN **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** y **sip3.pstnhub.microsoft.com** se resolverán en las direcciones IP de las siguientes subredes:
- 52.112.0.0/14
- 52.122.0.0/15

Debe abrir puertos para todos estos intervalos IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.

### <a name="office-365-gcc-dod-environment"></a>Office 365 entorno GCC DoD

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.dod.teams.microsoft.us** : FQDN global. Como el entorno de DoD Office 365 existe solo en los centros de datos de Ee. UU., no hay FQDN secundarios y terciarios.

El sip.pstnhub.dod.teams.microsoft.us fqdn se resolverá en una dirección IP desde la siguiente subred:

- 52.127.64.0/21

Debe abrir puertos para todos estos intervalos IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si el firewall admite nombres DNS, la sip.pstnhub.dod.teams.microsoft.us FQDN se resuelve en todas estas subredes IP. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.gov.teams.microsoft.us** : FQDN global. Como el entorno GCC High existe solo en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

El sip.pstnhub.gov.teams.microsoft.us fqdn se resolverá en una dirección IP desde la siguiente subred:

- 52.127.88.0/21

Debe abrir puertos para todos estos intervalos IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si el firewall admite nombres DNS, el sip.pstnhub.gov.teams.microsoft.us FQDN se resuelve en todas estas subredes IP. 

## <a name="sip-signaling-ports"></a>Señalización SIP: puertos

Los requisitos de puerto son los mismos para todos los entornos Office 365 en los que se ofrece enrutamiento directo:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Debes usar los puertos siguientes:

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
| SIP/TLS| SIP Proxy | SBC | 1024 - 65535 | Definido en el SBC |
| SIP/TLS | SBC | SIP Proxy | Definido en el SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Tráfico multimedia: intervalos de puertos y IP

El tráfico multimedia fluye entre el cliente de SBC y Teams si hay conectividad directa disponible o a través de retransmisiones de transporte de Teams si el cliente no puede llegar a la SBC con la dirección IP pública.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Requisitos para el tráfico multimedia directo (entre el cliente de Teams y el SBC) 

El cliente debe tener acceso a los puertos especificados (ver tabla) en la dirección IP pública del SBC. 

> [!NOTE]
> Si el cliente está en una red interna, los medios fluyen a la dirección IP pública del SBC. Puedes configurar el anclaje del pelo en el dispositivo NAT para que el tráfico nunca salga del equipo de red de la empresa.

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Cliente | SBC | 50000-50019| Definido en el SBC |
| UDP/SRTP | SBC | Cliente | Definido en el SBC | 50000-50019  |


> [!NOTE]
> Si tiene un dispositivo de red que traduzca los puertos de origen del cliente, asegúrese de que los puertos traducidos se abran entre el equipo de red y el SBC. 

### <a name="requirements-for-using-transport-relays"></a>Requisitos para usar relés de transporte

Los relés de transporte están en el mismo rango que los procesadores multimedia (para casos sin derivación): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Entornos GCC de Microsoft 365, Office 365 y Office 365

- 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 entorno GCC DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

- 52.127.88.0/21


El intervalo de puertos de los relés de transporte de Teams (aplicable a todos los entornos) se muestra en la tabla siguiente:


| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Retransmisión de transporte | SBC | 50 000 -59 999    | Definido en el SBC |
| UDP/SRTP | SBC | Retransmisión de transporte | Definido en el SBC | 50 000 – 59 999, 3478-3481     |


> [!NOTE]
> Microsoft recomienda al menos dos puertos por llamada simultánea en el SBC. Como Microsoft tiene dos versiones de relés de transporte, son necesarias las siguientes:
> 
> - v4, que solo puede trabajar con el intervalo de puertos 50 000 a 59 999
> 
> - v6, que funciona con los puertos 3478-3481

En este momento, la omisión de medios solo admite la versión v4 de los relés de transporte. Presentaremos el soporte técnico de v6 en el futuro. 

Debe abrir los puertos 3478-3481 para realizar la transición. Cuando Microsoft presenta la compatibilidad con relés de transporte v6 con omisión de medios, no es necesario volver a configurar el equipo de red ni los SBC. 

### <a name="requirements-for-using-media-processors"></a>Requisitos para usar procesadores multimedia

Los procesadores multimedia siempre están en la ruta de acceso multimedia para las aplicaciones de voz y para los clientes web (por ejemplo, los clientes de Teams en Microsoft Edge o Google Chrome). Los requisitos son los mismos que para la configuración que no es de omisión.


El intervalo IP para el tráfico multimedia es 

### <a name="office-365-and-office-365-gcc-environments"></a>entornos GCC Office 365 y Office 365

- 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 entorno GCC DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

- 52.127.88.0/21

El rango de puertos de los procesadores multimedia (aplicables a todos los entornos) se muestra en la tabla siguiente:

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
| UDP/SRTP | Procesador multimedia | SBC | 3478-3481 y 49 152 – 53 247    | Definido en el SBC |
| UDP/SRTP | SBC | Procesador multimedia | Definido en el SBC | 3478-3481 y 49 152 – 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Configurar troncos independientes para la omisión de medios y la omisión no multimedia  

Si va a migrar a la omisión de medios desde la omisión de medios y desea confirmar la funcionalidad antes de migrar todo el uso a la omisión de medios, puede crear un tronco independiente y una directiva de enrutamiento de voz en línea independiente para redirigir al tronco de omisión de medios y asignarlo a usuarios específicos. 

Pasos de configuración de alto nivel:

- Identifique a los usuarios para probar la omisión de medios.

- Crear dos troncos independientes con FQDN diferentes: uno habilitado para la omisión de medios; el otro no. 

  Ambos troncos apuntan al mismo SBC. Los puertos para la señalización SIP TLS deben ser diferentes. Los puertos para los medios deben ser los mismos.

- Cree una nueva directiva de enrutamiento de voz en línea y asigne el tronco de omisión de medios a las rutas correspondientes asociadas con el uso de RTC para esta directiva.

- Asigne la nueva directiva de enrutamiento de voz en línea a los usuarios que haya identificado para probar la omisión de medios.

En el ejemplo siguiente se ilustra esta lógica.

| Conjunto de usuarios | Número de usuarios | FQDN de tronco asignado en OVRP | Omisión de medios habilitada |
| :------------ |:----------------- |:--------------|:--------------|
| Usuarios con tronco de omisión no multimedia | 980 | sbc1.contoso.com:5061 | falso |
| Usuarios con tronco de omisión multimedia | 20 | sbc2.contoso.com:5060 | verdadero | 

Ambos troncos pueden apuntar al mismo SBC con la misma dirección IP pública. Los puertos de señalización TLS en el SBC deben ser diferentes, como se muestra en el siguiente diagrama. Note que usted necesitará asegurarse de que su certificado soporta ambos troncos. En SAN, debe tener dos nombres (**sbc1.contoso.com** y **sbc2.contoso.com**) o tener un certificado comodín.

> [!div class="mx-imgBorder"]
> ![Muestra ambos troncos pueden señalar al mismo SBC con el mismo IP público.](media/direct-routing-media-bypass-7.png)

Para obtener información sobre cómo configurar dos troncos en el mismo SBC, consulte la documentación proporcionada por su proveedor de SBC:

 - [Documentación de implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de comunicaciones de la cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Puntos de conexión de cliente compatibles con la omisión de medios

La omisión de medios es compatible con todos los clientes de escritorio independientes de Teams, los clientes de Android e iOS y los dispositivos de teléfono de Teams. 

Para todos los demás puntos de conexión que no admiten la omisión multimedia, convertiremos la llamada en no omisión incluso si se inició como una llamada de omisión. Esto ocurre automáticamente y no requiere ninguna acción del administrador. Esto incluye Skype Empresarial teléfonos 3PIP y clientes web de Teams que admiten llamadas de enrutamiento directo (clientes basados en WebRTC que se ejecutan en Microsoft Edge, Google Chrome y Mozilla Firefox). 
 
## <a name="see-also"></a>Vea también

[Configurar el desvío de medios con enrutamiento directo](direct-routing-configure-media-bypass.md)
