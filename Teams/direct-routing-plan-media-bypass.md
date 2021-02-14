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
description: Obtenga información sobre cómo planear la omisión de medios con el enrutamiento directo del sistema telefónico, que le permite acortar la ruta del tráfico multimedia y mejorar el rendimiento.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: efd6d4275d1e83df7821f178ddac8027039b6fce
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790662"
---
# <a name="plan-for-media-bypass-with-direct-routing"></a>Planear desvío de medios con enrutamiento directo

## <a name="about-media-bypass-with-direct-routing"></a>Acerca de la omisión de medios con enrutamiento directo

La omisión de medios permite acortar la ruta del tráfico multimedia y reducir el número de saltos en tránsito para un mejor rendimiento. Con la omisión de medios, los medios se mantienen entre el controlador de borde de sesión (SBC) y el cliente en lugar de enviarlos a través del sistema telefónico de Microsoft. Para configurar la omisión de medios, la SBC y el cliente deben estar en la misma ubicación o red.

Puede controlar la omisión de medios para cada SBC mediante el comando **Set-CSOnlinePSTNGateway** con el parámetro **-MediaBypass** establecido en true o false. Si habilita la omisión de medios, esto no significa que todo el tráfico multimedia permanezca dentro de la red corporativa. En este artículo se describe el flujo de llamadas en diferentes escenarios.    

Los diagramas siguientes muestran la diferencia en el flujo de llamadas con y sin omisión de medios.

Sin omisión de medios, cuando un cliente realiza o recibe una llamada, tanto la señalización como el flujo multimedia entre el SBC, el sistema telefónico de Microsoft y el cliente de Teams, como se muestra en el siguiente diagrama:

> [!div class="mx-imgBorder"]
> ![Muestra la señalización y el flujo de medios sin omisión de medios](media/direct-routing-media-bypass-1.png)


Pero imaginemos que un usuario está en el mismo edificio o red que el SBC. Por ejemplo, supongamos que un usuario que está en un edificio de Fráncfort realiza una llamada a un usuario de RTC: 

- **Sin omisión de** medios, los medios fluirán a través de Ámsterdam o Dublín (donde se implementan centros de datos de Microsoft) y de nuevo al SBC en Fráncfort. 

  El centro de datos en Europa está seleccionado porque la SBC está en Europa y Microsoft usa el centro de datos más cercano a la SBC. Aunque este método no afecta a la calidad de las llamadas debido a la optimización del flujo del tráfico dentro de las redes de Microsoft en la mayoría de las zonas geográficas, el tráfico tiene un bucle innecesario.     

- **Con la omisión** de medios, los elementos multimedia se mantienen directamente entre el usuario de Teams y el SBC, como se muestra en el siguiente diagrama:

  > [!div class="mx-imgBorder"]
  > ![Muestra la señalización y el flujo de medios con omisión de medios](media/direct-routing-media-bypass-2.png)

El omisión de medios aprovecha los protocolos denominados establecimientos de conectividad interactiva (ICE) en el cliente de Teams y ICE lite en la SBC. Estos protocolos permiten que el enrutamiento directo use la ruta de medios más directa para obtener una calidad óptima. ICE e ICE Lite son estándares WebRTC. Para obtener información detallada sobre estos protocolos, vea RFC 5245.


## <a name="call-flow-and-firewall-planning"></a>Planeamiento del flujo de llamadas y del firewall

El flujo de llamadas y la planificación del firewall dependen de si el usuario tiene acceso directo a la dirección IP pública del SBC y de si el usuario está dentro o fuera de la red.

### <a name="call-flow-if-the-user-has-direct-access-to-the-public-ip-address-of-the-sbc"></a>Flujo de llamadas si el usuario tiene acceso directo a la dirección IP pública de la SBC

Si el usuario tiene acceso directo a la dirección IP pública del SBC, el flujo de llamadas es el siguiente:

- Para la omisión de medios, el cliente de Teams debe tener acceso a la dirección IP pública del SBC incluso desde una red interna. Si no desea usar medios directos, los medios pueden fluir mediante retransmisión de transporte.

- Esta es la solución recomendada cuando un usuario está en el mismo edificio o red que el SBC: quite los componentes de Microsoft Cloud de la ruta multimedia.

- La señalización siempre fluye a través de la nube de Microsoft.

El siguiente diagrama muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es interno y el cliente puede llegar a la dirección IP pública del SBC (multimedia directo): 

