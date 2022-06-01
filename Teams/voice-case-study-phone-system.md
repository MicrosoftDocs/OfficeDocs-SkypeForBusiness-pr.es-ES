---
title: 'Caso práctico contoso: Sistema telefónico para una corporación multinacional'
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
description: 'Teams caso práctico de voz para la corporación multinacional: sistema telefónico'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95ba8e36948a3d61a2e81f9c1954919709eb3a77
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823671"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Caso práctico contoso: Sistema telefónico para una corporación multinacional

Según la ubicación geográfica y otros factores, Contoso tenía oficinas que usaban las siguientes soluciones de telefonía:

- Tipo de sitio A: Skype Empresarial Telefonía IP empresarial

- Tipo de sitio B: Sistemas de telefonía heredados tradicionales

- Tipo de sitio C: Una combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales


Para implementar una solución del sistema Teléfono Microsoft para toda su organización, Contoso tuvo que determinar&mdash;para cada tipo&mdash;de sitio cuáles de las siguientes opciones se usarían con Sistema telefónico para conectarse a la red telefónica conmutada (RTC):

- Sistema telefónico con plan de llamadas 

- Sistema telefónico con su propio operador RTC a través del enrutamiento directo 

- Combinación de Sistema telefónico con plan de llamadas y Sistema telefónico con su propio operador RTC a través del enrutamiento directo
 
Para determinar la solución adecuada para su organización, Contoso usó [Planear la solución de voz de Teams](/microsoftteams/cloud-voice-landing-page) y las llamadas a la sesión de Ignite 2019 [en Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-for-calling-in-microsoft-teams-ignite-2019-edition/ba-p/974935).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo de sitio A: Skype Empresarial Telefonía IP empresarial 

Contoso Skype Empresarial Telefonía IP empresarial se configuró como concentrador y habló. Había una ubicación central que mantiene la puerta de enlace RTC en la región que proporcionaba la conexión a la RTC para los usuarios de Skype Empresarial Telefonía IP empresarial en el país. A menudo, estas oficinas satélite no tenían su propia salida de Internet. Los números para estos usuarios residían en el tronco del SIP que conecta a un SBC existente. 

Para determinar si el SBC ya implementado está certificado para enrutamiento directo y omisión multimedia, Contoso ha comprobado la [lista de controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).  

Los hábitos de marcación del usuario eran llamar a un usuario en el sistema de telefonía heredado mediante una extensión, incluso cuando el usuario tiene un cliente de Skype Empresarial disponible para el audio de punto a punto. 

Contoso basó su decisión en las siguientes preguntas:

- Q. ¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  Un. No 

- Q. ¿Es necesario interoperar con sistemas PBX de terceros y otros equipos de telefonía?<br>
  Un. No 

- Q. ¿Es necesario conservar nuestro operador de terceros actual?<br> Un. Sí (países regulados) y No 

- Q. ¿Es necesario implementar el ROI en los SBCs?<br> Un. Sí y No  

- Q. ¿Están disponibles los planes de llamadas RTC de Microsoft en esta región?<br> Un. Sí y No 

En función de las respuestas a sus preguntas, Contoso decidió:

- Mueva los usuarios que se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas. 

- Mueva los usuarios que no se encuentren en una región donde los planes de llamadas RTC estén disponibles, los usuarios ubicados en un sitio donde aún no se haya cumplido el ROI de los SCA y los usuarios que residan en un país que tenga normativas de telefonía para Sistema telefónico con enrutamiento directo. 

El siguiente diagrama muestra la implementación inicial Skype Empresarial Telefonía IP empresarial y cómo se migró esta implementación a los planes de llamadas de Microsoft y al enrutamiento directo:

