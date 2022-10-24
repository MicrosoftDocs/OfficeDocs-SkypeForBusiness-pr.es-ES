---
title: Planear el enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: filippse
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Obtén información sobre cómo Enrutamiento directo de Microsoft te permite conectar un controlador de borde de sesión (SBC) compatible proporcionado por el cliente al sistema telefónico.
ms.openlocfilehash: de829008a45e8f4c1095138ddc1b1dcc32cdb3eb
ms.sourcegitcommit: c627bd1df17aefdc353bc4da6db169dfe169031e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2022
ms.locfileid: "68680523"
---
# <a name="plan-direct-routing"></a>Planear el enrutamiento directo

> [!Tip]
> Vea la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearlo e implementarlo: [Enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)

El enrutamiento directo te permite conectar un controlador de borde de sesión (SBC) compatible proporcionado por el cliente al sistema telefónico. Con esta funcionalidad, puede configurar la conectividad de red telefónica conmutada (RTC) local con el cliente de Microsoft Teams, como se muestra en el siguiente diagrama: 

![Diagrama que muestra la configuración de la conectividad con RTC local.](media/PlanDirectRouting1-PSTNwithTeams.png "Configuración de la conectividad con RTC local con el cliente de Microsoft Teams")

  > [!NOTE]
  > Skype Empresarial Online también le permite emparejar un SBC proporcionado por el cliente, pero esto requiere una implementación local Skype Empresarial Server o una edición especial de Skype Empresarial, denominada Cloud Connector, entre el SBC y la nube de Microsoft. Este escenario se conoce como voz híbrida. En cambio, el enrutamiento directo permite una conexión directa entre el SBC compatible y Microsoft Cloud.

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [enrutamiento directo](direct-routing-landing-page.md). 

Con enrutamiento directo, puede conectar su SBC a casi cualquier tronco de telefonía o interconexión con equipos RTC de terceros. Enrutamiento directo le permite: 

- Use prácticamente cualquier tronco RTC con el sistema telefónico. 

- Configure la interoperabilidad entre equipos de telefonía propiedad del cliente, como una central de telefonía privada (PBX) de terceros, dispositivos analógicos y Teams.

Microsoft también ofrece soluciones de voz todo en la nube, como Plan de llamadas. Sin embargo, una solución de voz híbrida podría ser la mejor para su organización si: 

- El plan de llamadas de Microsoft no está disponible en su país. 

- Su organización requiere conexión a dispositivos analógicos de terceros, centros de llamadas, etc. 

- Su organización tiene un contrato existente con un operador RTC.

Direct Routing también es compatible con los usuarios que tienen la licencia adicional para el plan de llamadas de Microsoft. Para obtener más información, consulte [Sistema telefónico y planes de llamadas](calling-plan-landing-page.md). 