- Las flechas y los valores numéricos de las rutas de acceso se ajustan a los flujos [de llamada de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)

- La señalización SIP siempre toma las rutas 4 y 4' (según la dirección del tráfico). Los medios permanecen como locales y asumen la ruta 5b.

> [!div class="mx-imgBorder"]
> ![Muestra el flujo de llamadas con Omisión de medios habilitada, el cliente es interno](media/direct-routing-media-bypass-3.png)


### <a name="call-flow-if-the-user-does-not-have-access-to-the-public-ip-address-of-the-sbc"></a>Flujo de llamadas si el usuario no tiene acceso a la dirección IP pública del SBC

A continuación se describe el flujo de llamadas si el usuario no tiene acceso a la dirección IP pública de la SBC. 

Por ejemplo, supongamos que el usuario es externo y que el administrador de inquilinos ha decidido no abrir la dirección IP pública del SBC a todos los usuarios en Internet, pero solo a Microsoft Cloud. Los componentes internos del tráfico pueden fluir a través de los relés de transporte de Teams. Tenga en cuenta lo siguiente:

- Se usan retransmisión de transporte de Teams.

- Para la omisión de medios, Microsoft usa una versión de retransmisión de transporte que requiere abrir los puertos de 50 000 a 59 999 entre los relés de transporte de Teams y la SBC (en el futuro tenemos previsto pasar a la versión que requiere solo 3478 y 3479 puertos).


El siguiente diagrama muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente no puede llegar a la dirección IP pública del controlador de borde de sesión (los medios se retransmiten por retransmisión de transporte de Teams).

- Las flechas y los valores numéricos de las rutas de acceso se ajustan a los flujos [de llamada de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)

- Los medios se retransmiten a través de las rutas 3, 3', 4 y 4'

> [!div class="mx-imgBorder"]
> ![Muestra el flujo de llamadas si el usuario no tiene acceso a la DIRECCIÓN IP pública de la SBC.](media/direct-routing-media-bypass-4.png)


### <a name="call-flow-if-a-user-is-outside-the-network-and-has-access-to-the-public-ip-of-the-sbc"></a>Flujo de llamadas si un usuario está fuera de la red y tiene acceso a la DIRECCIÓN IP pública de la SBC

> [!NOTE]
> Esta no es una configuración recomendada porque no aprovecha las ventajas de los relés de transporte de Teams. En su lugar, considere el escenario anterior en el que el usuario no tiene acceso a la dirección IP pública de la SBC. 

El siguiente diagrama muestra el flujo de llamadas cuando se habilita la omisión de medios, el cliente es externo y el cliente puede llegar a la dirección IP pública de la SBC (multimedia directa).

- Las flechas y los valores numéricos de las rutas de acceso se ajustan a lo establecido en el artículo sobre flujos de [llamada de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows)

- La señalización SIP siempre toma las rutas 3 y 3' (según la dirección del tráfico). Los flujos multimedia se fluyen mediante la ruta 2.

> [!div class="mx-imgBorder"]
> ![Muestra el flujo de llamadas si el usuario no tiene acceso a la DIRECCIÓN IP pública de la SBC.](media/direct-routing-media-bypass-5.png)


## <a name="use-of-media-processors-and-transport-relays"></a>Uso de procesadores multimedia y retransmisión de transporte

Hay dos componentes en Microsoft Cloud que pueden estar en la ruta del tráfico multimedia: procesadores de medios y retransmisión de transporte. 

- El procesador de medios es un componente público que controla los medios en casos que no se omiten y que controla los medios para las aplicaciones de voz.

   Los procesadores multimedia siempre están en la ruta de acceso a las llamadas no omitadas por el usuario final, pero nunca en la ruta de acceso a las llamadas omitadas. Los procesadores de medios siempre están en la ruta de acceso a todas las aplicaciones de voz, como El parque de llamadas, Operador automático de organización y colas de llamadas.

- La retransmisión de transporte se usa para conectarse al servicio de transporte más cercano y enviar tráfico en tiempo real.

   Los relés de transporte pueden o no estar en la ruta de acceso para las llamadas omitadas (que proceden de usuarios finales o se destinan a él) en función de dónde se encuentra el usuario y de cómo esté configurada la red.

En el siguiente diagrama se muestran dos flujos de llamadas: uno con omisión de medios habilitada y la segunda con omisión de medios deshabilitada. Tenga en cuenta que el diagrama solo ilustra el tráfico que procede de los usuarios finales o que se destina a él.  
- El controlador de medios es un microservice en Azure que asigna procesadores de medios y crea ofertas de Protocolo de descripción de sesión (SDP).

