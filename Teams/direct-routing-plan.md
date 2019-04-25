---
title: Planear el enrutamiento directo
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
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
description: Lea este tema para obtener información sobre cómo enrutamiento directo de Microsoft teléfono del sistema le permite conectar un compatibles, proporcionado por el cliente sesión controlador de borde (SBC) para el sistema telefónico de Microsoft.
ms.openlocfilehash: e2b09d4aef25569e1112983b5f62bf2ba3758387
ms.sourcegitcommit: ee3f79ce1b6da0885e1096f9fba894bcff1814da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "33298575"
---
# <a name="plan-direct-routing"></a>Planear el enrutamiento directo

> [!Tip]
> Vea la sesión para obtener información sobre las ventajas de Direct enrutamiento, cómo planear para él y cómo implementarlo siguiente: [El enrutamiento directo en los equipos de Microsoft](https://aka.ms/teams-direct-routing)

Enrutamiento directo de Microsoft teléfono del sistema le permite conectar un compatibles, proporcionado por el cliente sesión controlador de borde (SBC) para el sistema telefónico de Microsoft.  Con esta función, por ejemplo, puede configurar la conectividad de RTC local con el cliente de Microsoft Teams, tal como se muestra en el siguiente diagrama: 

![Muestra la configuración de la conectividad de RTC local con el cliente de Microsoft Teams](media/PlanDirectRouting1-PSTNwithTeams.png)

  > [!NOTE]
  > Skype para profesionales en línea también le permite par un SBC proporcionado por el cliente, pero esto requiere una Skype local para la implementación de Business Server o una edición especial de Skype para la empresa, se denomina conector en la nube, entre los SBC y el Microsoft Cloud. En este escenario se conoce como voz híbrida. Por el contrario, se permite una conexión directa entre la SBC compatible y el Microsoft Cloud enrutamiento directo. 

Con el enrutamiento directo, puede conectar su SBC casi cualquier tronco de telefonía o interconexión con equipamiento pública red de telefónica conmutada (RTC) de otro fabricante. Enrutamiento directo le permite: 

- Usar prácticamente cualquier tronco RTC con el sistema telefónico de Microsoft. 
- Configurar la interoperabilidad entre los equipos de telefonía que pertenecen al cliente, como un tercero central de conmutación (PBX), dispositivos analógicos y Microsoft Phone System.

Microsoft también ofrece soluciones de voz all-in-the-cloud, como la planeación de la llamada.  Sin embargo, una solución de voz híbrida podría ser mejor para su organización si: 

- Llamar a planeación de Microsoft no está disponible en su país o región. 
- La organización requiere conexión a dispositivos analógicos de terceros, centros de llamadas y así sucesivamente. 
- Su organización tiene un contrato existente con un operador de RTC.

Enrutamiento directo también es compatible con los usuarios que tienen una licencia adicional para la planeación de una llamada a Microsoft. Para obtener más información, vea el [sistema telefónico y planes de llamada](calling-plan-landing-page.md). 

Con el enrutamiento directo, cuando los usuarios participan en una conferencia programada, el número telefónico es proporcionado por el servicio de conferencia de Audio de Microsoft, que requiere licencia adecuada.  Al marcar, el servicio de conferencia de Audio de Microsoft coloca la llamada mediante las funciones de llamadas en línea, lo cual requiere licencia adecuada. (Tenga en cuenta que hacer llamadas no se enrutan a través de enrutamiento directo.) Para obtener más información, vea [Las reuniones en línea con los equipos](https://products.office.com/microsoft-teams/online-meeting-solutions). 
 
Planear la implementación de enrutamiento directo es clave para una implementación correcta. En este artículo se describe la infraestructura y los requisitos de licencia y proporciona información sobre la conectividad SBC: 

- [Requisitos de infraestructura](#infrastructure-requirements)
- [Concesión de licencias y otros requisitos](#licensing-and-other-requirements)
- [Nombres de dominio SBC](#sbc-domain-names)
- [Certificado de confianza pública para el SBC](#public-trusted-certificate-for-the-sbc)
- [Señalización SIP: Los puertos de firewall y los FQDN](#sip-signaling-fqdns-and-firewall-ports)
- [El tráfico de medios: intervalos de puertos](#media-traffic-port-ranges)
- [SBCs compatibles](#supported-session-border-controllers-sbcs)

Para obtener información detallada acerca de cómo configurar el enrutamiento directo, vea [Configurar el enrutamiento directo](direct-routing-configure.md).

## <a name="infrastructure-requirements"></a>Requisitos de infraestructura
En la siguiente tabla, se enumeran los requisitos de infraestructura para el SBCs compatibles, dominios y otros requisitos de conectividad de red para implementar el enrutamiento directo:  

|**Requisito de infraestructura**|**Se necesita lo siguiente**|
|:--- |:--- |
|Controlador de borde de sesión (SBC)|Un SBC compatible. Para obtener más información, vea [SBCs compatibles](#supported-session-border-controllers-sbcs).|
|Troncos de telefonía conectados a la SBC|Uno o más troncos de telefonía conectados a la SBC. En un extremo, el SBC se conecta al sistema de teléfono de Microsoft a través de enrutamiento directo. La SBC también puede conectarse a entidades de telefonía de terceros, como PBX, adaptadores de telefonía analógico y así sucesivamente. Cualquier opción de conectividad RTC conectado a la SBC funcionará. (Nota: para la configuración de los troncos RTC a SBC, hacer referencia a los proveedores SBC o proveedores de tronco.)|
|Inquilino de Office 365|Inquilino de Office 365 que use para hospedar los usuarios de Microsoft Teams y la configuración y la conexión a la SBC.|
|Registrador de usuario|Usuario debe estar alojado en Office 365.<br/>Si su compañía tiene un Skype local para un entorno empresarial o Lync con conectividad híbrida a Office 365, no se puede habilitar la voz en los equipos de un usuario alojado local.<br/><br/>Para comprobar al registrador de un usuario, use el siguiente Skype para el cmdlet de PowerShell en línea de negocio:<br/><code>Get-CsOnlineUser -Identity \<user> \| fl HostingProvider</code> <br/><br/>El resultado del cmdlet debe mostrar:<br/><code>HostingProvider : sipfed.online.lync.com</code>|
|Dominios|Uno o más dominios agregados a los inquilinos de Office 365.<br/><br/>**Nota:** No se puede usar el dominio predeterminado, *. onmicrosoft.com, que se crea automáticamente para el inquilino.<br/><br/>Para ver los dominios, puede usar el siguiente Skype para el cmdlet de PowerShell en línea de negocio:<br/><code>Get-CsTenant \| fl Domains</code><br/><br/>Para obtener más información acerca de dominios y los inquilinos de Office 365, consulte [Preguntas más frecuentes de dominios](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a).|
|Dirección IP pública para el SBC|Una dirección IP pública que puede usarse para conectarse a la SBC. En función del tipo de SBC, los SBC puede usar NAT.|
|Nombre de dominio completo (FQDN) para el SBC|Un FQDN para el SBC, donde la parte del dominio del FQDN es uno de los dominios registrados en el inquilino de Office 365. Para obtener más información, vea [nombres de dominio SBC](#sbc-domain-names).|
|Entrada DNS pública para el SBC |Una entrada DNS pública asignar el FQDN SBC a la dirección IP pública. |
|Certificado de confianza pública para el SBC |Un certificado para el SBC que se usará para todas las comunicaciones con el enrutamiento directo. Para obtener más información, vea [pública certificado de confianza para el SBC](#public-trusted-certificate-for-the-sbc).|
|Puntos de conexión para el enrutamiento directo |Los puntos de conexión para el enrutamiento directo son los FQDN de tres los siguientes:<br/><br/>`sip.pstnhub.microsoft.com`: FQDN global, debe intentar primero.<br/>`sip2.pstnhub.microsoft.com`: FQDN secundario, geográficamente se asigna a la segunda región de prioridad.<br/>`sip3.pstnhub.microsoft.com`– Terciario FQDN, geográficamente se asigna a la región de prioridad de terceros.<br/><br/>Para obtener información sobre los requisitos de configuración, vea [de señalización SIP: FQDN y los puertos de firewall](#sip-signaling-fqdns-and-firewall-ports).|
|Las direcciones IP de servidor de seguridad y los puertos para los medios de enrutamiento directo |La SBC se comunica con los siguientes servicios en la nube:<br/><br/>Proxy, que controla la señalización SIP<br/>Procesador de medios, que controla los medios-excepto cuando es el desvío de medios en<br/><br/>Estos dos servicios tienen direcciones IP distintas en Microsoft Cloud, que se describen más adelante en este documento.<br/><br/>Para obtener más información, vea la [sección de equipos de Microsoft](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) en [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|Medios de transporte perfil|RTP/TCP/SAVP <br/>RTP/UDP/SAVP|
Las direcciones IP de servidor de seguridad y los puertos de medios de Microsoft Teams |Para obtener más información, vea [las direcciones URL de Office 365 y los intervalos de direcciones IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). |
|||

## <a name="licensing-and-other-requirements"></a>Concesión de licencias y otros requisitos 

Los usuarios de enrutamiento directo deben tener las siguientes licencias asignadas en Office 365: 

- Sistema telefónico de Microsoft 
- Microsoft Teams 
- Conferencia de Audio de Microsoft 

La licencia de conferencias de Audio es necesaria para agregar los participantes externos a las reuniones programadas, mediante marcación a ellos o al proporcionar el número telefónico. 
 
  > [!NOTE]
  > La licencia de E5 incluye el sistema telefónico y conferencias de Audio.   

Además, debe asegurarse de lo siguiente:
 
- CsOnlineVoiceRoutingPolicy se asigna al usuario. 
- Permitir que privada de llamada está habilitada en el nivel de inquilino para Microsoft Teams. 

Enrutamiento directo también es compatible con los usuarios que están autorizados para llamar a planeación de Microsoft. Sistema de teléfono de Microsoft con el Plan para llamar a puede enrutar algunas llamadas mediante la interfaz de enrutamiento directo. Sin embargo, los números de teléfono de los usuarios deben ser adquiridos en línea o trasladados a Microsoft.  

Combinación de conectividad de planeación de la llamada y el enrutamiento directo para el mismo usuario es opcional, pero podría ser útil, por ejemplo, cuando el usuario está asignado a un Plan de llamar a Microsoft, pero desea enrutar algunas llamadas a través de SBC. Uno de los escenarios más comunes son las llamadas al PBX de terceros.  Con PBX de terceros, todas las llamadas, excepto a los teléfonos conectados a ese PBX, las llamadas se enrutan a través de una llamada a planeación de Microsoft; pero las llamadas a los teléfonos conectados a sistemas PBX de terceros que se vaya a la SBC, por lo tanto, permanecer dentro de la red de empresa y no a la RTC. 

Para obtener más información acerca de las licencias del sistema de teléfono, vea [Opciones de planeación de Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)y [obtener el máximo partido de Office con Office 365](https://products.office.com/compare-all-microsoft-office-products?tab=2) . 

Para obtener más información acerca de las licencias del sistema de teléfono, vea [licencias de complemento de equipos de Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). 

## <a name="sbc-domain-names"></a>Nombres de dominio SBC

El nombre de dominio SBC debe ser de uno de los nombres registrados en "Dominios" del inquilino. No puede usar el *. inquilino onmicrosoft.com para el nombre FQDN de la SBC.

La siguiente tabla muestran ejemplos de nombres DNS registrados para el inquilino, si el nombre se puede usar como un FQDN para los SBC y ejemplos de nombres válidos de FQDN:

|**Nombre DNS**|**Se puede usar para el FQDN de SBC**|**Ejemplos de nombres FQDN**|
|:--- |:--- |:--- |
contoso.com|Sí|**Nombres válidos:**<br/>sbc1.contoso.com<br/>ssbcs15.contoso.com<br/>Europe.contoso.com|
|contoso.onmicrosoft.com|No|<br/>Uso de *. onmicrosoft.com dominios no es compatible con nombres SBC

Suponga que desea usar un nuevo nombre de dominio. Por ejemplo, el inquilino tiene contoso.com como un nombre de dominio registrado en el inquilino, y desea usar sbc1.sip.contoso.com. Antes de que puede emparejar un SBC con el nombre sbc1.sip.contoso.com, debe registrar la sip.contoso.com de nombre de dominio en "Dominios" en el inquilino. Si intenta el emparejamiento un SBC con sbc1.sip.contoso.com antes de registrar el nombre de dominio, recibirá el siguiente error: "No se puede usar el dominio"sbc1.sip.contoso.com"como no se configuró para este inquilino."
Después de agregar el nombre de dominio, también debe crear un usuario con el UPN user@sip.contoso.com y asigna una licencia de "Equipos". Pueden tardar hasta 24 horas para totalmente aprovisionar el nombre de dominio después de se agrega a "Dominios" de su inquilino, se crea un usuario con un nombre nuevo, y se asigna una licencia para el usuario. 

Es posible que una empresa puede tener varios espacios de direcciones SIP en un inquilino. Por ejemplo, una empresa podría tener contoso.com como un espacio de direcciones SIP y fabrikam.com como segundo espacio de direcciones SIP. Algunos usuarios tienen direcciones user@contoso.com y algunos usuarios tienen direcciones user@fabrikam.com. 

La SBC sólo necesita un FQDN y puede dar servicio a los usuarios de cualquier espacio de direcciones en el inquilino emparejado. Por ejemplo, un SBC con el nombre sbc1.contoso.com puede recibir y enviar el tráfico de RTC para los usuarios con direcciones user@contoso.com y user@fabrikam.com siempre y cuando estos espacios de direcciones SIP se registran en el mismo arrendatario.  

## <a name="public-trusted-certificate-for-the-sbc"></a>Certificado de confianza pública para el SBC

Microsoft recomienda encarecidamente que solicitar el certificado para el SBC mediante la generación de una certificación de solicitud (CSR) de firma. Para obtener instrucciones específicas sobre cómo generar un CSR para un SBC, consulte las instrucciones de interconexión o la documentación proporcionada por los proveedores SBC. 

  > [!NOTE]
  > La mayoría de certificación (CA) requieren que el tamaño de la clave privado a ser de al menos 2048. Téngalo en cuenta cuando se genera el CSR.

El certificado debe tener el FQDN SBC en el asunto, el nombre común o los campos de nombre alternativo de sujeto.

Como alternativa, el enrutamiento directo es compatible con un carácter comodín en SAN, y el carácter comodín debe ajustarse al estándar [RFC HTTP a través de TLS](https://tools.ietf.org/html/rfc2818#section-3.1). Un ejemplo sería utilizar *. contoso.com en el SAN, que coincidirá con el FQDN SBC sbc.contoso.com, pero no coincide con sbc.test.contoso.com.

El certificado debe ser generado por una de las siguientes entidades de certificación raíz:

- AffirmTrust
- Raíz AddTrust External
- Baltimore CyberTrust Root
- Buypass
- Cybertrust
- Entidad de certificación principal pública de clase 3
- Entidad de certificación raíz de seguro de comodo
- Marco alemán Telekom 
- DigiCert de entidad de certificación raíz Global
- Entidad de certificación raíz de DigiCert High Assurance EV
- Entrust
- GlobalSign
- Go Daddy.
- GeoTrust
- VeriSign, Inc. 
- Campo de estrellas 
- Symantec Enterprise raíz móvil de Microsoft 
- SwissSign
- Marca de tiempo Thawte entidad emisora de certificados
- Trustwave
- TeliaSonera 
- T-Systems GmbH internacional (Deutsche Telekom)
- QuoVadis

Microsoft está trabajando en la adición de entidades de certificación adicionales en función de las solicitudes del cliente. 

## <a name="sip-signaling-fqdns-and-firewall-ports"></a>Señalización SIP: Los puertos de firewall y los FQDN 

El punto de conexión para el enrutamiento directo son los FQDN de tres los siguientes:

- **sip.pstnhub.microsoft.com** – FQDN Global – debe intentar en primer lugar. Cuando la SBC envía una solicitud para resolver este nombre, los servidores DNS de Microsoft Azure devolución una dirección IP que apunta al centro de datos de Azure principal asignada a la SBC. La asignación se basa en las métricas de rendimiento de los centros de datos y la proximidad geográfica a la SBC. La dirección IP devuelta corresponde al FQDN principal.
- **sip2.pstnhub.microsoft.com** – secundario FQDN – geográficamente se asigna a la segunda región de prioridad.
- **sip3.pstnhub.microsoft.com** – terciario FQDN – geográficamente se asigna a la región de prioridad de terceros.

Es necesaria para la colocación de estos tres nombres de dominio completos en orden:

- Proporcionar una experiencia óptima (menos cargada y más cercana al centro de datos SBC asignada por consultar el primer nombre de dominio completo).
- Proporcionar conmutación por error cuando se establece la conexión desde un SBC para un centro de datos que está experimentando un problema temporal. Para obtener más información, vea el [mecanismo de conmutación por error](#failover-mechanism-for-sip-signaling) .  

Los FQDN: sip.pstnhub.microsoft.com, sip2.pstnhub.microsoft.com y sip3.pstnhub.microsoft.com, se resolverán a una de las siguientes direcciones IP:

- 52.114.148.0
- 52.114.132.46 
- 52.114.75.24 
- 52.114.76.76 
- 52.114.7.24 
- 52.114.14.70

Debe abrir los puertos para todas estas direcciones IP en el firewall para permitir el tráfico entrante y saliente a y desde las direcciones de señalización.  Si el servidor de seguridad es compatible con nombres DNS, el FQDN sip-all.pstnhub.microsoft.com se resuelve en todas las direcciones IP por encima.  Debe usar los siguientes puertos:

|**Tráfico**|**De**|**Hasta**|**Puerto de origen**|**Puerto de destino**|
|:--- |:--- |:--- |:--- |:--- |
|SIP/TLS|Proxy SIP|SBC|1024 – 65535|Definidos en la SBC|
SIP/TLS|SBC|Proxy SIP|Definidos en la SBC|5061|
||||||

### <a name="failover-mechanism-for-sip-signaling"></a>Mecanismo de conmutación por error para la señalización SIP

La SBC realiza una consulta DNS para resolver sip.pstnhub.microsoft.com. En función de la ubicación de SBC y las métricas de rendimiento de centro de datos, se selecciona el centro de datos principal. Si el centro de datos principal experimenta un problema, el SBC intentará la sip2.pstnhub.microsoft.com, que se resuelve en el segundo centro de datos asignado, y, en el caso poco frecuente que centros de datos en dos regiones no están disponibles, el SBC reintentos el último (FQDN sip3.pstnhub.Microsoft.com), que proporciona la dirección IP de terciario del centro de datos.

En la tabla siguiente resume las relaciones entre centros de datos principal, secundario y terciario:

|**Si es el centro de datos principal**|**EMEA**|**NOAM**|**ASIA**|
|:--- |:--- |:--- |:--- |
|El centro de datos secundaria (sip2.pstnhub.microsoft.com)|NOSOTROS|UNIÓN EUROPEA|NOSOTROS|
|El centro de datos terciario (sip3.pstnhub.microsoft.com)|ASIA|ASIA|UNIÓN EUROPEA|
|||||

## <a name="media-traffic-port-ranges"></a>El tráfico de medios: intervalos de puertos

El tráfico de medios fluye hacia y desde un servicio independiente en el Microsoft Cloud. El intervalo de IP para el tráfico de medios:
- 52.112.0.0 /14 (direcciones IP de 52.112.0.1 a 52.115.255.254).

El intervalo de puertos de los procesadores de medios se muestra en la siguiente tabla: 

|**Tráfico**|**De**|**Hasta**|**Puerto de origen**|**Puerto de destino**|
|:--- |:--- |:--- |:--- |:--- |
|UDP/SRTP|Procesador de medios|SBC|49 152 – 53 247|Definidos en la SBC|
|UDP/SRTP|SBC|Procesador de medios|Definidos en la SBC|49 152 – 53 247|
|

  > [!NOTE]
  > Microsoft recomienda al menos dos puertos por llamada simultánea en la SBC.

## <a name="media-traffic-codecs"></a>El tráfico de medios: códecs

### <a name="leg-between-sbc-and-cloud-media-processor-or-microsoft-teams-client"></a>Bifurcación entre el cliente SBC y procesador de medios en la nube o Teams de Microsoft.
Se aplica a caso de desvío de medios y sin desvío de los casos

La interfaz de enrutamiento directo en el tramo de entre el controlador de borde de sesión y el procesador de medios en la nube (sin desvío de medios) o entre el cliente de los equipos y la SBC (si se habilita el desvío de medios) puede usar los siguientes códecs:
- (SBC para procesador de medios en la nube) el desvío de medios de no: SEDA, G.711, G.722, G, 729
- Desvío de medios (SBC al cliente de los equipos): SEDA, G.711, G.722, G, OPUS 729,

Puede forzar el uso del códec específico en el controlador de borde de sesión mediante la exclusión de códecs no deseados de la oferta.

### <a name="leg-between-microsoft-teams-client--and-cloud-media-processor"></a>Bifurcación entre el cliente de los equipos de Microsoft y procesador de medios en la nube
Se aplica a caso sólo el desvío de medios que no sean. Con los flujos de medios de desvío de medios directamente entre el cliente de los equipos y SBC

En la bifurcación entre el procesador de medios en la nube y el cliente de Microsoft Teams SEDA o G.722 usa. La opción de códec en este tramo basado en algoritmos de Microsoft, que tener en cuenta varios parámetros. 


## <a name="supported-session-border-controllers-sbcs"></a>Admite controladores de borde de sesión (SBCs)

Microsoft sólo admite SBCs certificadas para emparejar con el enrutamiento directo. Debido a que Enterprise Voice es fundamental para los negocios, Microsoft ejecuta pruebas intensivas con el seleccionado SBCs y funciona con los proveedores SBC para asegurarse de los dos sistemas es compatible. 

Los dispositivos que se han validado aparecen como certificado para el enrutamiento directo de los equipos. Se garantizan que los dispositivos certificados para que funcione en todos los escenarios. 

Para obtener más información acerca de SBCs compatibles, vea la [lista de controladores de borde de sesión de certificados para el enrutamiento directo](direct-routing-border-controllers.md).

 
## <a name="see-also"></a>Vea también

[Configurar el enrutamiento directo](direct-routing-configure.md)