Con el enrutamiento directo, cuando los usuarios participan en una conferencia programada, el número de acceso telefónico es proporcionado por el servicio de audioconferencia de Microsoft, que requiere una licencia adecuada.  Al llamar, el servicio de audioconferencia de Microsoft realiza la llamada mediante las funcionalidades de llamada en línea, que requieren una licencia adecuada. (Tenga en cuenta que si un usuario no tiene una licencia de Audioconferencia de Microsoft, la llamada se enruta a través del enrutamiento directo). Para obtener más información, consulte [Reuniones en línea con Teams](https://www.microsoft.com/en-us/microsoft-teams/online-meetings). 
 
Planear la implementación de enrutamiento directo es clave para una implementación correcta. En este artículo se describen los requisitos de infraestructura y licencias y se proporciona información sobre la conectividad SBC: 

- [Requisitos de infraestructura](#infrastructure-requirements)
- [Concesión de licencias y otros requisitos](#licensing-and-other-requirements)
- [Nombres de dominio SBC](#sbc-domain-names)
- [Certificado de confianza público para el SBC](#public-trusted-certificate-for-the-sbc)
- [Señalización SIP: FQDN](#sip-signaling-fqdns)
- [Señalización SIP: puertos](#sip-signaling-ports)
- [Tráfico multimedia: Intervalos de puertos](#media-traffic-port-ranges)
- [Controladores de borde de sesión compatibles (SBCs)](#supported-session-border-controllers-sbcs)

Para obtener información detallada sobre cómo configurar el enrutamiento directo, consulte [Configurar enrutamiento directo](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura
Los requisitos de infraestructura para los SBCs, los dominios y otros requisitos de conectividad de red admitidos para implementar el enrutamiento directo se enumeran en la tabla siguiente:  

|Requisito de infraestructura|Necesita lo siguiente|
|:--- |:--- |
|Controlador de borde de sesión (SBC)|Un SBC compatible. Para obtener más información, consulte [SBCs compatibles](#supported-session-border-controllers-sbcs).|
|Troncos de telefonía conectados al SBC|Uno o más troncos de telefonía conectados al SBC. En un extremo, el SBC se conecta al sistema telefónico a través del enrutamiento directo. El SBC también puede conectarse a entidades de telefonía de terceros, como PBX, adaptadores de telefonía analógica, etc. Funcionará cualquier opción de conectividad RTC conectada a la SBC. (Para la configuración de los troncos RTC al SBC, refiera a los proveedores de SBC o proveedores troncales.)|
|Organización de Microsoft 365|Una organización de Microsoft 365 que usa para hospedar a los usuarios de Microsoft Teams, así como la configuración y la conexión con el SBC.|
|Registrador de usuarios|El usuario debe estar alojado en Microsoft 365.<br/>Si su compañía tiene un entorno local de Skype Empresarial o Lync con conectividad híbrida a Microsoft 365, no puede habilitar la voz en Teams para un usuario alojado en local.<br/><br/>Para comprobar el registrador de un usuario, use el siguiente Skype Empresarial cmdlet de PowerShell en línea:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>El resultado del cmdlet debería mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Dominios|Uno o más dominios agregados a sus organizaciones de Microsoft 365 o Office 365.<br/><br/>Tenga en cuenta que no puede usar el dominio predeterminado, \*.onmicrosoft.com, que se crea automáticamente para su inquilino.<br/><br/>Para ver los dominios, puede usar el siguiente cmdlet de PowerShell de Skype Empresarial Online:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obtener más información sobre dominios y Microsoft 365 u organizaciones Office 365, consulte [Preguntas más frecuentes sobre dominios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Dirección IP pública para la SBC|Una dirección IP pública que se puede usar para conectarse al SBC. En función del tipo de SBC, el SBC puede usar NAT.|
|Nombre de dominio completo (FQDN) para el SBC|Un FQDN para el SBC, donde la parte del dominio del FQDN es uno de los dominios registrados en microsoft 365 o Office 365 organización. Para obtener más información, consulte [Nombres de dominio SBC](#sbc-domain-names).|
|Entrada DNS pública para la SBC |Una entrada DNS pública que asigna el FQDN de SBC a la dirección IP pública. |
|Certificado de confianza público para el SBC |Un certificado para que el SBC se use para todas las comunicaciones con enrutamiento directo. Para obtener más información, vea [Certificado de confianza público para el SBC](#public-trusted-certificate-for-the-sbc).|
|Puntos de conexión para enrutamiento directo |Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:<br/><br/>`sip.pstnhub.microsoft.com` – FQDN global, debe intentarse primero.<br/>`sip2.pstnhub.microsoft.com` – FQDN secundario, se asigna geográficamente a la región de segunda prioridad.<br/>`sip3.pstnhub.microsoft.com` – FQDN terciario, se asigna geográficamente a la tercera región de prioridad.<br/><br/>Para obtener información sobre los requisitos de configuración, consulte [Señalización SIP: FQDN](#sip-signaling-fqdns).|
|Direcciones IP y puertos de firewall para medios de enrutamiento directo |El SBC se comunica a los siguientes servicios en la nube:<br/><br/>Proxy SIP, que controla la señalización<br/>Procesador multimedia, que controla los medios, excepto cuando la omisión de medios está activada<br/><br/>Estos dos servicios tienen direcciones IP independientes en Microsoft Cloud, que se describen más adelante en este documento.<br/><br/>Para obtener más información, consulte la [sección de Microsoft Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) en [Direcciones URL e intervalos de direcciones IP](/office365/enterprise/urls-and-ip-address-ranges). |
|Perfil de transporte multimedia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Puertos y direcciones IP de firewall para medios de Microsoft Teams |Para obtener más información, vea [Direcciones URL e intervalos de direcciones IP](/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Concesión de licencias y otros requisitos 

Los usuarios de Enrutamiento directo deben tener las siguientes licencias asignadas en Microsoft 365: 

- Microsoft Phone System
- Microsoft Teams + Skype Empresarial Plan 2, si se incluye en las licencias
- Audioconferencia de Microsoft (lea las notas y el párrafo siguiente para ver ejemplos específicos sobre cuándo se necesita esta licencia).

> [!NOTE]
> Skype Empresarial plan no debe quitarse de ningún contrato de licencia donde se incluya. 
> 
> [!IMPORTANT]
> Los usuarios de GCC High y DoD deben deshabilitar cualquier licencia de Audioconferencia incluida en G5 y esperar a habilitar cualquier Audioconferencia hasta que el enrutamiento directo se haya configurado por completo. Los usuarios deben tener los números de teléfono de acceso telefónico local configurados y un teclado de marcado que funcione antes de habilitar las licencias de Audioconferencia. Consulte [Audioconferencia con enrutamiento directo para GCC High y DoD](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) para obtener más información.


> [!IMPORTANT]
>  Si desea agregar participantes externos a reuniones programadas, ya sea marcando para ellos o proporcionando el número de acceso telefónico local, se requiere la licencia de audioconferencia.
> Para GCC High y DoD, no asigne una licencia de Audioconferencia a los usuarios de G5. Para los usuarios de G3, no asigne una licencia de Audioconferencia hasta que Direct Routing esté completamente configurado y el usuario tenga un teclado de marcado que funcione.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalación de llamadas ad hoc y licencia de Audioconferencia

Un usuario de Teams puede iniciar una llamada de Teams a RTC o de Teams a Teams uno a uno y agregar a un participante de RTC. Este escenario se denomina conferencia ad hoc. La ruta que tome la llamada depende de si el usuario que escala la llamada tiene asignada o no una licencia de Audioconferencia de Microsoft:

- **Si el usuario de Teams que escala la llamada tiene asignada una licencia de Audioconferencia de Microsoft**, el aumento se produce a través del servicio De audioconferencia de Microsoft. El participante remoto de RTC al que se invita a la llamada existente recibe una notificación sobre la llamada entrante y ve el número del puente de Microsoft asignado al usuario de Teams que inició la escalación.

- **Si el usuario de Teams que escala la llamada no tiene asignada la licencia de Audioconferencia de Microsoft**, el escalado se produce a través de un controlador de borde de sesión conectado a la interfaz enrutamiento directo. El participante remoto de RTC al que se invita a la llamada recibe una notificación sobre la llamada entrante y ve el número del usuario de Teams que inició la escalación. El SBC específico usado para la escalada se define mediante la directiva de enrutamiento del usuario. 

Debe asegurarse de lo siguiente:
 
- CsOnlineVoiceRoutingPolicy está asignado al usuario. 

- Permitir llamadas privadas está habilitado en el nivel de inquilino de Microsoft Teams. 

Direct Routing también admite usuarios con licencia para Microsoft Calling Plan. El sistema telefónico con plan de llamadas puede enrutar algunas llamadas usando la interfaz de enrutamiento directo. Sin embargo, los números de teléfono de los usuarios deben adquirirse en línea o transferirse a Microsoft.  

La combinación de plan de llamadas y conectividad de enrutamiento directo para el mismo usuario es opcional, pero podría ser útil. Por ejemplo, cuando al usuario se le asigna un plan de llamadas de Microsoft pero quiere enrutar algunas llamadas con el SBC. Uno de los escenarios más comunes es las llamadas a PBX de terceros.  Con PBX de terceros, todas las llamadas, excepto las llamadas a los teléfonos conectados a ese PBX, se enrutan mediante El plan de llamadas de Microsoft, pero las llamadas a los teléfonos conectados a PBX de terceros van al SBC y, por lo tanto, permanecen dentro de la red empresarial y no de la RTC. 

Para obtener más información sobre las licencias de Phone System, consulte [Sacar el máximo partido de Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) y [Opciones de planes](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) y [licencias complementarias de Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="supported-end-points"></a>Puntos finales admitidos 

Puede usarse como punto final:

- Cualquier cliente de Teams. 

- Teléfonos de área común. Consulte [Configurar teléfonos de área común para Microsoft Teams](./set-up-common-area-phones.md). No necesita una licencia del plan de llamadas al configurar un teléfono de área común con enrutamiento directo.

- Skype Empresarial teléfonos de 3PIP. Vea [el soporte técnico de teléfonos Skype Empresarial (3PIP) con Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nombres de dominio SBC

El nombre de dominio SBC debe ser de uno de los nombres registrados en Dominios del inquilino. No puede usar el \*espacio empresarial .onmicrosoft.com para el nombre FQDN del SBC.

En la tabla siguiente se muestran ejemplos de nombres DNS registrados para el inquilino, si el nombre se puede usar como FQDN para el SBC y ejemplos de nombres FQDN válidos:

|Nombre DNS|Puede usarse para FQDN de SBC|Ejemplos de nombres FQDN|
|:--- |:--- |:--- |
contoso.com|Sí|**Nombres válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|No|No se admite el uso de dominios *.onmicrosoft.com para nombres SBC

Suponga que desea usar un nuevo nombre de dominio. Por ejemplo, el inquilino tiene contoso.com como un nombre de dominio registrado en el inquilino y desea usar sbc1.sip.contoso.com. Antes de poder emparejar un SBC con el nombre sbc1.sip.contoso.com, debe registrar el nombre de dominio sip.contoso.com en Dominios del espacio empresarial. Si intenta emparejar un SBC con sbc1.sip.contoso.com antes de registrar el nombre de dominio, recibirá el siguiente error: "No se puede usar el dominio "sbc1.sip.contoso.com" ya que no se configuró para este inquilino".
Después de agregar el nombre de dominio, también debe crear un usuario con UPN user@sip.contoso.com y asignar una licencia de Teams. El aprovisionamiento completo del nombre de dominio puede tardar hasta 24 horas después de agregarlo a dominios del inquilino, se crea un usuario con un nombre nuevo y se le asigna una licencia. 

Es posible que una empresa tenga varios espacios de direcciones SIP en un inquilino. Por ejemplo, una compañía podría tener contoso.com como un espacio de direcciones SIP y fabrikam.com como el segundo espacio de direcciones SIP. Algunos usuarios tienen user@contoso.com de direcciones y otros tienen user@fabrikam.com de direcciones. 

El SBC solo necesita un FQDN y puede atender a los usuarios desde cualquier espacio de direcciones en el espacio empresarial emparejado. Por ejemplo, un SBC con el nombre sbc1.contoso.com puede recibir y enviar el tráfico RTC para los usuarios con direcciones user@contoso.com y user@fabrikam.com siempre y cuando estos espacios de direcciones SIP se registren en el mismo espacio empresarial.  

 > [!NOTE]
 > El FQDN de SBC en Azure Communication Services enrutamiento directo debe ser diferente del FQDN de SBC en el enrutamiento directo de Teams.
  
## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado de confianza público para el SBC

Microsoft recomienda solicitar el certificado para el SBC generando una solicitud de firma de certificación (CSR). Para obtener instrucciones específicas sobre cómo generar un CSR para un SBC, consulte las instrucciones de interconexión o la documentación proporcionada por sus proveedores de SBC. 

> [!NOTE]
> La mayoría de las entidades emisoras de certificados (CA) requieren que el tamaño de la clave privada sea como mínimo 2048. Tenga esto en cuenta al generar el CSR.

El certificado debe tener el FQDN de SBC como el nombre común (CN) o el campo de nombre alternativo del asunto (SAN).

Como alternativa, enrutamiento directo admite un carácter comodín en el CN y/o SAN, y el carácter comodín debe ajustarse a [RFC HTTP Over TLS](https://tools.ietf.org/html/rfc2818#section-3.1) estándar. Un ejemplo sería el uso \*de .contoso.com que coincidiría con el sbc.contoso.com FQDN de SBC, pero no coincidiría con sbc.test.contoso.com.

La interfaz SIP de enrutamiento directo solo confiará en los certificados firmados por entidades emisoras de certificados (CA) que forman parte del Programa de certificados raíz de confianza de Microsoft. Asegúrese de que su certificado SBC está firmado por una CA que forma parte del programa y de que la extensión de uso de claves extendida (EKU) del certificado incluye autenticación de servidor.
Más información: [Requisitos del programa - Programa raíz de confianza de Microsoft](/security/trusted-root/program-requirements)
  
[Lista de certificados de CA incluida](https://ccadb-public.secure.force.com/microsoft/IncludedCACertificateReportForMSFT)
  
 Para el enrutamiento directo en Office 365 entornos GCCH y DoD, el certificado debe generarlo una de las siguientes entidades emisoras de certificados raíz:

- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> Si se habilita el soporte de Mutual TLS (MTLS) para la conexión de Teams en el SBC, debe instalar la raíz cybertrust de Baltimore y los certificados de DigiCert Global Root G2 en el almacén raíz de confianza de SBC del contexto tls de Teams. (Esto se debe a que los certificados de servicio de Microsoft usan uno de estos dos certificados raíz). Para descargar estos certificados raíz, consulte [Office 365 Cadenas de cifrado](/microsoft-365/compliance/encryption-office-365-certificate-chains). Para obtener más información, vea [Cambios de certificados de Office TLS](/microsoft-365/compliance/encryption-office-365-tls-certificates-changes).

## <a name="sip-signaling-fqdns"></a>Señalización SIP: FQDN 

Direct Routing se ofrece en los siguientes entornos:

- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Obtenga más información sobre [Office 365 y entornos gubernamentales de EE. UU.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) como GCC, GCC High y DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Entornos GCC de Microsoft 365, Office 365 y Office 365

Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:

- **sip.pstnhub.microsoft.com** , FQDN global, debe probarse primero. Cuando el SBC envía una solicitud para resolver este nombre, los servidores DNS de Microsoft Azure devuelven una dirección IP que apunta al centro de datos de Azure principal asignado al SBC. La asignación se basa en métricas de rendimiento de los centros de datos y la proximidad geográfica al SBC. La dirección IP devuelta corresponde al FQDN principal.

- **sip2.pstnhub.microsoft.com** ( FQDN secundario ) se asigna geográficamente a la región de segunda prioridad.

- **sip3.pstnhub.microsoft.com** ( FQDN terciario ) se asigna geográficamente a la tercera región de prioridad.

La colocación de estos tres FQDN en orden es necesaria para:

- Ofrezca una experiencia óptima (menos cargada y más cercana al centro de datos SBC asignado consultando el primer FQDN).

- Proporcionar conmutación por error cuando se establece la conexión desde un SBC a un centro de datos que está experimentando un problema temporal. Para obtener más información, consulte [mecanismo de conmutación por error](#failover-mechanism-for-sip-signaling) a continuación.  

Los FQDN (sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com y sip3.pstnhub.microsoft.com) se resolverán en direcciones IP desde las siguientes subredes:

- 52.112.0.0/14
- 52.120.0.0/14

Debe abrir puertos para todos estos intervalos de direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.

### <a name="office-gcc-dod-environment"></a>Entorno de DD de GCC de Office

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.dod.teams.microsoft.us** : FQDN global. Como el entorno de DoD Office 365 existe solo en los centros de datos de Ee. UU., no hay FQDN secundarios y terciarios.

El sip.pstnhub.dod.teams.microsoft.us fqdn se resolverá en una dirección IP desde la siguiente subred:

- 52.127.64.0/21

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.gov.teams.microsoft.us** : FQDN global. Como el entorno GCC High existe solo en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

El sip.pstnhub.gov.teams.microsoft.us fqdn se resolverá en una dirección IP desde la siguiente subred:

- 52.127.88.0/21

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.

## <a name="sip-signaling-ports"></a>Señalización SIP: puertos

Debe usar los puertos siguientes para Microsoft 365 o Office 365 entornos en los que se ofrece enrutamiento directo:

- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Tráfico|De|Hasta|Puerto de origen|Puerto de destino|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|Sbc|1024 – 65535|Definido en el SBC (para Office 365 GCC High/DoD sólo debe utilizarse el puerto 5061)|
SIP/TLS|Sbc|SIP Proxy|Definido en el SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de conmutación por error para la señalización SIP

El SBC realiza una consulta DNS para resolver sip.pstnhub.microsoft.com. Según la ubicación de SBC y las métricas de rendimiento del centro de datos, se selecciona el centro de datos principal. Si el centro de datos principal experimenta un problema, el SBC intentará el sip2.pstnhub.microsoft.com, que se resuelve en el segundo centro de datos asignado, y, en el caso poco frecuente de que los centros de datos de dos regiones no estén disponibles, el SBC vuelve a escribir el último FQDN (sip3.pstnhub.microsoft.com), que proporciona la IP del centro de datos terciario.

La tabla siguiente resume las relaciones entre los centros de datos primario, secundario y terciario:

|Si el centro de datos principal es|EMEA|NOAM|ASIA|
|:--- |:--- |:--- |:--- |
|El centro de datos secundario (sip2.pstnhub.microsoft.com)|Nos|Ue|Nos|
|El centro de datos terciario (sip3.pstnhub.microsoft.com)|ASIA|ASIA|Ue|
|||||

## <a name="media-traffic-port-ranges"></a>Tráfico multimedia: Intervalos de puertos
Tenga en cuenta que los requisitos siguientes se aplican si desea implementar enrutamiento directo sin omisión multimedia. Para conocer los requisitos de firewall para la omisión de medios, consulte [Planear la omisión de medios con enrutamiento directo](./direct-routing-plan-media-bypass.md).

El tráfico multimedia fluye hacia y desde un servicio independiente en Microsoft Cloud. Los intervalos de direcciones IP para el tráfico multimedia son los siguientes.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Entornos GCC de Microsoft 365, Office 365 y Office 365

- 52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (direcciones IP de 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>entorno de Office 365 DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC High Environment

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervalo de puertos (aplicable a todos los entornos)
El rango de puertos de los procesadores multimedia se muestra en la tabla siguiente: 

|Tráfico|De|Hasta|Puerto de origen|Puerto de destino|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Procesador multimedia|Sbc|3478-3481 y 49152 – 53247|Definido en el SBC|
|UDP/SRTP|Sbc|Procesador multimedia|Definido en el SBC|3478-3481 y 49152 – 53247|

  > [!NOTE]
  > Microsoft recomienda al menos dos puertos por llamada simultánea en el SBC.


## <a name="media-traffic-media-processors-geography"></a>Tráfico multimedia: procesadores multimedia geography

El tráfico multimedia fluye a través de componentes denominados procesadores multimedia. Los procesadores multimedia se colocan en los mismos centros de datos que los servidores proxy SIP:

- NOAM (US South Central, dos en los centros de datos oeste y este de EE. UU.)
- Europa (centro de datos del Sur del Reino Unido, Francia Central, Amsterdam y Dublín)
- Asia (centro de datos de Singapur)
- Japón (centros de datos de JP East y West)
- Australia (centros de datos au east y southeast)
- LATINOAMÉRICA (Brasil Sur)

## <a name="media-traffic-codecs"></a>Tráfico multimedia: códecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Leg between SBC and Cloud Media Processor or Microsoft Teams client

Se aplica tanto a casos de omisión multimedia como a casos que no son de omisión.

La interfaz Enrutamiento directo de la pierna entre el controlador de borde de sesión y el procesador de medios en la nube (sin omisión multimedia) o entre el cliente de Teams y el SBC (si la omisión de medios está habilitada) puede usar los siguientes códecs:

- Omisión no multimedia (SBC a Cloud Media Processor): SILK, G.711, G.722, G.729
- Omisión de medios (SBC al cliente de Teams): SILK, G.711, G.722, G.729

Puede forzar el uso del códec específico en el controlador de borde de sesión excluyendo los códecs no deseados de la oferta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Pierna entre el cliente de Microsoft Teams y el procesador de medios en la nube

Solo se aplica al caso de omisión no multimedia. Con omisión de medios, los elementos multimedia fluyen directamente entre el cliente de Teams y el SBC.

En el tramo entre el procesador de medios en la nube y el cliente de Microsoft Teams, se usa SILK o G.722. La elección del códec en esta pierna se basa en algoritmos de Microsoft, que tienen en cuenta varios parámetros. 

  > [!NOTE]
  > No se admite el redireccionamiento de medios. Durante una llamada de Enrutamiento directo, si el CLS envía una nueva dirección IP de medios a Enrutamiento directo de Teams, aunque se negocia en la señalización SIP, los medios nunca se envían a la nueva dirección IP desde Enrutamiento directo de Teams.

## <a name="supported-session-border-controllers-sbcs"></a>Controladores de borde de sesión compatibles (SBCs)

Microsoft solo admite SBCs certificados para emparejarse con Direct Routing. Dado que Telefonía IP empresarial es fundamental para las empresas, Microsoft ejecuta pruebas intensivas con los SBC seleccionados y trabaja con los proveedores de SBC para garantizar que los dos sistemas sean compatibles. 

Los dispositivos que se han validado se muestran como Certificados para el enrutamiento directo de Teams. Los dispositivos certificados están garantizados para funcionar en todos los escenarios. 

Para obtener más información sobre los SBCs compatibles, consulte [Controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).

## <a name="support-boundaries"></a>Límites de soporte técnico
Microsoft solo admite un sistema telefónico con enrutamiento directo cuando se usa con dispositivos certificados. En caso de problemas, debe ponerse en contacto con el servicio de atención al cliente del proveedor de SBC  Si es necesario, el proveedor de CLS remitirá el problema a Microsoft a través de canales internos. Microsoft se reserva el derecho a rechazar casos de soporte técnico de dispositivos no certificados conectados al Sistema telefónico a través del Enrutamiento directo. Si Microsoft determina que el problema de Enrutamiento directo de un cliente está relacionado con el dispositivo de un proveedor de CLS, el cliente deberá ponerse en contacto con el proveedor de CLS para obtener soporte técnico.
 
## <a name="see-also"></a>Vea también

[Configurar el enrutamiento directo](direct-routing-configure.md)