- El proxy SIP es un componente que traduce la señalización REST de HTTP usada en Teams a SIP.    

> [!div class="mx-imgBorder"]
> ![Muestra los flujos de llamada con media bypass habilitado e deshabilitado](media/direct-routing-media-bypass-6.png)


En la tabla siguiente se resume la diferencia entre los procesadores multimedia y los relés de transporte.

|    | Procesadores multimedia | Retransmisión de transporte|
| :--------------|:---------------|:------------|
En la ruta de acceso multimedia para llamadas no omitadas para usuarios finales | Siempre | Nunca | 
En la ruta de acceso multimedia para llamadas omitida para usuarios finales | Nunca | Si el cliente no puede acceder al SBC en la dirección IP pública | 
En la ruta de acceso a medios para aplicaciones de voz | Siempre | Nunca | 
Puede realizar la transcodificación (B2BUA)\* | Sí | No, solo retransmite el audio entre los puntos de conexión | 
Número de instancias en todo el mundo y ubicación | Total 10: 2 en EE. UU. Este y Oeste; 2 en Ámsterdam y Dublín; 2 en Hong Kong y Singapur; 2 en Japón; 2 en Australia East y Southeast | Múltiplo

Los intervalos IP son:
- 52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254)
- 52.120.0.0/14 (direcciones IP de 52.120.0.1 a 52.123.255.254)

\* Explicación de la transcodificación: 

- El procesador de medios es B2BUA, lo que significa que puede cambiar los códecs (por ejemplo, SILK del cliente de Teams a MP y G.711 entre MP y SBC).

- Los relés de transporte no son B2BUA, lo que significa que el códec nunca se cambia entre el cliente y el SBC, incluso si el tráfico fluye a través de retransmisión.

### <a name="use-of-teams-media-processors-if-trunk-is-configured-for-media-bypass"></a>Uso de los procesadores multimedia de Teams si se configura el tronco para la omisión de medios

Los procesadores multimedia de Teams siempre se insertan en la ruta de acceso multimedia en los escenarios siguientes:

- La llamada se escala de 1:1 a una llamada grupal
- La llamada va a parar a un usuario federado de Teams
- La llamada se desvía o se transfiere a un usuario de Skype Empresarial

Asegúrese de que la SBC tiene acceso a los intervalos de procesadores multimedia y retransmisión de transporte, como se describe a continuación.    


## <a name="sip-signaling-fqdns"></a>Señalización SIP: FQDN

Para la señalización SIP, los requisitos de FQDN y firewall son los mismos que para los casos que no se omiten. 

El enrutamiento directo se ofrece en los siguientes entornos de Microsoft 365 u Office 365:
- Microsoft 365 u Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD Obtenga más información sobre [los entornos de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) y administración gubernamental de Estados Unidos, como GCC, GCC High y DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Entornos GCC de Microsoft 365, Office 365 y Office 365

Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:

- **sip.pstnhub.microsoft.com** tiene que probarse primero el FQDN global. Cuando la SBC envía una solicitud para resolver este nombre, los servidores DNS de Microsoft Azure devuelven una dirección IP que apunta al centro de datos de Azure principal asignado a la SBC. La asignación se basa en las métricas de rendimiento de los centros de datos y la proximidad geográfica al SBC. La dirección IP devuelta corresponde al FQDN principal.

- **sip2.pstnhub.microsoft.com** – FQDN secundario – se asigna geográficamente a la segunda región de prioridad.

- **sip3.pstnhub.microsoft.com** – FQDN terciario - se asigna geográficamente a la tercera región de prioridad.

Debe colocar estos tres FQDN para:

- Proporcione una experiencia óptima (menos cargada y más cercana al centro de datos SBC asignado consultando el primer FQDN).

- Proporcionar conmutación por error cuando se establece una conexión desde un SBC a un centro de datos que está experimentando un problema temporal. Para obtener más información, vea a continuación el mecanismo de conmutación por error.


Los fqdN **sip.pstnhub.microsoft.com,** **sip2.pstnhub.microsoft.com** y **sip3.pstnhub.microsoft.com** se resolverán en una de las siguientes direcciones IP:
- 52.114.148.0
- 52.114.132.46
- 52.114.16.74
- 52.114.20.29
- 52.114.75.24
- 52.114.76.76
- 52.114.7.24
- 52.114.14.70

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización. Si el firewall admite nombres DNS, el nombre **sip-all.pstnhub.microsoft.com** FQDN se resuelve con todas estas direcciones IP. 

