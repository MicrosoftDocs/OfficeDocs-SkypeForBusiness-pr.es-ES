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
description: Obtenga información sobre Teléfono Microsoft system direct routing le permite conectar un controlador de borde de sesión (SBC) proporcionado por el cliente compatible con Teléfono Microsoft system.
ms.openlocfilehash: b7d065cd8e89e07203d50e4e21a4ac5eb2ccd843
ms.sourcegitcommit: 4a039550bc5c3a497b6b52c7fed08cadf8268b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926762"
---
# <a name="plan-direct-routing"></a>Planear el enrutamiento directo

> [!Tip]
> Vea la siguiente sesión para obtener información sobre las ventajas de Enrutamiento [directo,](https://aka.ms/teams-direct-routing) cómo planearlo y cómo implementarlo: Enrutamiento directo en Microsoft Teams

Teléfono Microsoft System Direct Routing le permite conectar un controlador de borde de sesión (SBC) compatible y proporcionado por el cliente a Teléfono Microsoft Sistema.  Con esta capacidad, por ejemplo, puede configurar la conectividad de red telefónica conmutada (RTC) local con un cliente Microsoft Teams, como se muestra en el siguiente diagrama: 

![Diagrama que muestra la configuración de conectividad RTC local](media/PlanDirectRouting1-PSTNwithTeams.png "Configuración de conectividad RTC local con Microsoft Teams cliente")

  > [!NOTE]
  > Skype Empresarial Online también le permite emparejar un SBC proporcionado por el cliente, pero esto requiere una implementación de Skype Empresarial Server local o una edición especial de Skype Empresarial, denominada Conector en la nube, entre el SBC y Microsoft Cloud. Este escenario se conoce como voz híbrida. Por el contrario, enrutamiento directo permite una conexión directa entre el SBC compatible y Microsoft Cloud.

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que su organización haya actualizado a Teams, obtenga información sobre cómo conectar su red de telefonía local a Teams mediante [enrutamiento directo.](direct-routing-landing-page.md) 

Con enrutamiento directo, puede conectar su SBC a casi cualquier tronco de telefonía o interconectarse con equipos RTC de terceros. Enrutamiento directo le permite: 

- Use prácticamente cualquier tronco RTC con Teléfono Microsoft sistema. 
- Configure la interoperabilidad entre equipos de telefonía propiedad del cliente, como un intercambio de sucursales privado (PBX) de terceros, dispositivos analógicos y Teléfono Microsoft System.

Microsoft también ofrece soluciones de voz todo en la nube, como Plan de llamadas. Sin embargo, una solución de voz híbrida puede ser la mejor para su organización si: 

- Microsoft Calling Plan no está disponible en tu país. 
- Su organización requiere conexión a dispositivos analógicos de terceros, centros de llamadas, y así sucesivamente. 
- Su organización tiene un contrato existente con un operador RTC.

Enrutamiento directo también es compatible con los usuarios que tienen la licencia adicional para el Plan de llamadas de Microsoft. Para obtener más información, [vea Sistema telefónico y Planes de llamadas.](calling-plan-landing-page.md) 

Con enrutamiento directo, cuando los usuarios participan en una conferencia programada, el número de acceso telefónico local lo proporciona el servicio de audioconferencia de Microsoft, que requiere licencias adecuadas.  Al llamar, el servicio de audioconferencia de Microsoft coloca la llamada con las capacidades de llamadas en línea, lo que requiere licencias adecuadas. (Tenga en cuenta que si un usuario no tiene una licencia de Audioconferencia de Microsoft, la llamada se dirige a través del enrutamiento directo). Para obtener más información, vea [Reuniones en línea con Teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
Planear la implementación de Enrutamiento directo es clave para una implementación correcta. En este artículo se describen los requisitos de infraestructura y licencias y se proporciona información sobre la conectividad de SBC: 

- [Requisitos de infraestructura](#infrastructure-requirements)
- [Licencias y otros requisitos](#licensing-and-other-requirements)
- [Nombres de dominio SBC](#sbc-domain-names)
- [Certificado de confianza pública para el SBC](#public-trusted-certificate-for-the-sbc)
- [Señalización SIP: FQDN](#sip-signaling-fqdns)
- [Señalización SIP: Puertos](#sip-signaling-ports)
- [Tráfico multimedia: Intervalos de puertos](#media-traffic-port-ranges)
- [Controladores de borde de sesión (SBC) compatibles](#supported-session-border-controllers-sbcs)

Para obtener información detallada sobre cómo configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura
Los requisitos de infraestructura para los SBC, dominios y otros requisitos de conectividad de red admitidos para implementar enrutamiento directo se muestran en la tabla siguiente:  

|Requisito de infraestructura|Necesita lo siguiente|
|:--- |:--- |
|Controlador de borde de sesión (SBC)|Un SBC compatible. Para obtener más información, vea [SBC compatibles.](#supported-session-border-controllers-sbcs)|
|Troncos de telefonía conectados al SBC|Uno o varios troncos de telefonía conectados al SBC. En un extremo, el SBC se conecta al sistema Teléfono Microsoft mediante enrutamiento directo. El SBC también puede conectarse a entidades de telefonía de terceros, como PBX, adaptadores de telefonía analógica, entre otras. Cualquier opción de conectividad RTC conectada al SBC funcionará. (Para obtener información sobre la configuración de los troncos RTC en el SBC, consulte los proveedores de SBC o los proveedores troncales).|
|Microsoft 365 o Office 365 organización|Una Microsoft 365 o Office 365 que usa para hospedar sus Microsoft Teams usuarios, así como la configuración y la conexión con el SBC.|
|Registrador de usuarios|El usuario debe estar en Microsoft 365 o Office 365.<br/>Si su empresa tiene un entorno de Skype Empresarial o Lync local con conectividad híbrida a Microsoft 365 o Office 365, no puede habilitar la voz en Teams para un usuario alocudo local.<br/><br/>Para comprobar el registrador de un usuario, use la siguiente Skype Empresarial cmdlet de PowerShell en línea:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>El resultado del cmdlet debe mostrar lo siguiente:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Dominios|Uno o varios dominios agregados a Microsoft 365 o Office 365 organizaciones.<br/><br/>Tenga en cuenta que no puede usar el dominio predeterminado , \* .onmicrosoft.com, que se crea automáticamente para el inquilino.<br/><br/>Para ver los dominios, puede usar el siguiente cmdlet Skype Empresarial PowerShell en línea:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obtener más información sobre dominios y Microsoft 365 o Office 365, vea [Preguntas más frecuentes sobre dominios.](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)|
|Dirección IP pública del SBC|Una dirección IP pública que se puede usar para conectarse al SBC. Según el tipo de SBC, el SBC puede usar NAT.|
|Nombre de dominio completo (FQDN) para el SBC|Un FQDN para el SBC, donde la parte del dominio del FQDN es uno de los dominios registrados en su Microsoft 365 o Office 365 organización. Para obtener más información, vea [Nombres de dominio SBC](#sbc-domain-names).|
|Entrada DNS pública para el SBC |Una entrada DNS pública asigna el FQDN de SBC a la dirección IP pública. |
|Certificado de confianza pública para el SBC |Un certificado para que el SBC se utilice para todas las comunicaciones con enrutamiento directo. Para obtener más información, vea [Certificado de confianza pública para el SBC.](#public-trusted-certificate-for-the-sbc)|
|Puntos de conexión para enrutamiento directo |Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:<br/><br/>`sip.pstnhub.microsoft.com` – FQDN global, debe probarse primero.<br/>`sip2.pstnhub.microsoft.com` – FQDN secundario, se asigna geográficamente a la región de segunda prioridad.<br/>`sip3.pstnhub.microsoft.com` – FQDN terciario, se asigna geográficamente a la región de tercera prioridad.<br/><br/>Para obtener información sobre los requisitos de configuración, vea [Señalización SIP: FQDN.](#sip-signaling-fqdns)|
|Direcciones IP de firewall y puertos para medios de enrutamiento directo |El SBC se comunica a los siguientes servicios en la nube:<br/><br/>Proxy SIP, que controla la señalización<br/>Procesador multimedia, que controla los medios ,excepto cuando la omisión de medios está en<br/><br/>Estos dos servicios tienen direcciones IP independientes en Microsoft Cloud, que se describen más adelante en este documento.<br/><br/>Para obtener más información, vea [la Microsoft Teams de](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) direcciones URL e [intervalos de direcciones IP.](/office365/enterprise/urls-and-ip-address-ranges) |
|Perfil de transporte multimedia|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Direcciones IP de firewall y puertos para Microsoft Teams multimedia |Para obtener más información, vea [Direcciones URL e intervalos de direcciones IP.](/office365/enterprise/urls-and-ip-address-ranges) |
|||

## <a name="licensing-and-other-requirements"></a>Licencias y otros requisitos 

Los usuarios de Enrutamiento directo deben tener asignadas las siguientes licencias Microsoft 365 o Office 365: 

- Teléfono Microsoft Sistema. 
- Microsoft Teams + Skype Empresarial Plan 2, si se incluye en las licencias.
- Audioconferencia de Microsoft (lea las notas y el párrafo siguiente para ver ejemplos específicos sobre cuándo se requiere la licencia).

> [!NOTE]
> Skype Empresarial El plan no debe quitarse de ningún contrato de licencia en el que se incluya. 
> 
> [!IMPORTANT]
> GCC Los usuarios altos y doD deben deshabilitar cualquier licencia de audioconferencia incluida en G5 y esperar a habilitar cualquier conferencia de audioconferencia hasta que el enrutamiento directo se haya configurado por completo. Los usuarios deben tener configurados los números de teléfono de acceso telefónico local y un teclado de marcado en funcionamiento antes de habilitar licencias de conferencias de audio. Vea [Conferencias de audio con enrutamiento directo para GCC alta](./audio-conferencing-with-direct-routing-for-gcch-and-dod.md) y doD para obtener más información.


> [!IMPORTANT]
>  En el caso de que quiera agregar participantes externos a las reuniones programadas, ya sea marcando para ellos o proporcionando el número de acceso telefónico local, se requiere la licencia de audioconferencia.
> Para GCC High y DoD, no asigne una licencia de audioconferencia para los usuarios de G5.  Para los usuarios de G3, no asigne una licencia de audioconferencia hasta que enrutamiento directo esté completamente configurado y el usuario tenga un teclado de marcado funcional.


### <a name="ad-hoc-call-escalation-and-audio-conferencing-license"></a>Escalación de llamadas ad hoc y licencia de audioconferencia

Un Teams puede iniciar una Teams a RTC o Teams Teams para realizar una llamada y agregarle un participante RTC. Este escenario se denomina conferencia ad hoc. La ruta de acceso que toma la llamada depende de si el usuario que escala la llamada tiene una licencia de Audioconferencia de Microsoft asignada o no:

- Si el Teams que escala la llamada tiene asignada una licencia de Audioconferencia de Microsoft, la escalación se produce a través del servicio de audioconferencia de Microsoft. El participante rtc remoto que está invitado a la llamada existente recibe una notificación sobre la llamada entrante y ve el número del puente de Microsoft asignado al usuario de Teams que inició la escalada.
- Si el Teams que escala la llamada no tiene asignada la licencia de Audioconferencia de Microsoft, la escalación se produce a través de un controlador de borde de sesión conectado a la interfaz de enrutamiento directo. El participante rtc remoto que está invitado a la llamada recibe una notificación sobre la llamada entrante y ve el número del usuario Teams que inició la escalada. La directiva de enrutamiento del usuario define el SBC específico que se usa para la escalada. 


Además, debe asegurarse de lo siguiente:
 
- CsOnlineVoiceRoutingPolicy se asigna al usuario. 
- Permitir llamadas privadas está habilitado en el nivel de inquilino para Microsoft Teams. 

Enrutamiento directo también admite usuarios con licencia para Microsoft Calling Plan. Teléfono Microsoft Sistema con plan de llamadas puede enrutar algunas llamadas mediante la interfaz de enrutamiento directo. Sin embargo, los números de teléfono de los usuarios deben adquirirse en línea o portados a Microsoft.  

Combinar la conectividad de plan de llamadas y enrutamiento directo para el mismo usuario es opcional, pero podría ser útil (por ejemplo, cuando se asigna al usuario un plan de llamadas de Microsoft, pero quiere enrutar algunas llamadas con el SBC). Uno de los escenarios más comunes son las llamadas a PBX de terceros.  Con PBX de terceros, todas las llamadas, excepto las llamadas a los teléfonos conectados a los PBX, se enruta con el Plan de llamadas de Microsoft, pero las llamadas a los teléfonos conectados a PBX de terceros van al SBC y, por lo tanto, permanecen dentro de la red empresarial y no de la RTC. 

Para obtener más información sobre Sistema telefónico licencias, vea Sacar el máximo partido de [Office](https://products.office.com/compare-all-microsoft-office-products?tab=2) [y Opciones de plan.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options) 

Para obtener más información sobre Sistema telefónico licencias, [vea Microsoft Teams de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 

## <a name="supported-end-points"></a>Puntos finales admitidos 

Puede usar como punto final:

- Cualquier Teams cliente. 
- Teléfonos de área común. Consulte [Configurar la licencia de uso Teléfono área común para Microsoft Teams](./set-up-common-area-phones.md). Tenga en cuenta que no necesita una licencia de Plan de llamadas al configurar un área común Teléfono con enrutamiento directo.
- Skype Empresarial teléfonos 3PIP. Vea [Skype Empresarial teléfonos móviles (3PIP) con Microsoft Teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Skype-for-Business-phones-3PIP-support-with-Microsoft-Teams/ba-p/789351)


## <a name="sbc-domain-names"></a>Nombres de dominio SBC

El nombre de dominio SBC debe ser de uno de los nombres registrados en Dominios del inquilino. No puede usar \* el espacio empresarial .onmicrosoft.com para el nombre FQDN del SBC.

En la tabla siguiente se muestran ejemplos de nombres DNS registrados para el inquilino, si el nombre se puede usar como FQDN para el SBC y ejemplos de nombres FQDN válidos:

|Nombre DNS|Se puede usar para FQDN de SBC|Ejemplos de nombres FQDN|
|:--- |:--- |:--- |
contoso.com|Sí|**Nombres válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|No|El uso de dominios *.onmicrosoft.com no es compatible con los nombres de SBC

Suponga que desea usar un nombre de dominio nuevo. Por ejemplo, el inquilino contoso.com como un nombre de dominio registrado en el inquilino y desea usar sbc1.sip.contoso.com. Para poder emparejar un SBC con el nombre sbc1.sip.contoso.com, debe registrar el nombre de dominio sip.contoso.com dominios en el espacio empresarial. Si intenta emparejar un SBC con sbc1.sip.contoso.com antes de registrar el nombre de dominio, recibirá el siguiente error: "No se puede usar el dominio "sbc1.sip.contoso.com" ya que no se configuró para este inquilino".
Después de agregar el nombre de dominio, también debe crear un usuario con UPN user@sip.contoso.com y asignar una Teams licencia. Es posible que tarde hasta 24 horas en aprovisionar completamente el nombre de dominio después de agregarlo a Dominios del inquilino, se crea un usuario con un nombre nuevo y se asigna una licencia al usuario. 

Es posible que una empresa tenga varios espacios de direcciones SIP en un inquilino. Por ejemplo, una empresa puede tener contoso.com como un espacio de direcciones SIP y fabrikam.com como el segundo espacio de direcciones SIP. Algunos usuarios tienen direcciones user@contoso.com y algunos usuarios tienen direcciones user@fabrikam.com. 

El SBC solo necesita un FQDN y puede atender a los usuarios desde cualquier espacio de direcciones en el espacio empresarial emparejado. Por ejemplo, un SBC con el nombre sbc1.contoso.com puede recibir y enviar el tráfico RTC para usuarios con direcciones user@contoso.com y user@fabrikam.com siempre que estos espacios de direcciones SIP se registren en el mismo espacio empresarial.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado de confianza pública para el SBC

Microsoft recomienda solicitar el certificado para el SBC generando una solicitud de firma de certificación (CSR). Para obtener instrucciones específicas sobre cómo generar un CSR para un SBC, consulte las instrucciones de interconexión o la documentación proporcionada por sus proveedores de SBC. 

  > [!NOTE]
  > La mayoría de las autoridades de certificación (CA) requieren que el tamaño de clave privada sea como mínimo 2048. Tenga esto en cuenta al generar la CSR.

El certificado debe tener el FQDN de SBC como el nombre común (CN) o el campo de nombre alternativo del asunto (SAN). El certificado debe emitirse directamente desde una entidad de certificación, no desde un proveedor intermedio.

Como alternativa, enrutamiento directo admite un carácter comodín en el CN o san, y el carácter comodín debe ajustarse a [RFC estándar HTTP Sobre TLS.](https://tools.ietf.org/html/rfc2818#section-3.1) Un ejemplo sería usar .contoso.com que coincidiría con el FQDN de SBC sbc.contoso.com, pero no coincidiría \* con sbc.test.contoso.com.

El certificado debe ser generado por una de las siguientes autoridades de certificación raíz:

- AffirmTrust
- Raíz de CA externa de AddTrust
- Raíz de CyberTrust de Baltimore*
- Buypass
- Ciberconfianza
- Entidad de certificación principal pública de clase 3
- Comodo Secure Root CA
- Deutsche Telekom 
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA
- Entrust
- GlobalSign
- Ir a papá
- GeoTrust
- Verisign, Inc. 
- SSL.com
- Starfield
- Symantec Enterprise Mobile Root para Microsoft 
- SwissSign
- Thawte Timestamping CA
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis
- USERTrust RSA Certification Authority
- Hongkong Post Root CA 1,2,3
- Sectigo Root CA

Para enrutamiento directo en Office 365 entornos GCCH y DoD, el certificado debe ser generado por una de las siguientes autoridades de certificación raíz:
- DigiCert Global Root CA
- DigiCert High Assurance EV Root CA

> [!NOTE]
> *Si el soporte de TLS mutuo (MTLS) está habilitado para la conexión Teams en el SBC, debe instalar el certificado raíz de CyberTrust de Baltimore en el almacén raíz de confianza de SBC del contexto Teams TLS. (Esto se debe a que los certificados de servicio de Microsoft usan el certificado raíz de Baltimore). Para descargar el certificado raíz de Baltimore, [vea Office 365 cadenas de cifrado](/microsoft-365/compliance/encryption-office-365-certificate-chains).

Microsoft está trabajando en la adición de entidades de certificación adicionales en función de las solicitudes de los clientes. 

## <a name="sip-signaling-fqdns"></a>Señalización SIP: FQDN 

El enrutamiento directo se ofrece en los siguientes entornos:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Obtenga más información [sobre Office 365 entornos](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) gubernamentales de Ee. UU. como GCC, GCC high y DoD.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 y Office 365 GCC entornos

Los puntos de conexión para enrutamiento directo son los tres FQDN siguientes:

- **sip.pstnhub.microsoft.com:** FQDN global, debe probarse primero. Cuando el SBC envía una solicitud para resolver este nombre, los servidores DNS Microsoft Azure devuelven una dirección IP que apunta al centro de datos de Azure principal asignado al SBC. La tarea se basa en las métricas de rendimiento de los centros de datos y la proximidad geográfica al SBC. La dirección IP devuelta corresponde al FQDN principal.
- **sip2.pstnhub.microsoft.com:** FQDN secundario, se asigna geográficamente a la región de segunda prioridad.
- **sip3.pstnhub.microsoft.com:** FQDN terciario, se asigna geográficamente a la región de tercera prioridad.

Es necesario poner estos tres FQDN en orden para:

- Proporcione una experiencia óptima (menos cargada y más cercana al centro de datos de SBC asignada consultando el primer FQDN).
- Proporcione conmutación por error cuando se establezca la conexión desde un SBC a un centro de datos que experimenta un problema temporal. Para obtener más información, vea Mecanismo [de conmutación por error a continuación.](#failover-mechanism-for-sip-signaling)  

Los FQDN (sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com y sip3.pstnhub.microsoft.com) se resolverán en direcciones IP de las siguientes subredes:

- 52.112.0.0/14
- 52.120.0.0/14

Debe abrir puertos para todos estos intervalos de direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si el firewall admite nombres DNS, el FQDN **sip-all.pstnhub.microsoft.com** se resuelve en todas estas subredes IP. 

> [!IMPORTANT]
> Como parte de Teams expansión y mejora del servicio de enrutamiento directo, hemos implementado nuevas instancias de infraestructura de enrutamiento directo en Australia en noviembre de 2020. Esto se refleja en dos direcciones IP adicionales (52.114.16.74 y 52.114.20.29) a las que se resolverán los siguientes FQDN para los clientes australianos: sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com y sip3.pstnhub.microsoft.com. Debe asegurarse de que estas dos direcciones IP (52.114.16.74 y 52.114.20.29) están permitidas en las listas de control de acceso IP (ACL) y los puertos están abiertos para todas estas direcciones IP del firewall para permitir el tráfico entrante y saliente a y desde las direcciones para la señalización.

> [!IMPORTANT]
> Como parte de Teams expansión y mejora del servicio de enrutamiento directo, hemos implementado nuevas instancias de infraestructura de enrutamiento directo en Japón en mayo de 2021. Esto se refleja en dos direcciones IP adicionales (52.114.36.156 y 52.114.32.169) a las que se resolverán los siguientes FQDN para los clientes japoneses: sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com y sip3.pstnhub.microsoft.com. Debe asegurarse de que estas dos direcciones IP (52.114.36.156 y 52.114.32.169) están permitidas en las listas de control de acceso IP (ACL) y los puertos están abiertos para todas estas direcciones IP del firewall para permitir el tráfico entrante y saliente a y desde las direcciones para la señalización.

### <a name="office-365-gcch-and-dod-environment"></a>Office 365 Entorno de GCCH y DoD

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.dod.teams.microsoft.us:** FQDN global. Como el Office 365 DoD solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

El fqdn sip.pstnhub.dod.teams.microsoft.us se resolverá en una dirección IP de la siguiente subred:

- 52.127.64.0/21

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC high environment

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**sip.pstnhub.gov.teams.microsoft.us:** FQDN global. Como el GCC high solo existe en los centros de datos de EE. UU., no hay FQDN secundarios y terciarios.

El fqdn sip.pstnhub.gov.teams.microsoft.us se resolverá en una dirección IP de la siguiente subred:

- 52.127.64.0/21

Debe abrir puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización. Si el firewall admite nombres DNS, el FQDN **sip-all.pstnhub.gov.teams.microsoft.us** se resuelve en todas estas direcciones IP. Este FQDN también se puede usar como FQDN federado para la clasificación de llamadas entrantes.

## <a name="sip-signaling-ports"></a>Señalización SIP: Puertos

Debe usar los siguientes puertos para Microsoft 365 o Office 365 en los que se ofrece enrutamiento directo:
- Microsoft 365 o Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

|Tráfico|De|Hasta|Puerto de origen|Puerto de destino|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|SIP Proxy|SBC|1024 – 65535|Definido en el SBC (para Office 365 GCC solo debe usarse el puerto Alto/DoD 5061)|
SIP/TLS|SBC|SIP Proxy|Definido en el SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de conmutación por error para señalización SIP

El SBC realiza una consulta DNS para resolver sip.pstnhub.microsoft.com. Según la ubicación de SBC y las métricas de rendimiento del centro de datos, se selecciona el centro de datos principal. Si el centro de datos principal experimenta un problema, el SBC probará el sip2.pstnhub.microsoft.com, que se resuelve en el segundo centro de datos asignado y, en el caso raro de que los centros de datos de dos regiones no están disponibles, el SBC vuelve a intentar el último FQDN (sip3.pstnhub.microsoft.com), que proporciona la IP terciaria del centro de datos.

En la tabla siguiente se resumen las relaciones entre centros de datos primarios, secundarios y terciarios:

|Si el centro de datos principal es|EMEA|NOAM|ASIA|
|:--- |:--- |:--- |:--- |
|El centro de datos secundario (sip2.pstnhub.microsoft.com)|EE. UU.|UE|EE. UU.|
|El centro de datos terciario (sip3.pstnhub.microsoft.com)|ASIA|ASIA|UE|
|||||

## <a name="media-traffic-port-ranges"></a>Tráfico multimedia: Intervalos de puertos
Tenga en cuenta que los requisitos siguientes se aplican si desea implementar enrutamiento directo sin omisión de medios. Para obtener información sobre los requisitos del firewall para la omisión de medios, consulte Planear la omisión [de medios con enrutamiento directo.](./direct-routing-plan-media-bypass.md)



El tráfico multimedia fluye hacia y desde un servicio independiente en Microsoft Cloud. Los intervalos de direcciones IP para el tráfico multimedia son los siguientes.

### <a name="microsoft-365-office-365-and-office-365-gcc-environments"></a>Microsoft 365, Office 365 y Office 365 GCC entornos

- 52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254).
- 52.120.0.0/14 (direcciones IP de 52.120.0.1 a 52.123.255.254).

### <a name="office-365-dod-environment"></a>Office 365 Entorno doD

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC high environment

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervalo de puertos (aplicable a todos los entornos)
El rango de puertos de los procesadores multimedia se muestra en la tabla siguiente: 

|Tráfico|De|Hasta|Puerto de origen|Puerto de destino|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Procesador multimedia|SBC|3478-3481 y 49152 - 53247|Definido en el SBC|
|UDP/SRTP|SBC|Procesador multimedia|Definido en el SBC|3478-3481 y 49152 - 53247|

  > [!NOTE]
  > Microsoft recomienda al menos dos puertos por llamada simultánea en el SBC.


## <a name="media-traffic-media-processors-geography"></a>Tráfico multimedia: geografía de los procesadores multimedia

El tráfico multimedia fluye a través de componentes denominados procesadores multimedia. Los procesadores multimedia se colocan en los mismos centros de datos que los servidores proxy SIP. Además, hay procesadores multimedia adicionales para optimizar el flujo de medios. Por ejemplo, ahora no tenemos un componente de proxy SIP en Australia (flujos SIP a través de Singapur o Hong Kong), pero tenemos el procesador multimedia localmente en Australia. La necesidad de los procesadores multimedia localmente se determina por la latencia que experimentamos al enviar tráfico de larga distancia, por ejemplo de Australia a Singapur o Hong Kong. Aunque la latencia en el ejemplo de tráfico que fluye de Australia a Hong Kong o Singapur es aceptable para conservar la buena calidad de las llamadas para el tráfico SIP, para el tráfico multimedia en tiempo real no lo es.

Ubicación de los procesadores multimedia:

Ubicaciones en las que se implementaron tanto los componentes del proxy SIP como del procesador multimedia:
- EE. UU. (dos en centros de datos de EE. UU. Oeste y Este de EE. UU.)
- Europa (centros de datos de Ámsterdam y Dublín)
- Asia (centros de datos de Singapur y Hong Kong)
- Japón (centros de datos de JP East y West)
- Australia (centros de datos de Este y Sureste de AUSTRALIA)

## <a name="media-traffic-codecs"></a>Tráfico multimedia: Códecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Leg between SBC and Cloud Media Processor or Microsoft Teams client.
Se aplica tanto a casos de omisión multimedia como a casos que no se omiten.

La interfaz de enrutamiento directo en el tramo entre el controlador de borde de sesión y el procesador multimedia en la nube (sin omisión de medios) o entre el cliente de Teams y el SBC (si la omisión de medios está habilitada) puede usar los siguientes códecs:

- Bypass no multimedia (SBC a cloud Media Processor): SILK, G.711, G.722, G.729
- Omisión de medios (SBC Teams cliente): SILK, G.711, G.722, G.729

Puede forzar el uso del códec específico en el controlador de borde de sesión excluyendo los códecs no deseados de la oferta.

### <a name="leg-between-microsoft-teams-client-and-cloud-media-processor"></a>Leg between Microsoft Teams Client and Cloud Media Processor
Solo se aplica a casos de omisión no multimedia. Con la omisión de medios, los medios fluyen directamente entre el Teams y el SBC.

En el tramo entre el procesador multimedia en la nube y Microsoft Teams se usa el cliente SILK o G.722. La elección del códec en esta parte se basa en los algoritmos de Microsoft, que tienen en cuenta varios parámetros. 


## <a name="supported-session-border-controllers-sbcs"></a>Controladores de borde de sesión (SBC) compatibles

Microsoft solo admite SBC certificados para emparejar con enrutamiento directo. Dado Telefonía IP empresarial es fundamental para las empresas, Microsoft ejecuta pruebas intensivas con los SBC seleccionados y trabaja con los proveedores de SBC para asegurarse de que los dos sistemas son compatibles. 

Los dispositivos que se han validado se muestran como Certificados para Teams enrutamiento directo. Los dispositivos certificados están garantizados para funcionar en todos los escenarios. 

Para obtener más información sobre los SBC compatibles, vea Lista de controladores de [borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)

 
## <a name="see-also"></a>Vea también

[Configurar el enrutamiento directo](direct-routing-configure.md)
