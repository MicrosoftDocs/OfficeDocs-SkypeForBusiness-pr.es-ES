---
title: Planear el enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
description: Obtenga información sobre cómo el enrutamiento directo de Microsoft Phone System le permite conectar un controlador de borde de sesión (SBC) proporcionado por el cliente a Microsoft Phone System.
ms.openlocfilehash: 77757cf76215dbed0b3ec572b5f1f57120551d86
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923832"
---
# <a name="plan-direct-routing"></a>Planear el enrutamiento directo

> [!Tip]
> Vea la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearlo y cómo implementarlo: enrutamiento directo [en Microsoft Teams](https://aka.ms/teams-direct-routing)

El enrutamiento directo de Microsoft Phone System le permite conectar un controlador de borde de sesión (SBC) compatible proporcionado por el cliente a Microsoft Phone System.  Con esta capacidad, por ejemplo, puede configurar la conectividad de la red telefónica conmutada (RTC) local con el cliente de Microsoft Teams, como se muestra en el siguiente diagrama: 

![Diagrama que muestra la configuración de la conectividad con RTC local](media/PlanDirectRouting1-PSTNwithTeams.png "Configuración de la conectividad con RTC local con el cliente de Microsoft Teams")

  > [!NOTE]
  > Skype Empresarial Online también le permite emparejar un SBC proporcionado por el cliente, pero esto requiere una implementación local de Skype Empresarial Server o una edición especial de Skype Empresarial, denominada Cloud Connector, entre la SBC y Microsoft Cloud. Este escenario se denomina voz híbrida. En cambio, el enrutamiento directo permite una conexión directa entre el SBC compatible y Microsoft Cloud.

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [enrutamiento directo.](direct-routing-landing-page.md) 

Con el enrutamiento directo, puede conectar su SBC a casi cualquier tronco de telefonía o interconectado con equipos RTC de terceros. El enrutamiento directo le permite: 

- Use prácticamente cualquier tronco RTC con Microsoft Phone System. 
- Configure la interoperabilidad entre equipos de telefonía propiedad del cliente, como una central de conmutación (PBX) privada de terceros, dispositivos analógicos y Microsoft Phone System.

Microsoft también ofrece soluciones de voz todo en la nube, como Plan de llamadas. Sin embargo, una solución de voz híbrida podría ser la mejor para su organización si: 

- El plan de llamadas de Microsoft no está disponible en tu país. 
- Su organización requiere conexión a dispositivos analógicos de terceros, centros de llamadas, entre otros. 
- Su organización tiene un contrato existente con un operador RTC.

El enrutamiento directo también es compatible con los usuarios que tienen la licencia adicional para el plan de llamadas de Microsoft. Para obtener más información, vea [Sistema telefónico y Planes de llamadas.](calling-plan-landing-page.md) 

Con enrutamiento directo, cuando los usuarios participan en una conferencia programada, el número de acceso telefónico local lo proporciona el servicio de Audioconferencia de Microsoft, que requiere una licencia adecuada.  Al realizar llamadas, el servicio de Audioconferencia de Microsoft realiza la llamada usando las capacidades de llamadas en línea, que requieren licencias adecuadas. (Tenga en cuenta que si un usuario no tiene una licencia de Audioconferencia de Microsoft, la llamada se enruta mediante enrutamiento directo). Para obtener más información, [vea Reuniones en línea con Teams.](https://products.office.com/microsoft-teams/online-meeting-solutions) 
 
Planear la implementación de enrutamiento directo es esencial para una implementación correcta. En este artículo se describen los requisitos de infraestructura y licencias, y se proporciona información sobre la conectividad SBC: 

- [Requisitos de infraestructura](#infrastructure-requirements)
- [Licencias y otros requisitos](#licensing-and-other-requirements)
- [Nombres de dominio SBC](#sbc-domain-names)
- [Certificado de confianza público para la SBC](#public-trusted-certificate-for-the-sbc)
- [Señalización SIP: FQDN](#sip-signaling-fqdns)
- [Señalización SIP: puertos](#sip-signaling-ports)
- [Tráfico multimedia: intervalos de puertos](#media-traffic-port-ranges)
- [Controladores de borde de sesión compatibles (SBCs)](#supported-session-border-controllers-sbcs)

Para obtener información detallada sobre cómo configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura
Los requisitos de infraestructura para los SBC, dominios y otros requisitos de conectividad de red admitidos para implementar enrutamiento directo se enumeran en la tabla siguiente:  

|Requisito de infraestructura|Necesita lo siguiente|
|:--- |:--- |
|Controlador de borde de sesión (SBC)|SBC compatible. Para obtener más información, vea [los SBC compatibles.](#supported-session-border-controllers-sbcs)|
|Troncos de telefonía conectados a la SBC|Uno o varios troncos de telefonía conectados a la SBC. En un extremo, el SBC se conecta al sistema telefónico de Microsoft a través del enrutamiento directo. La SBC también puede conectarse a entidades de telefonía de terceros, como PBX, adaptadores de telefonía analógica, entre otros. Cualquier opción de conectividad con RTC conectada a la SBC funcionará. (Para obtener información sobre la configuración de los troncos RTC en la SBC, consulte a los proveedores de troncos o proveedores de troncos SBC).|
|Organización de Microsoft 365 u Office 365|Una organización de Microsoft 365 u Office 365 que usa para hospedar a los usuarios de Microsoft Teams, así como la configuración y la conexión a la SBC.|
|Registrador de usuarios|El usuario debe estar en Microsoft 365 u Office 365.<br/>Si su compañía tiene un entorno local de Skype Empresarial o Lync con conectividad híbrida a Microsoft 365 u Office 365, no puede habilitar la voz en Teams para un usuario que se encuentra en local.<br/><br/>Para comprobar el registrador de un usuario, use el siguiente cmdlet de PowerShell de Skype Empresarial Online:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>El resultado del cmdlet debería mostrar lo siguiente:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Dominios|Uno o más dominios agregados a sus organizaciones de Microsoft 365 u Office 365.<br/><br/>Tenga en cuenta que no puede usar el dominio predeterminado, \* .onmicrosoft.com, que se crea automáticamente para su espacio empresarial.<br/><br/>Para ver los dominios, puede usar el siguiente cmdlet de PowerShell de Skype Empresarial Online:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obtener más información sobre dominios y organizaciones de Microsoft 365 u Office 365, vea Preguntas más frecuentes [sobre dominios.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|Dirección IP pública para la SBC|Una dirección IP pública que se puede usar para conectarse a la SBC. Según el tipo de SBC, la SBC puede usar NAT.|
|Nombre de dominio completo (FQDN) para la SBC|Un FQDN para la SBC, donde la parte del dominio del FQDN es uno de los dominios registrados en su organización de Microsoft 365 u Office 365. Para obtener más información, vea [Nombres de dominio SBC.](#sbc-domain-names)|
|Entrada DNS pública para la SBC |Una entrada DNS pública asigna el FQDN de SBC a la dirección IP pública. |
|Certificado de confianza público para la SBC |Un certificado para que SBC se utilice para todas las comunicaciones con enrutamiento directo. Para obtener más información, vea [Certificado de confianza público para la SBC.](#public-trusted-certificate-for-the-sbc)|
|Puntos de conexión para enrutamiento directo |Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:<br/><br/>`sip.pstnhub.microsoft.com` – FQDN global, debe intentarse primero.<br/>`sip2.pstnhub.microsoft.com` - FQDN secundario, se asigna geográficamente a la región de segunda prioridad.<br/>`sip3.pstnhub.microsoft.com` - FQDN terciario, se asigna geográficamente a la tercera región de prioridad.<br/><br/>Para obtener información sobre los requisitos de configuración, [consulte Señalización SIP: FQDN.](#sip-signaling-fqdns)|
|Puertos y direcciones IP del firewall para medios de enrutamiento directo |La SBC se comunica a los siguientes servicios en la nube:<br/><br/>Proxy SIP, que controla la señalización<br/>Procesador de medios, que controla los medios, excepto cuando la omisión de medios está<br/><br/>Estos dos servicios tienen direcciones IP independientes en Microsoft Cloud, como se describe más adelante en este documento.<br/><br/>Para obtener más información, consulte la sección [de Microsoft Teams en](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) URL e [intervalos de direcciones IP.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|Perfil de transporte multimedia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Direcciones IP y puertos del firewall para los archivos multimedia de Microsoft Teams |Para obtener más información, vea [direcciones URL e intervalos de direcciones IP.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>Licencias y otros requisitos 

Los usuarios de enrutamiento directo deben tener asignadas las siguientes licencias en Microsoft 365 u Office 365: 

- Microsoft Phone System. 
- Microsoft Teams + Skype Empresarial Plan 2, si se incluye en las licencias.
- Audioconferencia de Microsoft (lea las notas y el párrafo siguiente para ver ejemplos específicos sobre cuándo se requiere la licencia).

> [!NOTE]
> El plan de Skype Empresarial no debe quitarse de ningún contrato de licencia donde se incluya. 


> [!IMPORTANT]
>  En el caso de que quiera agregar participantes externos a las reuniones programadas, ya sea mediante una llamada a ellos o proporcionando el número de acceso telefónico local, se requiere la licencia de audioconferencia.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalación de llamadas ad hoc y licencia de Audioconferencia

Un usuario de Teams puede iniciar una llamada de Teams a RTC o de Teams a Teams y agregar un participante de RTC a la llamada. Este escenario se denomina conferencia ad hoc. La ruta que toma la llamada depende de si el usuario que escala la llamada tiene una licencia de Audioconferencia de Microsoft asignada o no:

- Si el usuario de Teams que escala la llamada tiene asignada una licencia de Audioconferencia de Microsoft, el escalamiento se produce a través del servicio De Audioconferencia de Microsoft. El participante remoto de RTC al que se le invite a la llamada existente recibe una notificación sobre la llamada entrante y ve el número del puente de Microsoft asignado al usuario de Teams que inició la escala.
- Si el usuario de Teams que escala la llamada no tiene asignada la licencia de Audioconferencia de Microsoft, la escalación se produce a través de un controlador de borde de sesión conectado a la interfaz de enrutamiento directo. El participante remoto de RTC al que se le invite a la llamada recibe una notificación sobre la llamada entrante y ve el número del usuario de Teams que ha iniciado el escalamiento. La SBC específica usada para la escala se define mediante la directiva de enrutamiento del usuario. 


Además, debe asegurarse de lo siguiente:
 
- CsOnlineVoiceRoutingPolicy se ha asignado al usuario. 
- Permitir llamadas privadas está habilitado en el nivel de inquilino de Microsoft Teams. 

El enrutamiento directo también admite usuarios con licencia para Microsoft Calling Plan. Microsoft Phone System con plan de llamadas puede enrutar algunas llamadas usando la interfaz de enrutamiento directo. Sin embargo, los números de teléfono de los usuarios deben adquirirse en línea o se deben realizar por correo electrónico a Microsoft.  

La combinación de la conectividad del plan de llamadas y el enrutamiento directo para el mismo usuario es opcional, pero puede ser útil (por ejemplo, cuando se asigna al usuario un plan de llamadas de Microsoft pero quiere enrutar algunas llamadas mediante SBC). Uno de los escenarios más comunes son las llamadas a PBX de terceros.  Con PBX de terceros, todas las llamadas, excepto las llamadas a los teléfonos conectados a dicho PBX, se enruta con el plan de llamadas de Microsoft, pero las llamadas a los teléfonos conectados a PBX de terceros van al SBC y, por lo tanto, permanecen dentro de la red empresarial y no en la RTC. 

Para obtener más información sobre las licencias de Sistema telefónico, vea [Sacar el máximo partido de las opciones de Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) y [Plan.](https://technet.microsoft.com/library/office-365-plan-options.aspx) 

Para obtener más información sobre las licencias de Sistema telefónico, consulte [Licencias de complementos de Microsoft Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) 

## <a name="supported-end-points"></a>Puntos finales admitidos 

Puede usar como un punto final:

- Cualquier cliente de Teams. 
- Teléfonos de área comunes. Consulte [Configurar la licencia del teléfono de área común para Microsoft Teams.](https://docs.microsoft.com/microsoftteams/set-up-common-area-phones) Tenga en cuenta que no necesita una licencia de plan de llamadas al configurar un teléfono de área común con enrutamiento directo.
- Teléfonos 3PIP de Skype Empresarial. Ver [la compatibilidad con teléfonos de Skype Empresarial (3PIP) con Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nombres de dominio SBC

El nombre de dominio SBC debe ser de uno de los nombres registrados en Dominios del inquilino. No puede usar el \* inquilino .onmicrosoft.com para el nombre FQDN de la SBC.

En la tabla siguiente se muestran ejemplos de nombres DNS registrados para el inquilino, si el nombre puede usarse como FQDN para la SBC y ejemplos de nombres FQDN válidos:

|Nombre DNS|Se puede usar para FQDN SBC|Ejemplos de nombres FQDN|
|:--- |:--- |:--- |
contoso.com|Sí|**Nombres válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|No|El uso de dominios *.onmicrosoft.com no es compatible con nombres SBC

Suponga que desea usar un nuevo nombre de dominio. Por ejemplo, el inquilino tiene contoso.com como un nombre de dominio registrado en su inquilino y desea usar sbc1.sip.contoso.com. Antes de poder emparejar un SBC con el nombre sbc1.sip.contoso.com, debe registrar el nombre de dominio sip.contoso.com dominios en su inquilino. Si intenta emparejar un SBC con sbc1.sip.contoso.com antes de registrar el nombre de dominio, recibirá el siguiente error: "No se puede usar el dominio "sbc1.sip.contoso.com" al no estar configurado para este inquilino".
Después de agregar el nombre de dominio, también debe crear un usuario con UPN y user@sip.contoso.com una licencia de Teams. El aprovisionamiento completo del nombre de dominio puede tardar hasta 24 horas después de que se haya agregado a Dominios del inquilino, se cree un usuario con un nombre nuevo y se asigne una licencia al usuario. 

Es posible que una empresa tenga varios espacios de direcciones SIP en un inquilino. Por ejemplo, es posible que una empresa contoso.com un espacio de direcciones SIP y que fabrikam.com como el segundo espacio de direcciones SIP. Algunos usuarios tienen direcciones user@contoso.com y otros tienen direcciones de user@fabrikam.com. 

La SBC solo necesita un FQDN y puede atender a los usuarios desde cualquier espacio de direcciones en el espacio empresarial emparejado. Por ejemplo, una SBC con el nombre sbc1.contoso.com puede recibir y enviar el tráfico RTC de los usuarios con direcciones user@contoso.com y user@fabrikam.com siempre que estos espacios de direcciones SIP se registren en el mismo espacio empresarial.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado de confianza público para la SBC

Microsoft recomienda solicitar el certificado para el SBC generando una solicitud de firma de certificación (CSR). Para obtener instrucciones específicas sobre cómo generar un CSR para un SBC, consulte las instrucciones de sistema o documentación proporcionadas por los proveedores de SBC. 

  > [!NOTE]
  > La mayoría de las autoridades de certificación (CA) requieren que el tamaño de clave privada sea como mínimo 2048. Tenga esto en cuenta al generar el CSR.

El certificado debe tener el FQDN SBC como el nombre común (CN) o el campo de nombre alternativo del asunto (SAN). El certificado debe emitirse directamente desde una entidad emisora de certificados, no desde un proveedor intermedio.

Como alternativa, el enrutamiento directo admite un carácter comodín en CN o SAN, y el carácter comodín debe ajustarse a [RFC HTTP sobre TLS estándar.](https://tools.ietf.org/html/rfc2818#section-3.1) Un ejemplo sería el uso de .contoso.com que coincidiría con el FQDN de SBC sbc.contoso.com pero no coincidiría con \* sbc.test.contoso.com.

El certificado debe ser generado por una de las siguientes autoridades de certificado raíz:

- Desconfiar de
- Raíz de entidad de certificación externa de AddTrust
- Root de CyberTrust de Baltimore*
- Buypass
- Cibertrust
- Entidad de certificación principal pública de clase 3
- Ca raíz segura de Comodo
- Deutsche Telekom 
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- Entrust
- GlobalSign
- Go Daddy
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Raíz móvil de Sylis Enterprise para Microsoft 
- SwissSign
- Thawte Timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International DeutscheH (Deutsche Telekom)
- QuoVadis

Para el enrutamiento directo en entornos GCCH y DoD de Office 365, el certificado debe generarlo una de las siguientes autoridades de certificado raíz:
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> *Si se habilita la compatibilidad con TLS mutuo (MTLS) para la conexión de Teams en el SBC, debe instalar el certificado raíz de Baltimore CyberTrust en el almacén raíz de confianza SBC del contexto tls de Teams. (Esto se debe a que los certificados de servicio de Microsoft usan el certificado raíz de Baltimore). Para descargar el certificado raíz de Baltimore, consulte Cadenas de cifrado de [Office 365.](https://docs.microsoft.com/microsoft-365/compliance/encryption-office-365-certificate-chains)

Microsoft está trabajando en agregar entidades emisoras de certificados adicionales en función de las solicitudes de los clientes. 

## <a name="sip-signaling-fqdns"></a>Señalización SIP: FQDN 

El enrutamiento directo se ofrece en los siguientes entornos:
- Microsoft 365 u Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Obtenga más información [sobre los entornos de Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) y el gobierno de ESTADOS UNIDOS, como GCC, GCC High y DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Entornos GCC de Microsoft 365, Office 365 y Office 365

Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:

- **sip.pstnhub.microsoft.com** tiene que probarse primero el FQDN global. Cuando la SBC envía una solicitud para resolver este nombre, los servidores DNS de Microsoft Azure devuelven una dirección IP que apunta al centro de datos de Azure principal asignado a la SBC. La asignación se basa en las métricas de rendimiento de los centros de datos y la proximidad geográfica al SBC. La dirección IP devuelta corresponde al FQDN principal.
- **sip2.pstnhub.microsoft.com** – FQDN secundario – se asigna geográficamente a la segunda región de prioridad.
- **sip3.pstnhub.microsoft.com** – FQDN terciario - se asigna geográficamente a la tercera región de prioridad.

Colocar estos tres FQDN en orden es necesario para:

- Proporcione una experiencia óptima (menos cargada y más cercana al centro de datos SBC asignado consultando el primer FQDN).
- Proporcionar conmutación por error cuando se establece la conexión desde un SBC a un centro de datos que está experimentando un problema temporal. Para obtener más información, vea a continuación el [mecanismo de conmutación por error.](#failover-mechanism-for-sip-signaling)  

Los FQDN (sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com y sip3.pstnhub.microsoft.com) se resolverán en una de las siguientes direcciones IP:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70
- 52.114.16.74
- 52.114.20.29

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si el firewall admite nombres DNS, el nombre **sip-all.pstnhub.microsoft.com** FQDN se resuelve con todas estas direcciones IP. 

> [!IMPORTANT]
>  Como parte de la expansión y mejora del servicio de enrutamiento directo de Teams, hemos implementado nuevas instancias de infraestructura de enrutamiento directo en Australia. Esto se refleja en dos direcciones IP adicionales (52.114.16.74 y 52.114.20.29) a las que se resolverán los siguientes FQDN para los clientes australianos: sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com y sip3.pstnhub.microsoft.com. Debe agregar estas dos direcciones IP (52.114.16.74 y 52.114.20.29) a sus listas de control de acceso (ACL) IP y abrir puertos para todas estas direcciones IP en el firewall con el fin de permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.

### <a name="office-365-gcch-and-dod-environment"></a>Entorno de Office 365 GCCH y DoD

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.dod.teams.microsoft.us:** FQDN global. Como el entorno del DoD de Office 365 solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

El nombre de sip.pstnhub.dod.teams.microsoft.us FQDN se resolverá en una de las siguientes direcciones IP:

- 52.127.64.33
- 52.127.68.34

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.

### <a name="office-365-gcc-high-environment"></a>Entorno de Office 365 GCC High

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.gov.teams.microsoft.us:** FQDN global. Como el entorno de GCC High solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

El nombre sip.pstnhub.gov.teams.microsoft.us FQDN se resolverá en una de las siguientes direcciones IP:

- 52.127.88.59
- 52.127.92.64

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización. Si el firewall admite nombres DNS, el nombre **sip-all.pstnhub.gov.teams.microsoft.us** FQDN se resuelve en todas estas direcciones IP. Este FQDN también se puede usar como FQDN federado para la clasificación de llamadas entrantes.

## <a name="sip-signaling-ports"></a>Señalización SIP: puertos

Debe usar los puertos siguientes para los entornos de Microsoft 365 u Office 365 donde se ofrece enrutamiento directo:
- Microsoft 365 u Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Tráfico|De|Hasta|Puerto de origen|Puerto de destino|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Definido en el SBC (para Office 365 GCC High/DoD solo debe usarse el puerto 5061)|
SIP/TLS|SBC|SIP Proxy|Definido en la SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de conmutación por error para señalización SIP

La SBC realiza una consulta DNS para resolver sip.pstnhub.microsoft.com. Según la ubicación de SBC y las métricas de rendimiento del centro de datos, se selecciona el centro de datos principal. Si el centro de datos principal experimenta un problema, la SBC probará el sip2.pstnhub.microsoft.com, que se resuelve en el segundo centro de datos asignado y, en el caso poco frecuente, que los centros de datos de dos regiones no están disponibles, el SBC vuelve a entradas el último FQDN (sip3.pstnhub.microsoft.com), que proporciona la DIRECCIÓN IP del centro de datos terciario.

En la tabla siguiente se resumen las relaciones entre centros de datos principales, secundarios y terciarios:

|Si el centro de datos principal está|EMEA|NOAM|ASIA|
|:--- |:--- |:--- |:--- |
|El centro de datos secundario (sip2.pstnhub.microsoft.com)|EE. UU.|UE|EE. UU.|
|El centro de datos terciario (sip3.pstnhub.microsoft.com)|ASIA|ASIA|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Tráfico multimedia: intervalos de puertos
Tenga en cuenta que los requisitos siguientes se aplican si desea implementar enrutamiento directo sin omisión de medios. Para consultar los requisitos del firewall para la omisión de medios, consulte Planear la omisión de [medios con enrutamiento directo.](https://docs.microsoft.com/microsoftteams/direct-routing-plan-media-bypass)



El tráfico multimedia fluye hacia y desde un servicio independiente en La nube de Microsoft. Los intervalos de direcciones IP para el tráfico multimedia son los siguientes.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Entornos GCC de Microsoft 365, Office 365 y Office 365

- 52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (direcciones IP de 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>Entorno de Office 365 DoD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Entorno de Office 365 GCC High

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervalo de puertos (aplicable a todos los entornos)
El rango de puertos de los procesadores multimedia se muestra en la tabla siguiente: 

|Tráfico|De|Hasta|Puerto de origen|Puerto de destino|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Procesador de medios|SBC|3478-3481 y 49152- 53247|Definido en la SBC|
|UDP/SRTP|SBC|Procesador de medios|Definido en la SBC|3478-3481 y 49152- 53247|

  > [!NOTE]
  > Microsoft recomienda al menos dos puertos por llamada simultánea en la SBC.


## <a name="media-traffic-media-processors-geography"></a>Tráfico multimedia: geografía de los procesadores multimedia

El tráfico multimedia fluye a través de componentes llamados procesadores multimedia. Los procesadores multimedia se colocan en los mismos centros de datos que los servidores proxy SIP. Además, hay procesadores de medios adicionales para optimizar el flujo de medios. Por ejemplo, actualmente no tenemos un componente proxy SIP en Australia (flujos SIP a través de Singapur o Hong Kong), pero tenemos el procesador de medios localmente en Australia. La necesidad de los procesadores de medios localmente viene determinada por la latencia experimentada al enviar tráfico de larga distancia, por ejemplo, desde Australia a Singapur o Hong Kong. Aunque la latencia en el ejemplo de tráfico que fluye de Australia a Hong Kong o Singapur es aceptable para conservar la buena calidad de llamada para el tráfico SIP, para el tráfico multimedia en tiempo real no lo es.

Ubicación de los procesadores multimedia:

Ubicaciones en las que se han implementado tanto los componentes del proxy SIP como del procesador de medios:
- EE. UU. (dos en centros de datos de EE. UU. Oeste y Este de EE. UU.)
- Europa (centros de datos de Ámsterdam y Dublín)
- Asia (centros de datos de Singapur y Hong Kong)

Ubicaciones donde solo se implementan procesadores de medios (flujos SIP a través del centro de datos más cercano enumerado anteriormente):
- Japón (centros de datos de JP East y West)
- Australia (centros de datos de AUSTRALIA este y sudeste)




## <a name="media-traffic-codecs"></a>Tráfico multimedia: códecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Intervalo entre SBC y Cloud Media Processor o el cliente de Microsoft Teams.
Se aplica tanto a los casos de omisión de medios como a los de no omisión.

La interfaz de enrutamiento directo en el tramo entre el controlador de borde de sesión y el procesador de medios en la nube (sin omisión de medios) o entre el cliente de Teams y el SBC (si omisión de medios está habilitada) puede usar los códecs siguientes:

- Omisión no multimedia (SBC a procesador de medios en la nube): SILK, G.711, G.722, G.729
- Media Bypass (SBC to Teams client): SILK, G.711, G.722, G.729

Puede forzar el uso del códec específico en el controlador de borde de sesión excluyendo los códecs no deseados de la oferta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Relación entre el cliente de Microsoft Teams y el procesador de medios en la nube
Solo se aplica a casos de omisión que no son de medios. Con media bypass, los medios fluyen directamente entre el cliente de Teams y el SBC.

En el tramo entre el procesador de medios en la nube y el cliente de Microsoft Teams se utiliza SILK o G.722. La elección del códec en este tramo se basa en algoritmos de Microsoft, que tienen en cuenta varios parámetros. 


## <a name="supported-session-border-controllers-sbcs"></a>Controladores de borde de sesión compatibles (SBCs)

Microsoft solo admite las OSN certificadas para emparejar con enrutamiento directo. Dado que Telefonía IP empresarial es fundamental para las empresas, Microsoft ejecuta pruebas intensivas con los SBC seleccionados y trabaja con los proveedores de SBC para asegurarse de que los dos sistemas son compatibles. 

Los dispositivos que se han validado aparecen en la lista Certified for Teams Direct Routing. Se garantiza el funcionamiento de los dispositivos certificados en todos los escenarios. 

Para obtener más información sobre los SBC compatibles, vea Lista de controladores de [borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Consulte también

[Configurar el enrutamiento directo](direct-routing-configure.md)
