---
title: Planear desvío de medios con enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo planear la omisión de medios con Sistema telefónico enrutamiento directo, lo que le permite acortar la ruta del tráfico multimedia y mejorar el rendimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c65cdb4ede98fbd34c39eb941aed2c582c15b37b
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264960"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planear desvío de medios con enrutamiento directo

## <a name="about-media-bypass-with-direct-routing"></a>Acerca de la omisión de medios con enrutamiento directo

La omisión de medios le permite acortar la ruta del tráfico multimedia y reducir el número de saltos en tránsito para un mejor rendimiento. Con la omisión de medios, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviarlo a través del sistema Teléfono Microsoft sesión. Para configurar la omisión de medios, el SBC y el cliente deben estar en la misma ubicación o red.

Puede controlar la omisión de medios para cada SBC mediante el comando **Set-CSOnlinePSTNGateway** con el **parámetro -MediaBypass** establecido en verdadero o falso. Si habilita la omisión de medios, esto no significa que todo el tráfico multimedia permanezca dentro de la red corporativa. En este artículo se describe el flujo de llamadas en diferentes escenarios.

Los diagramas siguientes ilustran la diferencia en el flujo de llamadas con y sin omisión de medios.

Sin omisión de medios, cuando un cliente realiza o recibe una llamada, tanto la señalización como el flujo multimedia entre el SBC, el sistema Teléfono Microsoft y el cliente Teams, como se muestra en el siguiente diagrama:

> [!div class="mx-imgBorder"]
> ![Muestra la señalización y el flujo de medios sin omisión de medios](media/direct-routing-media-bypass-1.png)


Pero supongamos que un usuario está en el mismo edificio o red que el SBC. Por ejemplo, supongamos que un usuario que se encuentra en un edificio de Fráncfort realiza una llamada a un usuario RTC: 

- **Sin el desvío** de medios, los medios fluirán a través de Ámsterdam o Dublín (donde se implementan los centros de datos de Microsoft) y de nuevo al SBC de Fráncfort. 

  El centro de datos en Europa está seleccionado porque el SBC está en Europa y Microsoft usa el centro de datos más próximo al SBC. Aunque este enfoque no afecta a la calidad de las llamadas debido a la optimización del flujo de tráfico dentro de las redes de Microsoft en la mayoría de las geografías, el tráfico tiene un bucle innecesario.     

- **Con la omisión** de medios, el medio se mantiene directamente entre el Teams y el SBC como se muestra en el diagrama siguiente:

  > [!div class="mx-imgBorder"]
  > ![Muestra la señalización y el flujo multimedia con la omisión de medios](media/direct-routing-media-bypass-2.png)

La omisión de medios usa protocolos denominados Establecimiento de conectividad interactiva (ICE) en el cliente Teams y ICE lite en el SBC. Estos protocolos permiten que el enrutamiento directo use la ruta multimedia más directa para obtener una calidad óptima. ICE y ICE Lite son estándares webRTC. Para obtener información detallada sobre estos protocolos, vea RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Planificación del flujo de llamadas y del firewall

El flujo de llamadas y la planificación del firewall dependen de si el usuario tiene acceso directo a la dirección IP pública del SBC y de si el usuario está dentro o fuera de la red.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flujo de llamadas si el usuario tiene acceso directo a la dirección IP pública del SBC

Si el usuario tiene acceso directo a la dirección IP pública del SBC, el flujo de llamadas es el siguiente:

- Para la omisión de medios, Teams cliente debe tener acceso a la dirección IP pública del SBC incluso desde una red interna. Si no se desea usar medios directos, los medios pueden fluir a través de retransmisión de transporte.

- Esta es la solución recomendada cuando un usuario está en el mismo edificio o red que el SBC: quite los componentes de Microsoft Cloud de la ruta de acceso multimedia.

- La señalización siempre fluye a través de la nube de Microsoft.

En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es interno y el cliente puede llegar a la dirección IP pública del SBC (medios directos): 

