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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Lea este tema para obtener información sobre cómo el enrutamiento directo de Microsoft Phone System le permite conectar un controlador de borde de sesión compatible suministrado por el cliente (SBC) a Microsoft Phone System.
ms.openlocfilehash: 8dc06650a50af5b66931f196c0a1c3d7c5090bc5
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464584"
---
# <a name="plan-direct-routing"></a>Planear el enrutamiento directo

> [!Tip]
> Vea la siguiente sesión para obtener información sobre las ventajas del enrutamiento directo, cómo planearlo y cómo implementarlo: [enrutamiento directo en Microsoft Teams](https://aka.ms/teams-direct-routing)

El enrutamiento directo de Microsoft Phone System le permite conectar un controlador de borde de sesión compatible suministrado por el cliente (SBC) a Microsoft Phone System.  Con esta capacidad, por ejemplo, puede configurar la conectividad RTC local con el cliente de Microsoft Teams, como se muestra en el siguiente diagrama: 

![Diagrama que muestra la configuración de conectividad RTC local] (media/PlanDirectRouting1-PSTNwithTeams.png "Configuración de conectividad RTC local con el cliente de Microsoft Teams")

  > [!NOTE]
  > Skype empresarial online también le permite emparejar un SBC proporcionado por el cliente, pero esto requiere una implementación local de Skype empresarial Server o una edición especial de Skype empresarial, denominada Cloud Connector, entre el SBC y la nube de Microsoft. Este escenario se conoce como voz híbrida. Por el contrario, el enrutamiento directo permite una conexión directa entre el SBC compatible y la nube de Microsoft. 

Con el enrutamiento directo, puede conectar su SBC a casi cualquier troncal de telefonía o interconexión con equipos de la red telefónica conmutada (RTC) de terceros. El enrutamiento directo le permite: 

- Usa prácticamente cualquier tronco de RTC con Microsoft Phone System. 
- Configurar la interoperabilidad entre equipos de telefonía del cliente, como un intercambio de sucursales privada (PBX) de terceros, dispositivos analógicos y Microsoft Phone System.

Microsoft también ofrece soluciones de voz todo en la nube, como el plan de llamadas.  Sin embargo, una solución de voz híbrida puede ser la mejor para su organización si: 

- El plan de llamadas de Microsoft no está disponible en tu país. 
- Su organización requiere conexión a dispositivos analógicos de terceros, centros de llamadas, etc. 
- Tu organización tiene un contrato existente con una portadora RTC.

El enrutamiento directo también es compatible con los usuarios que tienen la licencia adicional para el plan de llamadas de Microsoft. Para obtener más información, consulta [planes de llamadas y sistema telefónico](calling-plan-landing-page.md). 

Con el enrutamiento directo, cuando los usuarios participan en una conferencia programada, el número de acceso telefónico es proporcionado por el servicio de conferencias de audio de Microsoft, que requiere licencias apropiadas.  Cuando se hace el marcado, el servicio Conferencia de audio de Microsoft coloca la llamada mediante capacidades de llamadas en línea, que requiere licencias apropiadas. (Tenga en cuenta que el marcado no se enruta a través del enrutamiento directo). Para obtener más información, vea [reuniones en línea con Teams](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
Planear la implementación de enrutamiento directo es clave para una implementación exitosa. Este artículo describe los requisitos de infraestructura y licencias, y proporciona información sobre la conectividad de SBC: 

- [Requisitos de infraestructura](#infrastructure-requirements)
- [Licencias y otros requisitos](#licensing-and-other-requirements)
- [Nombres de dominio de SBC](#sbc-domain-names)
- [Certificado de confianza pública para SBC](#public-trusted-certificate-for-the-sbc)
- [Señalización SIP: FQDN](#sip-signaling-fqdns)
- [Señalización SIP: puertos](#sip-signaling-ports)
- [Tráfico de medios: intervalos de puertos](#media-traffic-port-ranges)
- [Controladores de borde de sesión compatibles (SBCs)](#supported-session-border-controllers-sbcs)

Para obtener información detallada sobre cómo configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura
En la tabla siguiente se enumeran los requisitos de infraestructura para los SBCs, los dominios y otros requisitos de conectividad de red admitidos para implementar el enrutamiento directo:  

|**Requisito de infraestructura**|**Necesitas lo siguiente**|
|:--- |:--- |
|Controlador de borde de sesión (SBC)|Una SBC compatible. Para obtener más información, consulte [SBCS admitido](#supported-session-border-controllers-sbcs).|
|Troncos de telefonía conectados a la SBC|Uno o más troncos de telefonía conectados a la SBC. En un extremo, el SBC se conecta al sistema telefónico de Microsoft a través del enrutamiento directo. La SBC también se puede conectar a entidades de telefonía de terceros, como PBX, adaptadores de telefonía analógicos, etc. Cualquier opción de conectividad de RTC conectada a SBC funcionará. (Nota: para la configuración de los troncos RTC en SBC, consulte los proveedores de SBC o los proveedores troncales).|
|Inquilino de Office 365|Un inquilino de Office 365 que usa para alojar a los usuarios de Microsoft Teams, así como la configuración y la conexión a SBC.|
|Registrador de usuario|El usuario debe estar alojado en Office 365.<br/>Si su empresa tiene un entorno local de Skype empresarial o de Lync con conectividad híbrida con Office 365, no puede habilitar la voz en Teams para un usuario de ubicación local.<br/><br/>Para comprobar el registrador de un usuario, use el siguiente cmdlet de PowerShell de Skype empresarial online:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>El resultado del cmdlet debe mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Dominios|Uno o más dominios agregados a sus inquilinos de Office 365.<br/><br/>**Nota:** No puede usar el dominio predeterminado, *. onmicrosoft.com, que se crea automáticamente para su inquilino.<br/><br/>Para ver los dominios, puede usar el siguiente cmdlet de PowerShell de Skype empresarial online:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obtener más información sobre los dominios y los inquilinos de Office 365, consulte [preguntas más frecuentes](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)sobre los dominios.|
|Dirección IP pública para el SBC|Una dirección IP pública que se puede usar para conectarse a SBC. Según el tipo de SBC, el SBC puede usar NAT.|
|Nombre de dominio completo (FQDN) para el SBC|Un FQDN para el SBC, donde la parte de dominio del FQDN es uno de los dominios registrados de su inquilino de Office 365. Para obtener más información, consulte [nombres de dominio de SBC](#sbc-domain-names).|
|Entrada DNS pública para SBC |Una entrada DNS pública que asigna el FQDN de SBC a la dirección IP pública. |
|Certificado de confianza pública para SBC |Un certificado para que la SBC se use para todas las comunicaciones con enrutamiento directo. Para obtener más información, consulte [certificado público de confianza para SBC](#public-trusted-certificate-for-the-sbc).|
|Puntos de conexión para enrutamiento directo |Los puntos de conexión para el enrutamiento directo son los tres FQDN siguientes:<br/><br/>`sip.pstnhub.microsoft.com`(FQDN global) debe probarse en primer lugar.<br/>`sip2.pstnhub.microsoft.com`-FQDN secundario, se asigna geográficamente a la segunda región prioritaria.<br/>`sip3.pstnhub.microsoft.com`– El FQDN terciario se asigna geográficamente a la tercera región de prioridad.<br/><br/>Para obtener información sobre los requisitos de configuración, consulte [señalización SIP: FQDN](#sip-signaling-fqdns).|
|Direcciones IP y puertos de Firewall para medios de enrutamiento directos |El SBC se comunica con los siguientes servicios en la nube:<br/><br/>Proxy SIP, que controla la señalización<br/>Procesador de medios, que controla los medios, excepto cuando la omisión de medios está activada<br/><br/>Estos dos servicios tienen direcciones IP independientes en la nube de Microsoft, que se describen más adelante en este documento.<br/><br/>Para obtener más información, consulte la [sección Microsoft Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) en [Office 365 direcciones URL e intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|Perfil de transporte de medios|TCP/RTP/SAVP <br/>UDP/RTP/SAVP|
Direcciones IP y puertos de Firewall para los medios de Microsoft Teams |Para obtener más información, consulte [direcciones URL e intervalos de direcciones IP de Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Licencias y otros requisitos 

Los usuarios de enrutamiento directo deben tener las siguientes licencias asignadas en Office 365: 

- Microsoft Phone System 
- Microsoft Teams + Skype para empresas plan 2 si se incluye en la SKU de licencias
- Conferencias de audio de Microsoft 

> [!NOTE]
> El plan de Skype empresarial no se debe quitar de ninguna SKU de licencia donde esté incluido. 


> [!IMPORTANT]
>  En el caso de que desee agregar participantes externos a las reuniones programadas, ya sea mediante la marcación de ellos o proporcionando el número de acceso telefónico local, se *necesita*la licencia de audioconferencia.

> [!NOTE]
> La licencia de conferencia de audio es *necesaria* para:
> - Escalar desde la llamada de 1:1 a una llamada grupal.
> - Agregue participantes externos a las reuniones programadas, mediante marcado o proporcionando el número de acceso telefónico local. 


Además, debe asegurarse de lo siguiente:
 
- CsOnlineVoiceRoutingPolicy está asignado al usuario. 
- Permitir llamadas privadas está habilitada en el nivel de espacio empresarial de Microsoft Teams. 

El enrutamiento directo también admite usuarios con licencia para el plan de llamadas de Microsoft. El sistema telefónico de Microsoft con el plan de llamadas puede enrutar algunas llamadas con la interfaz de enrutamiento directo. Sin embargo, los números de teléfono de los usuarios deben adquirirse en línea o trasladarse a Microsoft.  

Combinar el plan de llamadas y la conectividad de enrutamiento directo para el mismo usuario es opcional, pero podría ser útil, por ejemplo, cuando se asigna al usuario un plan de llamadas de Microsoft pero quiere enrutar algunas llamadas a través de SBC. Uno de los escenarios más comunes son las llamadas a PBX de terceros.  Con las PBX de terceros, todas las llamadas, excepto las llamadas a los teléfonos conectados a dichas PBX, se enrutan a través del plan de llamadas de Microsoft; pero las llamadas a los teléfonos conectados a sistemas PBX de terceros van a la SBC, por lo tanto, permanecen dentro de la red empresarial y no en la RTC. 

Para obtener más información sobre las licencias de sistema telefónico, consulte [sacar el máximo provecho de Office con](https://products.office.com/compare-all-microsoft-office-products?tab=2) [las opciones de Plan](https://technet.microsoft.com/library/office-365-plan-options.aspx)de office 365 y Office 365. 

Para obtener más información sobre las licencias de sistema telefónico, consulte [licencias complementarias de Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="sbc-domain-names"></a>Nombres de dominio de SBC

El nombre de dominio de SBC debe ser de uno de los nombres registrados en "dominios" del inquilino. No puede usar el inquilino *. onmicrosoft.com para el nombre de FQDN de la SBC.

En la tabla siguiente se muestran ejemplos de nombres DNS registrados para el inquilino, si el nombre se puede usar como FQDN de SBC y ejemplos de nombres FQDN válidos:

|**Nombre DNS**|**Puede usarse para el FQDN de SBC**|**Ejemplos de nombres FQDN**|
|:--- |:--- |:--- |
contoso.com|Sí|**Nombres válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>europe.contoso.com|
|contoso.onmicrosoft.com|No|<br/>No se admite el uso de dominios *. onmicrosoft.com para los nombres de SBC

Supongamos que desea usar un nuevo nombre de dominio. Por ejemplo, su inquilino tiene contoso.com como un nombre de dominio registrado en su inquilino y quiere usar sbc1.sip.contoso.com. Antes de poder emparejar un SBC con el nombre sbc1.sip.contoso.com, debe registrar el nombre de dominio sip.contoso.com en "dominios" en su espacio empresarial. Si intenta emparejar un SBC con sbc1.sip.contoso.com antes de registrar el nombre de dominio, recibirá el siguiente error: "no se puede usar el dominio" sbc1.sip.contoso.com "porque no estaba configurado para este inquilino".
Después de agregar el nombre de dominio, también tiene que crear un usuario con UPN user@sip.contoso.com y asignar una licencia de "Teams". Puede demorar hasta 24 horas en provisionar completamente el nombre de dominio después de agregarlo a "dominios" de su inquilino, se crea un usuario con un nuevo nombre y se asigna una licencia al usuario. 

Es posible que una empresa tenga varios espacios de direcciones SIP en un inquilino. Por ejemplo, una empresa puede tener contoso.com como un espacio de direcciones SIP y fabrikam.com como el segundo espacio de direcciones SIP. Algunos usuarios tienen user@contoso.com de dirección y algunos usuarios tienen direcciones user@fabrikam.com. 

La SBC solo necesita un FQDN y puede atender a los usuarios desde cualquier espacio de direcciones en el inquilino emparejado. Por ejemplo, un SBC con el nombre sbc1.contoso.com puede recibir y enviar el tráfico de RTC a los usuarios con direcciones user@contoso.com y user@fabrikam.com siempre que estos espacios de direcciones SIP estén registrados en el mismo inquilino.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado de confianza pública para SBC

Microsoft recomienda encarecidamente que solicite el certificado para la SBC generando una solicitud de firma de certificación (CSR). Para obtener instrucciones específicas sobre la creación de un CSR para una SBC, consulte las instrucciones de interconexión o la documentación proporcionada por los proveedores de SBC. 

  > [!NOTE]
  > La mayoría de las entidades de certificación (CA) requieren que el tamaño de la clave privada sea de al menos 2048. Ten esto en cuenta al generar el CSR.

El certificado debe tener el FQDN de SBC en los campos asunto, nombre común o nombre alternativo del asunto.

Como alternativa, el enrutamiento directo es compatible con un comodín en SAN y el comodín debe cumplir con el estándar [RFC http sobre TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Un ejemplo sería usar *. contoso.com en el SAN, que coincidiría con la sbc.contoso.com FQDN de SBC, pero no coincidiría con sbc.test.contoso.com.

El certificado debe ser generado por una de las siguientes entidades emisoras de certificados raíz:

- AffirmTrust
- Raíz de la entidad emisora de AddTrust externa
- Baltimore CyberTrust Root
- Buypass
- Cybertrust
- Entidad de certificación principal pública de clase 3
- Comodo de seguridad raíz segura
- Deutsche Telekom 
- Entidad de certificación raíz global de DigiCert
- DigiCert raíz de validación extendida de alta seguridad
- Confiar
- GlobalSign
- Ir Daddy
- GeoTrust
- VeriSign, Inc. 
- Starfield 
- Symantec Enterprise Mobile para Microsoft 
- SwissSign
- CA de marca de hora de Thawte
- Trustwave
- TeliaSonera 
- T-Systems International GmbH (Deutsche Telekom)
- QuoVadis

Microsoft está trabajando en la adición de entidades de certificación adicionales basadas en solicitudes de los clientes. 

## <a name="sip-signaling-fqdns"></a>Señalización SIP: FQDN 

El enrutamiento directo se ofrece en los siguientes entornos de Office 365:
- Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Obtenga más información sobre [Office 365 y entornos gubernamentales de Estados Unidos](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) , como GCC, GCC High y DoD.

### <a name="office-365-and-office-365-gcc-environments"></a>Entornos de Office 365 y Office 365 GCC

El punto de conexión para el enrutamiento directo son los tres FQDN siguientes:

- **SIP.pstnhub.Microsoft.com** (FQDN global) debe probarse en primer lugar. Cuando la SBC envía una solicitud para resolver este nombre, los servidores DNS de Microsoft Azure devuelven una dirección IP que apunta al centro de información principal de Azure asignado a SBC. La asignación se basa en las métricas de rendimiento de los centros de trabajo y la proximidad geográfica a la SBC. La dirección IP devuelta corresponde al FQDN principal.
- **SIP2.pstnhub.Microsoft.com** : FQDN secundario: se asigna geográficamente a la segunda región prioritaria.
- **sip3.pstnhub.Microsoft.com** – terciario FQDN: se asigna geográficamente a la tercera región prioritaria.

Es necesario ubicar estos tres FQDN en orden para:

- Proporciona una experiencia óptima (menos cargadas y más cercana al centro de proceso de la la de SBC asignado consultando el primer FQDN).
- Proporcione la conmutación por error cuando se establezca una conexión de SBC a un centro de información que esté experimentando un problema temporal. Para obtener más información, vea [mecanismo de conmutación por error](#failover-mechanism-for-sip-signaling) a continuación.  

Los FQDN (sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com y sip3.pstnhub.microsoft.com) se resolverán en una de las siguientes direcciones IP:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

Necesitas abrir puertos para todas estas direcciones IP en tu firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si su Firewall admite nombres DNS, el FQDN sip-all.pstnhub.microsoft.com se resuelve en todas estas direcciones IP. 


### <a name="office-365-gcc-dod-environment"></a>Entorno DoD de Office 365 GCC

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**SIP.pstnhub.DoD.Teams.Microsoft.US** : FQDN global. Puesto que el entorno de Office 365 DoD solo existe en los centros de datos de los Estados Unidos, no hay FQDN secundarios ni terciarios.

Los FQDN-sip.pstnhub.dod.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:

- 52.127.64.33
- 52.127.68.34

Necesitas abrir puertos para todas estas direcciones IP en tu firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si su Firewall admite nombres DNS, el FQDN sip.pstnhub.dod.teams.microsoft.us se resuelve en todas estas direcciones IP. 

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC de gran entorno

El punto de conexión para enrutamiento directo es el siguiente FQDN:

**SIP.pstnhub.gov.Teams.Microsoft.US** : FQDN global. Puesto que el entorno alto de GCC solo existe en los centros de datos de los Estados Unidos, no hay FQDN secundarios ni terciarios.

Los FQDN-sip.pstnhub.gov.teams.microsoft.us se resolverán en una de las siguientes direcciones IP:

- 52.127.88.59
- 52.127.92.64

Necesitas abrir puertos para todas estas direcciones IP en tu firewall para permitir el tráfico entrante y saliente hacia y desde las direcciones para la señalización.  Si su Firewall admite nombres DNS, el FQDN sip.pstnhub.gov.teams.microsoft.us se resuelve en todas estas direcciones IP. 

## <a name="sip-signaling-ports"></a>Señalización SIP: puertos

Los requisitos de puerto son los mismos para todos los entornos de Office 365 donde se ofrece enrutamiento directo:
- Office 365
- Office 365 GCC
- Office 365 GCC High
- Office 365 DoD

Debe usar los siguientes puertos:

|**Transmisión**|**De**|**Hasta**|**Puerto de origen**|**Puerto de destino**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|Proxy SIP|SBC|1024 – 65535|Definido en la SBC|
SIP/TLS|SBC|Proxy SIP|Definido en la SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de conmutación por error para la señalización SIP

La SBC realiza una consulta DNS para resolver sip.pstnhub.microsoft.com. En función de la ubicación de SBC y de las métricas de rendimiento del centro de recursos, se selecciona el centro de recursos principal. Si el centro de información principal sufre un problema, la SBC probará la sip2.pstnhub.microsoft.com, que se resuelve en el segundo centro de información asignado y, en el caso raro de que no se encuentren disponibles centros de información en dos regiones, la SBC reintenta el último FQDN ( sip3.pstnhub.microsoft.com), que proporciona la IP del centro de centros de recursos terciario.

En la tabla siguiente se resumen las relaciones entre centros de recursos primarios, secundarios y terciarios:

|**Si el centro de recursos principal está**|**EMEA**|**NOAM**|**ASIÁTICA**|
|:--- |:--- |:--- |:--- |
|Centro de recursos secundario (sip2.pstnhub.microsoft.com)|DÉJEN|Reciba|DÉJEN|
|El centro de recursos terciario (sip3.pstnhub.microsoft.com)|ASIÁTICA|ASIÁTICA|Reciba|
|||||

## <a name="media-traffic-port-ranges"></a>Tráfico de medios: intervalos de puertos
Tenga en cuenta que los requisitos siguientes se aplican si desea implementar el enrutamiento directo sin omisión de medios. Para conocer los requisitos de Firewall para omisión de medios, consulte [planear la omisión de medios con enrutamiento directo](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-plan-media-bypass).



El tráfico multimedia fluye hacia y desde un servicio independiente en la nube de Microsoft. El intervalo IP para el tráfico de medios:

### <a name="office-365-and-office-365-gcc-environments"></a>Entornos de Office 365 y Office 365 GCC

- 52.112.0.0/14 (direcciones IP de 52.112.0.1 a 52.115.255.254).

### <a name="office-365-gcc-dod-environment"></a>Entorno DoD de Office 365 GCC

- 52.127.64.0/21

### <a name="office-365-gcc-high-environment"></a>Office 365 GCC de gran entorno

- 52.127.88.0/21

### <a name="port-range-applicable-to-all-environments"></a>Intervalo de puertos (válido para todos los entornos)
El intervalo de puertos de los procesadores multimedia se muestra en la tabla siguiente: 

|**Transmisión**|**De**|**Hasta**|**Puerto de origen**|**Puerto de destino**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Procesador de medios|SBC|49 152 – 53 247|Definido en la SBC|
|UDP/SRTP|SBC|Procesador de medios|Definido en la SBC|49 152 – 53 247|
|

  > [!NOTE]
  > Microsoft recomienda al menos dos puertos por llamada simultánea en la SBC.

## <a name="media-traffic-codecs"></a>Tráfico de medios: códecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Segmento entre el procesador multimedia de la nube y la SBC entre el cliente de Microsoft Teams.
Se aplica a los casos de omisión de medios y de no omisión

La interfaz de enrutamiento directo en el segmento entre el controlador de borde de la sesión y el procesador de multimedia en la nube (sin omisión de medios) o entre el cliente de Teams y el SBC (si la omisión de medios habilitados) puede usar los códecs siguientes:
- Omisión de contenido no multimedia (SBC a procesador de medios de nube): seda, G. 711, G. 722, G. 729
- Omisión de medios (cliente de SBC a teams): seda, G. 711, G. 722, G. 729, OPUS

Puede forzar el uso del códec específico en el controlador de borde de la sesión excluyendo los códecs no deseados de la oferta.

### <a name="leg-between-microsoft-teams-client--and-cloud-media-processor"></a>Segmento entre el cliente de Microsoft Teams y el procesador multimedia en la nube
Se aplica solo a las mayúsculas y minúsculas. Con medios, omita los flujos de medios directamente entre el cliente y el SBC de Teams

En la pierna entre el procesador de multimedia en la nube y el cliente de Microsoft Teams, se usa seda o G. 722. El códec que se elige en este segmento en función de los algoritmos de Microsoft, que tienen en cuenta varios parámetros. 


## <a name="supported-session-border-controllers-sbcs"></a>Controladores de borde de sesión compatibles (SBCs)

Microsoft solo admite SBCs certificado para emparejar con enrutamiento directo. Debido a que la telefonía IP es esencial para las empresas, Microsoft ejecuta pruebas intensivas con el SBCs seleccionado y funciona con los proveedores de SBC para garantizar que los dos sistemas sean compatibles. 

Los dispositivos que se han validado se enumeran como certificados para el enrutamiento directo de Teams. Los dispositivos certificados están garantizados para funcionar en todos los escenarios. 

Para obtener más información sobre SBCs admitido, vea [lista de controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).

 
## <a name="see-also"></a>Vea también

[Configurar el enrutamiento directo](direct-routing-configure.md)



