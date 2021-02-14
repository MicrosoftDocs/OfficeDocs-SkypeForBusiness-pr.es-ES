---
title: Caso práctico de Teams voice Contoso
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
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786097"
---
# <a name="contoso-case-study-phone-system"></a>Caso práctico Contoso: Sistema telefónico

Según la ubicación geográfica y otros factores, Contoso tenía oficinas con las siguientes soluciones de telefonía:

- Tipo de sitio A: Skype Empresarial Telefonía IP empresarial

- Tipo de sitio B: sistemas de telefonía heredados tradicionales

- Tipo de sitio C: Una combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales


Para implementar una solución de Microsoft Phone System para toda la organización, Contoso tenía que determinar para cada tipo de sitio cuál de las siguientes opciones se usaría con Sistema telefónico para conectarse a la red telefónica conmutada &mdash; &mdash; (RTC):

- Sistema telefónico con plan de llamadas 

- Sistema telefónico con un operador RTC propio a través del enrutamiento directo 

- Combinación de sistema telefónico con plan de llamadas y sistema telefónico con un operador RTC propio a través del enrutamiento directo
 
Para determinar la solución adecuada para su organización, Contoso usó soluciones de telefonía de [Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) y las llamadas de sesión de Ignite 2019 [en Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo de sitio A: Skype Empresarial Telefonía IP empresarial 

El sitio de Skype Telefonía IP empresarial Contoso se ha configurado como un concentrador y se ha hablado. Había una ubicación central donde se conservaba la puerta de enlace RTC en la región que proporcionaba la conexión a RTC para los usuarios de Skype Empresarial Telefonía IP empresarial del país. A menudo, estas oficinas satélite no tenía su propia salida de Internet. Los números de estos usuarios residen en el tronco SIP que se conecta a un SBC existente. 

Para determinar si la SBC ya implementada está certificada para enrutamiento directo y omisión de medios, Contoso revisó la lista de controladores de borde de sesión certificados [para enrutamiento directo.](direct-routing-border-controllers.md)  

Los hábitos de marcación del usuario eran marcar a un usuario en el sistema de telefonía heredado con una extensión, incluso cuando el usuario tiene un cliente de Skype Empresarial disponible para el audio de punto a punto. 

Contoso se basa en su decisión en las siguientes preguntas:

- P. ¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  A. No 

- P. ¿Es necesario interactuar con sistemas PBX de terceros y otros equipos de telefonía?<br>
  A. No 

- P. ¿Debemos conservar nuestro operador actual de terceros?<br> A. Sí (países regulados) y No 

- P. ¿Es necesario implementar el ROI de los SBCs?<br> A. Sí y No  

- P. ¿Los planes de llamadas RTC de Microsoft están disponibles en esta región?<br> A. Sí y No 

Basándose en las respuestas a sus preguntas, Contoso decidió:

- Mueva los usuarios ubicados en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas. 

- Mueva los usuarios que no se encuentran en una región donde los planes de llamadas RTC están disponibles, los usuarios ubicados en un sitio donde aún no se ha cumplido el ROI de los SBCs y los usuarios que residen en un país que tiene normativas de telefonía a Sistema telefónico con enrutamiento directo. 

En el siguiente diagrama se muestra la implementación inicial de Telefonía IP empresarial empresarial y cómo se ha migrado esta implementación tanto a los planes de llamadas de Microsoft como al enrutamiento directo:

![Diagrama que muestra los estados de antes y después](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Tipo de sitio B: sistemas de telefonía tradicionales heredados

Contoso tenía muchas oficinas que aprovechaban los sistemas de telefonía heredados. Había un subconjunto de usuarios que tenían un número de teléfono E1.64 mientras que otros solo tenían una extensión. Estos números residen en el tronco TDM de la puerta de enlace RTC. El marcado entre sitios se configuró aprovechando un código de sitio delante de la extensión para determinar dónde enrutar la llamada. Los hábitos de marcación de los usuarios eran marcar por extensión.   

Contoso se basa en su decisión en las siguientes preguntas:

- P. ¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  A. No 

- P. ¿Es necesario interactuar con sistemas PBX de terceros y otros equipos de telefonía?<br> A. Sí

- P. ¿Debemos conservar nuestro operador actual de terceros?<br> A. No 

- P. ¿El plan de llamadas RTC de Microsoft está disponible en nuestra región?<br> A. Sí y No 

Basándose en las respuestas a sus preguntas, Contoso decidió: 

- Mueva los usuarios ubicados en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas. 

- Mueva los usuarios que no se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con enrutamiento directo. 

- Mantenga una conexión RTC a dispositivos analógicos críticos para la empresa.

Los siguientes diagramas muestran la implementación original del sistema heredado con sitios remotos y la migración a una implementación de enrutamiento directo con optimización de medios locales:

**Implementación heredada original**  
 ![ Diagrama que muestra los estados de antes y después](media/voice-case-study-2.png)


**Implementación con enrutamiento directo**

![Diagrama que muestra los estados de antes y después](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo de sitio C: combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales

Contoso Skype Empresarial y Telefonía IP empresarial los números de los usuarios residen en el tronco SIP al SBC desde el operador. Los números de los sistemas de telefonía tradicionales residen en el tronco TDM de la puerta de enlace RTC.   

Contoso se basa en su decisión en las siguientes preguntas:

- P. ¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  A. No 

- P. ¿Es necesario interactuar con sistemas PBX de terceros y otros equipos de telefonía?<br> A. No 

- P. ¿Debemos conservar nuestro operador actual de terceros?<br> A. No 

- P. ¿Es necesario implementar el ROI de los SBCs?<br> A. Sí y No  

- P. ¿El plan de llamadas RTC de Microsoft está disponible en esta región?<br> A. No 

Basándose en las respuestas a sus preguntas, Contoso decidió lo siguiente: 

- Para los usuarios de telefonía heredados que se habilitarán para enrutamiento directo, Contoso portó los números desde el tronco TDM al tronco SIP para la SBC, ya que SBC está certificado para enrutamiento directo. 

- Para admitir un subconjunto de usuarios que se mueven a Sistema telefónico y permitir la continuación del enrutamiento a través del sistema heredado, el sistema de telefonía heredado se estableció como el próximo salto a la SBC.   

- Además, para fomentar el cambio en el comportamiento de los usuarios y quitar la dependencia del marcado de extensiones entre sitios y entre sitios, Contoso proporciona una guía para usar Teams para todas las llamadas internas.  

Los siguientes diagramas muestran la implementación original del Telefonía IP empresarial skype empresarial y del sistema de telefonía heredado y la migración a una implementación mixta mediante enrutamiento directo:

**Implementación mixta original** 
 ![ Diagrama que se muestra antes del estado](media/voice-case-study-4.png)

**Implementación mixta con enrutamiento directo** 
 ![ Diagrama que se muestra antes del estado](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Planes de llamadas

Para determinar los requisitos de configuración para los planes de llamadas, Contoso revisó las decisiones de implementación [básicas del plan de llamadas.](calling-plan-landing-page.md#core-deployment-decisions) Se tomaron las decisiones resultantes: 

- P. ¿Mis usuarios necesitan llamadas internacionales?<br> A. Sí 

- P. ¿Tienen mis usuarios cada uno un número de teléfono que se haya recibido directamente?<br> A. Hoy no. Todos los usuarios habilitados recibirán un DID. 

- P. ¿Quiero enmascarar o deshabilitar la identificación de llamadas?<br> A. El identificador de llamada de un usuario se ocultará al número local de Contoso. 


## <a name="direct-routing"></a>Enrutamiento directo

Contoso ha asistido a Ignite para mantenerse al día sobre las características de Office 365, incluidas las disponibles con Sistema telefónico y Enrutamiento directo. El liderazgo técnico y los arquitectos usaron las instrucciones proporcionadas durante Ignite 2019 para determinar su dirección.  Sesiones clave que se han usado: 

- [Plan de éxito con enrutamiento directo de Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Actualizaciones de enrutamiento directo](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Configuración

### <a name="calling-plans-sites"></a>Sitios de planes de llamadas

Para obtener licencias y asignar números de teléfono a los usuarios, Contoso ha seguido los pasos de [Configurar planes de llamadas.](set-up-calling-plans.md) 

Debido a la cantidad de usuarios a los que era necesario asignar números de teléfono, Contoso decidió usar PowerShell para asignar los números de teléfono. Para obtener información sobre cómo asignar números con PowerShell, además de otras opciones de configuración, &mdash; &mdash; Contoso usó la información general de [PowerShell de Teams.](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>Sitios de enrutamiento directo

Para conectar la infraestructura de telefonía local de Contoso a Microsoft Teams, el administrador de Contoso ha seguido los pasos de Configurar enrutamiento directo y ha revisado el vídeo Enrutamiento directo en [Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obtener instrucciones. [](direct-routing-configure.md)  Contoso también hizo referencia a la documentación de implementación de enrutamiento directo del proveedor certificado de SBC. 

Una vez que se configuró el enrutamiento directo entre SBC y Microsoft Phone System, contoso era necesario para probar la configuración. Para ello, los administradores de Contoso usaron el cliente evaluador de SIP analizado en la sesión actualizaciones de enrutamiento directo en [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) La documentación y el script del cliente del evaluador SIP se descargaron desde el script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo.   


### <a name="local-media-optimization"></a>Optimización de medios locales

Contoso vio la oportunidad de aprovechar la optimización de medios locales en las distintas regiones de todo el mundo. Los escenarios compatibles con Contoso se describen en la [optimización de medios locales para enrutamiento directo.](direct-routing-media-optimization.md) La configuración de la optimización de medios locales se completó siguiendo las instrucciones del proveedor de SBC y de Microsoft. Los pasos de configuración para la optimización de medios locales incluyen: 

- Configurar los sitios de usuario y SBC 

- Configure la SBC según la especificación de proveedor de SBC, 

- Agregar direcciones IP de confianza externa a cada sitio usado para la optimización de medios locales    

- Definir la topología de red 

- Definir la topología de red virtual 

- Determinar el modo: Omitir siempre o solo para los usuarios locales 

## <a name="networking-considerations"></a>Consideraciones sobre redes

Contoso tenía un número de usuarios que necesitaban trabajar de forma remota durante un largo período de tiempo después de que se habilitara para Sistema telefónico. Los usuarios usaban una VPN para acceder a determinadas aplicaciones de línea de negocio. Mientras utilizas una VPN, los usuarios del sistema telefónico experimentaron una degradación de la calidad de la llamada. 

Para resolver el problema de calidad, Contoso implementó el túnel dividido de VPN, que permitía que el tráfico de Office 365 atravesara Internet mientras la conexión a las aplicaciones internas seguía estando en la VPN. Para implementar el túnel dividido de VPN, Contoso siguió las instrucciones de Implementar el túnel dividido de [VPN para Office 365.](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)  

 