### <a name="office-365-gcc-dod-environment"></a>Entorno de Office 365 GCC DoD

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.dod.teams.microsoft.us:** FQDN global. Como el entorno del DoD de Office 365 solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

Los FQDN : sip.pstnhub.dod.teams.microsoft.us resolverán en una de las siguientes direcciones IP:

- 52.127.64.33
- 52.127.68.34

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si el firewall admite nombres DNS, el nombre sip.pstnhub.dod.teams.microsoft.us FQDN se resuelve con todas estas direcciones IP. 

### <a name="office-365-gcc-high-environment"></a>Entorno de Office 365 GCC High

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.gov.teams.microsoft.us:** FQDN global. Como el entorno de GCC High solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

Los FQDN : sip.pstnhub.gov.teams.microsoft.us resolverán en una de las siguientes direcciones IP:

- 52.127.88.59
- 52.127.92.64

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si el firewall admite nombres DNS, el nombre sip.pstnhub.gov.teams.microsoft.us FQDN se resuelve en todas estas direcciones IP. 

## <a name="sip-signaling-ports"></a>Señalización SIP: puertos

Los requisitos de puerto son los mismos para todos los entornos de Office 365 donde se ofrece enrutamiento directo:
- Microsoft 365 u Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Debes usar los puertos siguientes:

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
SIP/TLS| SIP Proxy | SBC | 1024 - 65535 | Definido en la SBC |
| SIP/TLS | SBC | SIP Proxy | Definido en la SBC | 5061 |


## <a name="media-traffic-ip-and-port-ranges"></a>Tráfico multimedia: intervalos de IP y puertos

El tráfico multimedia fluye entre el cliente de SBC y Teams si la conectividad directa está disponible o a través de retransmisión de transporte de Teams si el cliente no puede llegar al SBC con la dirección IP pública.

### <a name="requirements-for-direct-media-traffic-between-the-teams-client-and-the-sbc"></a>Requisitos para el tráfico multimedia directo (entre el cliente de Teams y el SBC) 

El cliente debe tener acceso a los puertos especificados (vea la tabla) en la dirección IP pública de la SBC. 

Nota: Si el cliente está en una red interna, los medios fluyen a la dirección IP pública de la SBC. Puede configurar la fijación de pelo en el dispositivo NAT para que el tráfico nunca salga del equipo de red empresarial.

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Cliente | SBC | 50 000 – 50 019  | Definido en la SBC |
| UDP/SRTP | SBC | Cliente | Definido en la SBC | 50 000 – 50 019  |


> [!NOTE]
> Si tiene un dispositivo de red que traduce los puertos de origen del cliente, asegúrese de que los puertos traducidos estén abiertos entre el equipo de red y la SBC. 

### <a name="requirements-for-using-transport-relays"></a>Requisitos para usar retransmisión de transporte

Los relés de transporte están en el mismo rango que los procesadores multimedia (para los casos que no se omiten): 

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Entornos GCC de Microsoft 365, Office 365 y Office 365

- 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Entorno de Office 365 GCC DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Entorno de Office 365 GCC High

- 52.127.88.0/21


El intervalo de puertos de los relés de transporte de Teams (aplicable a todos los entornos) se muestra en la tabla siguiente:


| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Retransmisión de transporte | SBC | 50 000 -59 999    | Definido en la SBC |
| UDP/SRTP | SBC | Retransmisión de transporte | Definido en la SBC | 50 000 – 59 999, 3478, 3479     |


> [!NOTE]
> Microsoft recomienda al menos dos puertos por llamada simultánea en la SBC. Dado que Microsoft tiene dos versiones de retransmisión de transporte, son necesarias las siguientes opciones:
> 
> - v4, que solo puede trabajar con el intervalo de puertos 50 000 a 59 999
> 
> - v6, que funciona con los puertos 3478, 3479

En este momento, la omisión de medios solo es compatible con la versión v4 de los relés de transporte. Presentaremos la compatibilidad con v6 en el futuro. 

Debe abrir los puertos 3478 y 3479 para realizar la transición. Cuando Microsoft introduzca la compatibilidad con retransmisión de transporte v6 con omisión de medios, no tendrá que volver a configurar su equipo de red o SBCs. 

### <a name="requirements-for-using-media-processors"></a>Requisitos para usar procesadores multimedia