- Las flechas y los valores numéricos de las rutas de acceso se ajustan a [Microsoft Teams de llamadas.](./microsoft-teams-online-call-flows.md)

- La señalización SIP siempre toma trayectorias 4 y 4' (según la dirección del tráfico). Multimedia permanece local y toma la ruta 5b.

> [!div class="mx-imgBorder"]
> ![Muestra el flujo de llamadas con la omisión de medios habilitada, el cliente es interno](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC

A continuación se describe el flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC. 

Por ejemplo, suponga que el usuario es externo y el administrador de inquilinos decidió no abrir la dirección IP pública del SBC a todos los usuarios de Internet, sino solo a Microsoft Cloud. Los componentes internos del tráfico pueden fluir a través Teams relés de transporte. Tenga en cuenta lo siguiente:

- Teams Se usan relés de transporte.

- Para la omisión de medios, Microsoft usa una versión de retransmisión de transporte que requiere abrir puertos de 50 000 a 59 999 entre las retransmisiones de transporte de Teams y el SBC (en el futuro planeamos pasar a la versión que solo requiere 3478 y 3479 puertos).


En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente no puede llegar a la dirección IP pública del controlador de borde de sesión (los medios se retransmiten Teams Retransmisión de transporte).

- Las flechas y los valores numéricos de las rutas de acceso se ajustan a [Microsoft Teams de llamadas.](./microsoft-teams-online-call-flows.md)

- Los medios se retransmiten a través de las rutas 3, 3', 4 y 4'

> [!div class="mx-imgBorder"]
> ![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública del SBC](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flujo de llamadas si un usuario está fuera de la red y tiene acceso a la DIRECCIÓN IP pública del SBC

> [!NOTE]
> Esta no es una configuración recomendada porque no se aprovecha de Teams retransmisión de transporte. En su lugar, debe considerar el escenario anterior en el que el usuario no tiene acceso a la dirección IP pública del SBC. 

En el siguiente diagrama se muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente puede llegar a la dirección IP pública del SBC (medios directos).

- Las flechas y los valores numéricos de las rutas de acceso se ajustan al [artículo Microsoft Teams flujos de llamadas.](./microsoft-teams-online-call-flows.md)

- La señalización SIP siempre toma trayectorias 3 y 3' (según la dirección del tráfico). Los flujos multimedia usan la ruta 2.

> [!div class="mx-imgBorder"]
> ![Muestra el flujo de llamadas si el usuario no tiene acceso a la IP pública del SBC](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Uso de procesadores multimedia y retransmisión de transporte

Hay dos componentes en microsoft cloud que pueden estar en la ruta del tráfico multimedia: procesadores multimedia y retransmisión de transporte. 

- El procesador multimedia es un componente orientado al público que controla los medios en casos que no se omiten y controla los medios para las aplicaciones de voz.

   Los procesadores multimedia siempre están en la ruta de acceso para las llamadas no omitidas por el usuario final, pero nunca en la ruta de acceso para las llamadas omitida. Los procesadores multimedia siempre están en la ruta de acceso para todas las aplicaciones de voz, como Parque de llamadas, Operador automático y Colas de llamadas.

- El Retransmisión de transporte se usa para conectarse al servicio de transporte más cercano para enviar tráfico en tiempo real.

   Las retransmisiones de transporte pueden o no estar en la ruta de acceso para llamadas omitida (que proceden o están destinadas a usuarios finales), dependiendo de dónde se encuentra el usuario y de cómo esté configurada la red.

En el siguiente diagrama se muestran dos flujos de llamadas: uno con la omisión de medios habilitada y la segunda con la omisión de medios deshabilitada.

> [!NOTE]
> En el diagrama solo se muestra el tráfico procedente o destinado a los usuarios finales.  

- El controlador multimedia es un microservicio de Azure que asigna procesadores multimedia y crea ofertas del Protocolo de descripción de sesión (SDP).

- El proxy SIP es un componente que traduce la señalización HTTP REST que se usa en Teams a SIP.    

> [!div class="mx-imgBorder"]
> ![Muestra los flujos de llamadas con la omisión de medios habilitada y deshabilitada](media/direct-routing-media-bypass-6.png)


En la tabla siguiente se resume la diferencia entre los procesadores multimedia y los relés de transporte.

|    | Procesadores multimedia | Retransmisión de transporte|
| :--------------|:---------------|:------------|
En la ruta de acceso multimedia para llamadas no omitida para usuarios finales | Siempre | Si el cliente no puede ponerse en contacto directamente con el Procesador multimedia | 
En la ruta de acceso multimedia para llamadas omitida para usuarios finales | Nunca | Si el cliente no puede llegar al SBC en la dirección IP pública | 
En la ruta de acceso multimedia para aplicaciones de voz | Siempre | Nunca | 
Puede realizar la transcodificación (B2BUA)\* | Sí | No, solo retransmite audio entre puntos de conexión | 
Número de instancias en todo el mundo y ubicación | 10 total: 2 en Ee. UU. Este y Oeste; 2 en Ámsterdam y Dublín; 2 en Hong Kong y Singapur; 2 en Japón; 2 en Australia Este y Sureste | Múltiplo

Los rangos IP son:
- 52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254)
- 52.120.0.0/14 (direcciones IP de 52.120.0.1 a 52.123.255.254)

\* Explicación de transcodificación: 

- El procesador multimedia es B2BUA, lo que significa que puede cambiar un códec (por ejemplo, SILK de cliente Teams a MP y G.711 entre MP y SBC).

- Los relés de transporte no son B2BUA, lo que significa que el códec nunca se cambia entre el cliente y el SBC, incluso si el tráfico fluye a través de retransmisión.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Uso de Teams multimedia si el tronco está configurado para la omisión de medios

Teams Los procesadores multimedia siempre se insertan en la ruta de acceso multimedia en los siguientes escenarios:

- La llamada se escala de 1:1 a una llamada grupal
- La llamada se va a un usuario Teams federado
- La llamada se reenvía o se transfiere a Skype Empresarial usuario

Asegúrese de que su SBC tiene acceso a los rangos procesadores multimedia y retransmisión de transporte como se describe a continuación.    


## <a name="sip-signaling-fqdns"></a>Señalización SIP: FQDN

Para la señalización SIP, los requisitos de FQDN y firewall son los mismos que para los casos no omitido. 

El enrutamiento directo se ofrece en los siguientes Microsoft 365 o Office 365 entornos:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD Obtenga más información sobre [Office 365 entornos](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) gubernamentales de Ee. UU. como GCC, GCC high y DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 y Office 365 GCC entornos

Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:

- **sip.pstnhub.microsoft.com:** FQDN global, debe probarse primero. Cuando el SBC envía una solicitud para resolver este nombre, los servidores DNS Microsoft Azure devuelven una dirección IP que apunta al centro de datos de Azure principal asignado al SBC. La tarea se basa en las métricas de rendimiento de los centros de datos y la proximidad geográfica al SBC. La dirección IP devuelta corresponde al FQDN principal.

- **sip2.pstnhub.microsoft.com:** FQDN secundario, se asigna geográficamente a la región de segunda prioridad.

- **sip3.pstnhub.microsoft.com:** FQDN terciario, se asigna geográficamente a la región de tercera prioridad.

Debe colocar estos tres FQDN para:

- Proporcione una experiencia óptima (menos cargada y más cercana al centro de datos de SBC asignada consultando el primer FQDN).

- Proporcionar conmutación por error cuando se establece una conexión desde un SBC a un centro de datos que experimenta un problema temporal. Para obtener más información, vea Mecanismo de conmutación por error a continuación.


Los FQDN **sip.pstnhub.microsoft.com**, **sip2.pstnhub.microsoft.com** y **sip3.pstnhub.microsoft.com** se resolverán en una de las siguientes direcciones IP:
- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29
- 52.114.36.156 
- 52.114.32.169

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización. Si el firewall admite nombres DNS, el FQDN **sip-all.pstnhub.microsoft.com** se resuelve en todas estas direcciones IP. 

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC doD

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.dod.teams.microsoft.us:** FQDN global. Como el Office 365 DoD solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

Los FQDN: sip.pstnhub.dod.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:

- 52.127.64.33
- 52.127.68.34

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si el firewall admite nombres DNS, el FQDN sip.pstnhub.dod.teams.microsoft.us se resuelve en todas estas direcciones IP. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC high environment

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.gov.teams.microsoft.us:** FQDN global. Como el GCC high solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

Los FQDN: sip.pstnhub.gov.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:

- 52.127.88.59
- 52.127.92.64

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si el firewall admite nombres DNS, el FQDN sip.pstnhub.gov.teams.microsoft.us se resuelve en todas estas direcciones IP. 

## <a name="sip-signaling-ports"></a>Señalización SIP: Puertos

Los requisitos de puerto son los mismos para todos los Office 365 en los que se ofrece enrutamiento directo:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Debe usar los siguientes puertos:

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP Proxy | SBC | 1024 - 65535 | Definido en el SBC |
| SIP/TLS | SBC | SIP Proxy | Definido en el SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Tráfico multimedia: intervalos de IP y puertos

El tráfico multimedia fluye entre el SBC y el cliente Teams si la conectividad directa está disponible o a través de retransmisión de transporte de Teams si el cliente no puede llegar al SBC con la dirección IP pública.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Requisitos para el tráfico multimedia directo (entre el Teams y el SBC) 

El cliente debe tener acceso a los puertos especificados (ver tabla) en la dirección IP pública del SBC. 

> [!NOTE]
> Si el cliente se encuentra en una red interna, el medio fluye a la dirección IP pública del SBC. Puede configurar la fijación de pelo en el dispositivo NAT para que el tráfico nunca salga del equipo de red empresarial.

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Cliente | SBC | 3478-3481 y 49152 - 53247| Definido en el SBC |
| UDP/SRTP | SBC | Cliente | Definido en el SBC | 3478-3481 y 49152 - 53247  |


> [!NOTE]
> Si tiene un dispositivo de red que traduce los puertos de origen del cliente, asegúrese de que los puertos traducidos se abren entre el equipo de red y el SBC. 

### <a name="requirements-for-using-transport-relays"></a>Requisitos para usar retransmisión de transporte

Las retransmisión de transporte están en el mismo rango que los procesadores multimedia (para casos que no se omiten): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 y Office 365 GCC entornos

- 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC doD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC high environment

- 52.127.88.0/21


El rango de puertos de Teams relés de transporte (aplicables a todos los entornos) se muestra en la tabla siguiente:


| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Retransmisión de transporte | SBC | 50 000 -59 999    | Definido en el SBC |
| UDP/SRTP | SBC | Retransmisión de transporte | Definido en el SBC | 50 000 – 59 999, 3478, 3479     |


> [!NOTE]
> Microsoft recomienda al menos dos puertos por llamada simultánea en el SBC. Dado que Microsoft tiene dos versiones de retransmisión de transporte, son necesarias las siguientes:
> 
> - v4, que solo puede funcionar con el rango de puertos de 50 000 a 59 999
> 
> - v6, que funciona con los puertos 3478 y 3479

En este momento, la omisión de medios solo admite la versión v4 de retransmisión de transporte. Presentaremos compatibilidad con v6 en el futuro. 

Debe abrir los puertos 3478 y 3479 para la transición. Cuando Microsoft presenta compatibilidad con retransmisión de transporte v6 con omisión de medios, no tendrá que volver a configurar el equipo de red ni los SBC. 

### <a name="requirements-for-using-media-processors"></a>Requisitos para usar procesadores multimedia

Los procesadores multimedia siempre están en la ruta de acceso multimedia para aplicaciones de voz y para clientes web (por ejemplo, Teams en Edge o Google Chrome). Los requisitos son los mismos que para la configuración sin omisión.


El intervalo IP para el tráfico multimedia es 

### <a name="office-365-and-office-365-gcc-environments"></a>Office 365 y Office 365 GCC entornos

- 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)

### <a name="office-365-gcc-dod-environment"></a>Office 365 GCC doD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC high environment

- 52.127.88.0/21

El rango de puertos de los procesadores multimedia (aplicable a todos los entornos) se muestra en la tabla siguiente:

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Procesador multimedia | SBC | 3478, 3479 y 49 152 - 53 247    | Definido en el SBC |
| UDP/SRTP | SBC | Procesador multimedia | Definido en el SBC | 3478, 3479 y 49 152 - 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Configurar troncos independientes para la omisión de medios y la omisión no multimedia  

Si va a migrar a la omisión de medios desde la omisión no multimedia y desea confirmar la funcionalidad antes de migrar todo el uso a la omisión de medios, puede crear un tronco independiente y una directiva de enrutamiento de voz en línea independiente para enrutar al tronco de omisión multimedia y asignarlo a usuarios específicos. 

Pasos de configuración de alto nivel:

- Identificar usuarios para probar la omisión de medios.

- Cree dos troncos independientes con FQDN diferentes: uno habilitado para la omisión de medios; el otro no. 

  Ambos troncos apuntan al mismo SBC. Los puertos para la señalización SIP TLS deben ser diferentes. Los puertos para medios deben ser los mismos.

- Cree una nueva directiva de enrutamiento de voz en línea y asigne el tronco de omisión multimedia a las rutas correspondientes asociadas con el uso de RTC para esta directiva.

- Asigne la nueva directiva de enrutamiento de voz en línea a los usuarios identificados para probar la omisión de medios.

En el ejemplo siguiente se muestra esta lógica.

| Conjunto de usuarios | Número de usuarios | FQDN de tronco asignado en OVRP | Omisión de medios habilitada |
| :------------ |:----------------- |:--------------|:--------------|
Usuarios con tronco de omisión no multimedia | 980 | sbc1.contoso.com:5061 | falso |
Usuarios con tronco de omisión multimedia | 20 | sbc2.contoso.com:5060 | verdadero | 

Ambos troncos pueden apuntar al mismo SBC con la misma dirección IP pública. Los puertos de señalización TLS del SBC deben ser diferentes, como se muestra en el siguiente diagrama. Tenga en cuenta que tendrá que asegurarse de que el certificado admite ambos troncos. En SAN, debe tener dos nombres **(sbc1.contoso.com** y **sbc2.contoso.com)** o tener un certificado comodín.

> [!div class="mx-imgBorder"]
> ![Muestra que ambos troncos pueden apuntar al mismo SBC con la misma IP pública](media/direct-routing-media-bypass-7.png)

Para obtener información sobre cómo configurar dos troncos en el mismo SBC, vea la documentación proporcionada por el proveedor de SBC:

 - [Documentación de implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de Comunicaciones de la cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Extremos de cliente compatibles con la omisión de medios

La omisión de medios es compatible con todos los Teams de escritorio independientes, clientes de Android e iOS y Teams Teléfono dispositivos. 

Para todos los demás puntos de conexión que no admiten la omisión de medios, convertiremos la llamada en no omitir, incluso si se inició como una llamada de omisión. Esto ocurre automáticamente y no requiere ninguna acción del administrador. Esto incluye Skype Empresarial teléfonos 3PIP y clientes web Teams compatibles con las llamadas de enrutamiento directo (clientes basados en WebRTC que se ejecutan en Microsoft Edge, Google Chrome y Mozilla Firefox). 
 
## <a name="see-also"></a>Vea también

[Configurar el desvío de medios con enrutamiento directo](direct-routing-configure-media-bypass.md)