![El diagrama muestra los estados de antes y después.](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Tipo de sitio B: Sistemas de telefonía heredados tradicionales

Contoso tenía muchas oficinas que aprovechaban los sistemas de telefonía heredados. Había un subconjunto de usuarios que tenían un número de teléfono E1.64, mientras que otros solo tenían una extensión. Estos números residían en el tronco TDM al gateway RTC. La marcación entre sitios se configuró aprovechando un código de sitio delante de la extensión para determinar dónde redirigir la llamada. Los hábitos de marcación de los usuarios eran marcar por extensión.   

Contoso basó su decisión en las siguientes preguntas:

- Q. ¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  Un. No 

- Q. ¿Es necesario interoperar con sistemas PBX de terceros y otros equipos de telefonía?<br> Un. Sí

- Q. ¿Es necesario conservar nuestro operador de terceros actual?<br> Un. No 

- Q. ¿Está disponible el plan de llamadas RTC de Microsoft en nuestra región?<br> Un. Sí y No 

En función de las respuestas a sus preguntas, Contoso decidió: 

- Mueva los usuarios que se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas. 

- Mueva los usuarios que no se encuentren en una región donde los planes de llamadas RTC estén disponibles para Sistema telefónico con enrutamiento directo. 

- Mantener una conexión RTC a dispositivos analógicos críticos para la empresa.

Los siguientes diagramas muestran la implementación original del sistema heredado con sitios remotos y la migración a una implementación de enrutamiento directo con optimización de medios locales:

**Implementación** 
![ heredada original Un diagrama muestra los estados de antes y después.](media/voice-case-study-2.png)


**Implementación con enrutamiento directo**

![Diagrama que muestra los estados de antes y después.](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo de sitio C: Combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales

Contoso Skype Empresarial Telefonía IP empresarial los números de los usuarios residen en el tronco SIP al SBC desde el operador. Los números de los sistemas de telefonía tradicionales residían en el tronco TDM a la puerta de enlace RTC.   

Contoso basó su decisión en las siguientes preguntas:

- Q. ¿Es necesario conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  Un. No 

- Q. ¿Es necesario interoperar con sistemas PBX de terceros y otros equipos de telefonía?<br> Un. No 

- Q. ¿Es necesario conservar nuestro operador de terceros actual?<br> Un. No 

- Q. ¿Es necesario implementar el ROI en los SBCs?<br> Un. Sí y No  

- Q. ¿Está disponible el plan de llamadas RTC de Microsoft en esta región?<br> Un. No 

En función de las respuestas a sus preguntas, Contoso decidió lo siguiente: 

- Para los usuarios de telefonía heredados que se habilitarán para el enrutamiento directo, Contoso ha realizado la portabilidad de los números del tronco TDM al tronco SIP para el SBC, ya que el SBC está certificado para el enrutamiento directo. 

- Para admitir un subconjunto de usuarios que pasan a Sistema telefónico y permitir el enrutamiento continuo a través del sistema heredado, el sistema de telefonía heredado se configuró como el siguiente salto a la SBC.   

- Además, para animar el cambio de comportamiento de los usuarios y quitar la dependencia en el marcado de extensión entre sitios y dentro del sitio, Contoso proporciona instrucciones para usar Teams para todas las llamadas internas.  

Los siguientes diagramas muestran la implementación original de Skype Empresarial Telefonía IP empresarial y del sistema de telefonía heredado y la migración a una implementación mixta con enrutamiento directo:

**Implementación**
![ mixta original Diagrama 1 que muestra el estado anterior.](media/voice-case-study-4.png)

**Implementación mixta con enrutamiento**
![ directo Diagrama 2 que muestra el estado anterior.](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Planes de llamadas

Para determinar los requisitos de configuración para los planes de llamadas, Contoso revisó las [decisiones de implementación básicas del plan de llamadas](calling-plan-landing-page.md#core-deployment-decisions). Se tomaron las decisiones resultantes: 

- Q. ¿Mis usuarios necesitan llamadas internacionales?<br> Un. Sí 

- Q. ¿Mis usuarios tienen cada uno un número de teléfono DE ENTRADA directa?<br> A. Hoy no. Todos los usuarios habilitados recibirán un DID. 

- Q. ¿Quiero enmascarar o deshabilitar el identificador de llamadas?<br> Un. El identificador de llamada de un usuario se enmascarará al número local de Contoso. 


## <a name="direct-routing"></a>Enrutamiento directo

Contoso asistió a Ignite para mantenerse al día con Office 365 características, incluidas las disponibles con Teléfono sistema y enrutamiento directo. Los responsables técnicos y los arquitectos utilizaron la orientación proporcionada durante el Ignite 2019 para determinar su dirección.  Sesiones clave que se usaron: 

- [Planear el éxito con Microsoft Teams enrutamiento directo](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)

- [Actualizaciones de enrutamiento directo](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)


## <a name="configuration"></a>Configuración

### <a name="calling-plans-sites"></a>Sitios de planes de llamadas

Para obtener licencias y asignar números de teléfono a los usuarios, Contoso siguió los pasos [de Configurar planes de llamadas](set-up-calling-plans.md). 

Debido al número de usuarios a los que era necesario asignar números de teléfono, Contoso decidió usar PowerShell para asignar los números de teléfono. Para obtener información sobre cómo asignar números mediante PowerShell&mdash;, además de otras opciones de configuración&mdash;, Contoso usó la [Teams Introducción a PowerShell](teams-powershell-overview.md).  

### <a name="direct-routing-sites"></a>Sitios de enrutamiento directo

Para conectar la infraestructura de telefonía local de Contoso a Microsoft Teams, el administrador de Contoso siguió los pasos de [Configurar enrutamiento directo](direct-routing-configure.md) y revisó el vídeo [Enrutamiento directo en Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obtener instrucciones.  Contoso también se refirió a la documentación de implementación de enrutamiento directo por el proveedor certificado de SBC. 

Una vez configurado El enrutamiento directo entre el SBC y el sistema de Teléfono Microsoft, era necesario que Contoso probara la configuración. Para ello, los administradores de Contoso usaron el cliente del probador SIP que se debatió en la [sesión "Actualizaciones de enrutamiento directo en Ignite 2019](https://techcommunity.microsoft.com/t5/microsoft-teams-events-blog/ignite-live-blog-session-vce20-updates-for-direct-routing/ba-p/1025138). El script y la documentación del cliente del probador SIP se descargaron del script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo.   


### <a name="local-media-optimization"></a>Optimización de medios locales

Contoso ha aprovechado la oportunidad de aprovechar la Optimización de medios locales en las diferentes regiones de todo el mundo. Los escenarios admitidos para Contoso se describen en [Optimización de medios locales para enrutamiento directo](direct-routing-media-optimization.md). La configuración de la optimización de medios locales se completó siguiendo las instrucciones del proveedor de SBC y de Microsoft. Los pasos de configuración para optimización de medios locales incluyen: 

- Configurar el usuario y los sitios de SBC 

- Configure el SBC según la especificación del proveedor de SBC, 

- Agregar direcciones IP de confianza externas a cada sitio usado para optimización de medios locales    

- Definir la topología de red 

- Definir la topología de red virtual 

- Determinar el modo: Omitir siempre o Solo para usuarios locales 

## <a name="networking-considerations"></a>Consideraciones de redes

Contoso tenía varios usuarios que necesitaban trabajar de forma remota durante un largo período de tiempo después de que se habilitaran para Sistema telefónico. Los usuarios usaron VPN para acceder a determinadas aplicaciones de línea de negocio. Mientras se usaba una VPN, la Sistema telefónico los usuarios experimentaron una degradación de la calidad de la llamada. 

Para resolver el problema de calidad, Contoso implementó el túnel dividido de VPN, lo que permitió que su tráfico de Office 365 atravesara Internet mientras la conexión a las aplicaciones internas permanecía en la VPN. Para implementar el túnel dividido de VPN, Contoso siguió las instrucciones en [Implementar el túnel dividido de VPN para Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).  

