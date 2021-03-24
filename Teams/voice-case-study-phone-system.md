---
title: Caso práctico de Contoso de voz de Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Caso práctico de voz de Teams para una corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 995b4ddf9c07dea57c8d4de9940776d5137c2d02
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101036"
---
# <a name="contoso-case-study-phone-system"></a>Caso práctico de Contoso: Sistema telefónico

Según la ubicación geográfica y otros factores, Contoso tenía oficinas con las siguientes soluciones de telefonía:

- Tipo de sitio A: Skype Empresarial Telefonía IP empresarial

- Tipo de sitio B: Sistemas de telefonía heredados tradicionales

- Tipo de sitio C: Una combinación de skype empresarial Telefonía IP empresarial y sistemas de telefonía tradicional heredados


Para implementar una solución de Microsoft Phone System para toda su organización, Contoso tenía que determinar para cada tipo de sitio cuál de las siguientes opciones se usaría con Sistema telefónico para conectarse a la red telefónica conmutada &mdash; &mdash; (RTC):

- Sistema telefónico con plan de llamadas 

- Sistema telefónico con un operador RTC propio a través del enrutamiento directo 

- Combinación del sistema telefónico con el plan de llamadas y el sistema telefónico con un operador RTC propio a través del enrutamiento directo
 
Para determinar la solución adecuada para su organización, Contoso usó las soluciones de telefonía de [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) y las llamadas de sesión de Ignite 2019 [en Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo de sitio A: Skype Empresarial Telefonía IP empresarial 

Contoso Skype Empresarial Telefonía IP empresarial se ha configurado como concentrador y ha hablado. Había una ubicación central que conservaba la puerta de enlace RTC en la región que proporcionaba la conexión a la RTC para los usuarios de Skype Empresarial Telefonía IP empresarial en el país. A menudo, estas oficinas de satélite no tienen su propia salida de Internet. Los números de estos usuarios residían en el tronco SIP que se conectaba a un SBC existente. 

Para determinar si el SBC ya implementado está certificado para enrutamiento directo y omisión de medios, Contoso ha activado la lista de controladores de borde de sesión certificados [para enrutamiento directo.](direct-routing-border-controllers.md)  

Los hábitos de marcado del usuario eran marcar a un usuario en el sistema de telefonía heredado con una extensión, incluso cuando el usuario tiene un cliente de Skype Empresarial disponible para audio punto a punto. 

Contoso basó su decisión en las siguientes preguntas:

- P. ¿Necesitamos conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  A. No 

- P. ¿Necesitamos interoperar con sistemas PBX de terceros y otros equipos de telefonía?<br>
  A. No 

- P. ¿Necesitamos conservar nuestro operador de terceros actual?<br> A. Sí (países regulados) y No 

- P. ¿Necesitamos implementar el ROI en SBC?<br> A. Sí y No  

- P. ¿Los planes de llamadas RTC de Microsoft están disponibles en esta región?<br> A. Sí y No 

En función de las respuestas a sus preguntas, Contoso decidió:

- Mueva los usuarios que se encuentran en una región donde los planes de llamadas RTC están disponibles para El sistema telefónico con planes de llamadas. 

- Mueva los usuarios que no están ubicados en una región donde los planes de llamadas RTC están disponibles, los usuarios ubicados en un sitio en el que aún no se ha cumplido el retorno de la inversión en los SBC y los usuarios que residen en un país que tiene regulaciones de telefonía a Sistema telefónico con enrutamiento directo. 

En el siguiente diagrama se muestra la implementación inicial de Skype Empresarial Telefonía IP empresarial y cómo se ha migrado esta implementación a planes de llamadas de Microsoft y enrutamiento directo:

![Diagrama que muestra los estados antes y después](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Tipo de sitio B: Sistemas de telefonía heredados tradicionales

Contoso tenía muchas oficinas que aprovechaban sistemas de telefonía heredados. Había un subconjunto de usuarios que tenían un número de teléfono E1.64, mientras que otros solo tenían una extensión. Estos números residían en el tronco TDM de la puerta de enlace RTC. La marcación entre sitios se configuró aprovechando un código de sitio delante de la extensión para determinar dónde enrutar la llamada. Los hábitos de marcado de los usuarios eran marcar por extensión.   

Contoso basó su decisión en las siguientes preguntas:

- P. ¿Necesitamos conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  A. No 

- P. ¿Necesitamos interoperar con sistemas PBX de terceros y otros equipos de telefonía?<br> A. Sí

- P. ¿Necesitamos conservar nuestro operador de terceros actual?<br> A. No 

- P. ¿El Plan de llamadas RTC de Microsoft está disponible en nuestra región?<br> A. Sí y No 

En función de las respuestas a sus preguntas, Contoso decidió: 

- Mueva los usuarios que se encuentran en una región donde los planes de llamadas RTC están disponibles para El sistema telefónico con planes de llamadas. 

- Mueva los usuarios que no se encuentran en una región donde los planes de llamadas RTC están disponibles para El sistema telefónico con enrutamiento directo. 

- Mantener una conexión RTC a dispositivos analógicos críticos para la empresa.

En los diagramas siguientes se muestra la implementación original del sistema heredado con sitios remotos y la migración a una implementación de enrutamiento directo con optimización de medios locales:

**Implementación heredada original**  
 ![ Diagrama que muestra los estados antes y después](media/voice-case-study-2.png)


**Implementación con enrutamiento directo**

![Diagrama que muestra los estados antes y después](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo de sitio C: Combinación de skype empresarial Telefonía IP empresarial y sistemas de telefonía tradicional heredados

Contoso Skype Empresarial Telefonía IP empresarial los números de los usuarios residen en el tronco SIP al SBC desde el operador. Los números de los sistemas de telefonía tradicionales residían en el tronco TDM de la puerta de enlace RTC.   

Contoso basó su decisión en las siguientes preguntas:

- P. ¿Necesitamos conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  A. No 

- P. ¿Necesitamos interoperar con sistemas PBX de terceros y otros equipos de telefonía?<br> A. No 

- P. ¿Necesitamos conservar nuestro operador de terceros actual?<br> A. No 

- P. ¿Necesitamos implementar el ROI en SBC?<br> A. Sí y No  

- P. ¿El Plan de llamadas RTC de Microsoft está disponible en esta región?<br> A. No 

En función de las respuestas a sus preguntas, Contoso decidió lo siguiente: 

- Para los usuarios de telefonía heredados que se habilitarán para enrutamiento directo, Contoso portó los números del tronco TDM al tronco SIP para el SBC, ya que el SBC está certificado para enrutamiento directo. 

- Para admitir un subconjunto de usuarios que se mueven al sistema telefónico y permitir el enrutamiento continuo a través del sistema heredado, el sistema de telefonía heredado se ha configurado como el siguiente salto al SBC.   

- Además, para fomentar el cambio de comportamiento de los usuarios y quitar la dependencia en el marcado de extensiones entre sitios e internos, Contoso proporcionó instrucciones para usar Teams para todas las llamadas internas.  

En los diagramas siguientes se muestra la implementación original de skype empresarial Telefonía IP empresarial sistema de telefonía heredado y la migración a una implementación mixta mediante enrutamiento directo:

**Implementación mixta original** 
 ![ Diagrama que se muestra antes del estado](media/voice-case-study-4.png)

**Implementación mixta con enrutamiento directo** 
 ![ Diagrama que se muestra antes del estado](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Planes de llamadas

Para determinar los requisitos de configuración de los planes de llamadas, Contoso revisó las decisiones de implementación [principales del plan de llamadas.](calling-plan-landing-page.md#core-deployment-decisions) Se tomaron las decisiones resultantes: 

- P. ¿Mis usuarios necesitan llamadas internacionales?<br> A. Sí 

- P. ¿Mis usuarios tienen cada uno un número de teléfono did directo hacia adentro?<br> A. Hoy no. Todos los usuarios habilitados recibirán un DID. 

- P. ¿Quiero enmascarar o deshabilitar el identificador de llamada?<br> A. El identificador de llamada de un usuario se enmascarará con el número local de Contoso. 


## <a name="direct-routing"></a>Enrutamiento directo

Contoso asistió a Ignite para mantenerse al día en las características de Office 365, incluidas las disponibles con sistema telefónico y enrutamiento directo. Los directores técnicos y los arquitectos usaron las instrucciones proporcionadas durante el Ignite 2019 para determinar su dirección.  Sesiones clave que se usaron: 

- [Planear el éxito con enrutamiento directo de Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Actualizaciones para enrutamiento directo](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Configuración

### <a name="calling-plans-sites"></a>Sitios de planes de llamadas

Para obtener licencias y asignar números de teléfono a los usuarios, Contoso siguió los pasos de [Configurar planes de llamadas.](set-up-calling-plans.md) 

Debido al número de usuarios a los que había que asignar números de teléfono, Contoso decidió usar PowerShell para asignar los números de teléfono. Para obtener información sobre cómo asignar números mediante PowerShell, además de &mdash; otras opciones de &mdash; configuración, Contoso usó [la Información general de PowerShell de Teams.](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>Sitios de enrutamiento directo

Para conectar la infraestructura de telefonía local de Contoso a Microsoft Teams, el administrador de Contoso siguió los pasos de Configurar enrutamiento directo y revisó el vídeo Enrutamiento directo en [Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obtener instrucciones. [](direct-routing-configure.md)  Contoso también hizo referencia a la documentación de implementación de enrutamiento directo del proveedor certificado de SBC. 

Una vez que el enrutamiento directo se configuró entre el SBC y Microsoft Phone System, era necesario que Contoso probara la configuración. Para ello, los administradores de Contoso usaron el cliente probador SIP que se debatió en la sesión Actualizaciones para enrutamiento directo en [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) El script y la documentación del cliente de Prueba SIP se descargaron desde el script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo.   


### <a name="local-media-optimization"></a>Optimización de medios locales

Contoso vio la oportunidad de aprovechar la optimización de medios locales en las diferentes regiones de todo el mundo. Los escenarios admitidos para Contoso se describen en [Optimización de medios locales para enrutamiento directo.](direct-routing-media-optimization.md) La configuración de la optimización de medios locales se completó siguiendo las instrucciones del proveedor de SBC y microsoft. Los pasos de configuración de optimización de medios locales incluyen: 

- Configurar el usuario y los sitios de SBC 

- Configurar el SBC según la especificación de proveedor de SBC, 

- Agregar direcciones IP de confianza externa a cada sitio que se usa para la optimización de medios locales    

- Definir la topología de red 

- Definir la topología de red virtual 

- Determinar el modo: Omitir siempre o Solo para usuarios locales 

## <a name="networking-considerations"></a>Consideraciones de red

Contoso tenía un número de usuarios que necesitaban trabajar de forma remota durante un período prolongado de tiempo después de que se habilitara para El sistema telefónico. Los usuarios usaron VPN para acceder a determinadas aplicaciones de línea de negocio. Mientras se encuentra en VPN, los usuarios del sistema telefónico experimentaron una degradación de la calidad de las llamadas. 

Para resolver el problema de calidad, Contoso implementó el túnel dividido de VPN, que permitía que su tráfico de Office 365 atravesara Internet mientras la conexión a las aplicaciones internas permanecía en la VPN. Para implementar el túnel dividido de VPN, Contoso siguió las instrucciones de Implementación de túneles divididos [de VPN para Office 365.](/office365/enterprise/office-365-vpn-implement-split-tunnel)  