Los procesadores de medios siempre están en la ruta de acceso multimedia de las aplicaciones de voz y de los clientes web (por ejemplo, los clientes de Teams en Edge o Google Chrome). Los requisitos son los mismos que para la configuración que no se omita.


El intervalo IP para el tráfico multimedia es 

### <a name="office-365-and-office-365-gcc-environments"></a>Entornos GCC de Office 365 y Office 365

- 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254)

## <a name="office-365-gcc-dod-environment"></a>Entorno de Office 365 GCC DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Entorno de Office 365 GCC High

- 52.127.88.0/21

El rango de puertos de los procesadores de medios (aplicables a todos los entornos) se muestra en la tabla siguiente:

| Tráfico | De | Hasta | Puerto de origen | Puerto de destino|
| :-------- | :-------- |:-----------|:--------|:---------|
UDP/SRTP | Procesador de medios | SBC | 3478, 3479 y 49 152- 53 247    | Definido en la SBC |
| UDP/SRTP | SBC | Procesador de medios | Definido en la SBC | 3478, 3479 y 49 152- 53 247     |

## <a name="configure-separate-trunks-for-media-bypass-and-non-media-bypass"></a>Configurar troncos separados para la omisión de medios y la omisión sin medios  

Si va a migrar a la omisión de medios desde una omisión que no sea de medios y desea confirmar la funcionalidad antes de migrar todo el uso a la omisión de medios, puede crear un tronco separado y una directiva de enrutamiento de voz en línea separada para enrutar al tronco de omisión de medios y asignarlo a usuarios específicos. 

Pasos de configuración de alto nivel:

- Identifique a los usuarios para probar la omisión de medios.

- Cree dos troncos independientes con FQDN diferentes: uno habilitado para la omisión de medios; y la otra no. 

  Ambos troncos apuntan al mismo SBC. Los puertos de señalización SIP tls deben ser diferentes. Los puertos para los medios deben ser los mismos.

- Cree una nueva directiva de enrutamiento de voz en línea y asigne el tronco de omisión de medios a las rutas correspondientes asociadas con el uso de RTC para esta directiva.

- Asigne la nueva directiva de enrutamiento de voz en línea a los usuarios que haya identificado para probar la omisión de medios.

En el ejemplo siguiente se ilustra esta lógica.

| Conjunto de usuarios | Número de usuarios | FQDN de tronco asignado en OVRP | Omisión de medios habilitada |
| :------------ |:----------------- |:--------------|:--------------|
Usuarios con tronco de omisión sin medios | 980 | sbc1.contoso.com:5060 | verdadero
Usuarios con tronco de omisión de medios | 20 | sbc2.contoso.com:5061 | falso | 

Ambos troncos pueden apuntar al mismo SBC con la misma dirección IP pública. Los puertos de señalización TLS de la SBC deben ser diferentes, como se muestra en el siguiente diagrama. Tenga en cuenta que necesitará asegurarse de que el certificado admite ambos troncos. En SAN, debe tener dos nombres **(sbc1.contoso.com** y **sbc2.contoso.com)** o tener un certificado comodín.

> [!div class="mx-imgBorder"]
> ![Muestra que ambos troncos pueden apuntar al mismo SBC con la misma IP pública.](media/direct-routing-media-bypass-7.png)

Para obtener información sobre cómo configurar dos troncos en el mismo SBC, consulte la documentación proporcionada por su proveedor de SBC:

 - [Documentación de implementación de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentación de implementación de Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentación de implementación de comunicaciones de la cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentación de implementación de TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

## <a name="client-endpoints-supported-with-media-bypass"></a>Puntos de conexión de cliente compatibles con omisión de medios

La omisión de medios es compatible con todos los clientes de escritorio independientes de Teams, los clientes Android e iOS y los dispositivos de teams phone. 

En el caso de los demás puntos de conexión que no admitan el omisión de medios, convertiremos la llamada a no omitida incluso si se inició como una llamada de omisión. Esto ocurre automáticamente y no requiere ninguna acción del administrador. Esto incluye teléfonos 3PIP de Skype Empresarial y clientes web de Teams que admiten las llamadas de enrutamiento directo (clientes basados en WebRTC que se ejecutan en Microsoft Edge, Google Chrome y Mozilla Firefox). 
 
## <a name="see-also"></a>Consulte también

[Configurar el desvío de medios con enrutamiento directo](direct-routing-configure-media-bypass.md)


