---
title: 'Caso práctico de Contoso: Sistema telefónico para una corporación multinacional'
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
description: 'Teams caso de voz para la corporación multinacional: sistema telefónico'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ee15ef9bb42a28023c86963dd9100797c51edc3
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587149"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Caso práctico de Contoso: Sistema telefónico para una corporación multinacional

Según la ubicación geográfica y otros factores, Contoso tenía oficinas con las siguientes soluciones de telefonía:

- Tipo de sitio A: Skype Empresarial Telefonía IP empresarial

- Tipo de sitio B: Sistemas de telefonía heredados tradicionales

- Tipo de sitio C: una combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales


Para implementar una solución del sistema Teléfono Microsoft para toda su organización, Contoso tenía que determinar para cada tipo de sitio cuál de las siguientes opciones se usaría con Sistema telefónico para conectarse a la red telefónica conmutada &mdash; &mdash; (RTC):

- Sistema telefónico con plan de llamadas 

- Sistema telefónico con un operador RTC propio a través del enrutamiento directo 

- Combinación de Sistema telefónico con plan de llamadas y Sistema telefónico con un operador RTC propio a través del enrutamiento directo
 
Para determinar la solución adecuada para su organización, Contoso usó soluciones de telefonía de [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) y la sesión Ignite 2019 [Llamadas en Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo de sitio A: Skype Empresarial Telefonía IP empresarial 

Contoso Skype Empresarial Telefonía IP empresarial se ha configurado como concentrador y ha hablado. Había una ubicación central que conservaba la puerta de enlace RTC en la región que proporcionaba la conexión a la RTC para los Skype Empresarial Telefonía IP empresarial en el país. A menudo, estas oficinas de satélite no tienen su propia salida de Internet. Los números de estos usuarios residían en el tronco SIP que se conectaba a un SBC existente. 

Para determinar si el SBC ya implementado está certificado para enrutamiento directo y omisión de medios, Contoso ha activado la lista de controladores de borde de sesión certificados [para enrutamiento directo.](direct-routing-border-controllers.md)  

Los hábitos de marcado del usuario eran marcar a un usuario en el sistema de telefonía heredado con una extensión, incluso cuando el usuario tiene un cliente de Skype Empresarial disponible para audio punto a punto. 

Contoso basó su decisión en las siguientes preguntas:

- Q. ¿Necesitamos conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  A. No 

- Q. ¿Necesitamos interoperar con sistemas PBX de terceros y otros equipos de telefonía?<br>
  A. No 

- Q. ¿Necesitamos conservar nuestro operador de terceros actual?<br> A. Sí (países regulados) y No 

- Q. ¿Necesitamos implementar el ROI en SBC?<br> A. Sí y No  

- Q. ¿Los planes de llamadas RTC de Microsoft están disponibles en esta región?<br> A. Sí y No 

En función de las respuestas a sus preguntas, Contoso decidió:

- Mueva los usuarios que se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas. 

- Mueva los usuarios que no se encuentran en una región donde los planes de llamadas RTC están disponibles, los usuarios ubicados en un sitio en el que aún no se ha cumplido el ROI de los SBC y los usuarios que residían en un país que tiene normativas de telefonía para Sistema telefónico con enrutamiento directo. 

En el siguiente diagrama se muestran las Skype Empresarial Telefonía IP empresarial iniciales y cómo se ha migrado esta implementación a planes de llamadas de Microsoft y enrutamiento directo:

![Diagrama muestra los estados antes y después.](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Tipo de sitio B: Sistemas de telefonía heredados tradicionales

Contoso tenía muchas oficinas que aprovechaban sistemas de telefonía heredados. Había un subconjunto de usuarios que tenían un número de teléfono E1.64, mientras que otros solo tenían una extensión. Estos números residían en el tronco TDM de la puerta de enlace RTC. La marcación entre sitios se configuró aprovechando un código de sitio delante de la extensión para determinar dónde enrutar la llamada. Los hábitos de marcado de los usuarios eran marcar por extensión.   

Contoso basó su decisión en las siguientes preguntas:

- Q. ¿Necesitamos conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  A. No 

- Q. ¿Necesitamos interoperar con sistemas PBX de terceros y otros equipos de telefonía?<br> A. Sí

- Q. ¿Necesitamos conservar nuestro operador de terceros actual?<br> A. No 

- Q. ¿El Plan de llamadas RTC de Microsoft está disponible en nuestra región?<br> A. Sí y No 

En función de las respuestas a sus preguntas, Contoso decidió: 

- Mueva los usuarios que se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con planes de llamadas. 

- Mueva los usuarios que no se encuentran en una región donde los planes de llamadas RTC están disponibles para Sistema telefónico con enrutamiento directo. 

- Mantener una conexión RTC a dispositivos analógicos críticos para la empresa.

En los diagramas siguientes se muestra la implementación original del sistema heredado con sitios remotos y la migración a una implementación de enrutamiento directo con optimización de medios locales:

**Implementación heredada original**  
 ![ Un diagrama muestra los estados antes y después.](media/voice-case-study-2.png)


**Implementación con enrutamiento directo**

![Un diagrama que muestra los estados antes y después.](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo de sitio C: Combinación de Skype Empresarial Telefonía IP empresarial y sistemas de telefonía heredados tradicionales

Contoso Skype Empresarial Telefonía IP empresarial los números de los usuarios residen en el tronco SIP al SBC desde el operador. Los números de los sistemas de telefonía tradicionales residían en el tronco TDM de la puerta de enlace RTC.   

Contoso basó su decisión en las siguientes preguntas:

- Q. ¿Necesitamos conservar la funcionalidad proporcionada por nuestra implementación local?<br>
  A. No 

- Q. ¿Necesitamos interoperar con sistemas PBX de terceros y otros equipos de telefonía?<br> A. No 

- Q. ¿Necesitamos conservar nuestro operador de terceros actual?<br> A. No 

- Q. ¿Necesitamos implementar el ROI en SBC?<br> A. Sí y No  

- Q. ¿El Plan de llamadas RTC de Microsoft está disponible en esta región?<br> A. No 

En función de las respuestas a sus preguntas, Contoso decidió lo siguiente: 

- Para los usuarios de telefonía heredados que se habilitarán para enrutamiento directo, Contoso portó los números del tronco TDM al tronco SIP para el SBC, ya que el SBC está certificado para enrutamiento directo. 

- Para admitir un subconjunto de usuarios que se mueven a Sistema telefónico y permitir el enrutamiento continuo a través del sistema heredado, el sistema de telefonía heredado se ha configurado como el siguiente salto al SBC.   

- Además, para fomentar el cambio de comportamiento de los usuarios y quitar la dependencia en el marcado de extensiones entre sitios e internos, Contoso proporcionó instrucciones para usar Teams para todas las llamadas internas.  

Los diagramas siguientes muestran la implementación original Skype Empresarial Telefonía IP empresarial sistema de telefonía heredado y la migración a una implementación mixta mediante enrutamiento directo:

**Implementación mixta original** 
 ![ Diagrama 1 que muestra el estado anterior.](media/voice-case-study-4.png)

**Implementación mixta con enrutamiento directo** 
 ![ Diagrama 2 que muestra el estado anterior.](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Planes de llamadas

Para determinar los requisitos de configuración de los planes de llamadas, Contoso revisó las decisiones de implementación [principales del plan de llamadas.](calling-plan-landing-page.md#core-deployment-decisions) Se tomaron las decisiones resultantes: 

- Q. ¿Mis usuarios necesitan llamadas internacionales?<br> A. Sí 

- Q. ¿Mis usuarios tienen cada uno un número de teléfono did directo hacia adentro?<br> A. Hoy no. Todos los usuarios habilitados recibirán un DID. 

- Q. ¿Quiero enmascarar o deshabilitar el identificador de llamada?<br> A. El identificador de llamada de un usuario se enmascarará con el número local de Contoso. 


## <a name="direct-routing"></a>Enrutamiento directo

Contoso asistió a Ignite para mantenerse al día Office 365 características, incluidas las disponibles con Teléfono sistema y enrutamiento directo. Los directores técnicos y los arquitectos usaron las instrucciones proporcionadas durante el Ignite 2019 para determinar su dirección.  Sesiones clave que se usaron: 

- [Planear el éxito con Microsoft Teams enrutamiento directo](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Actualizaciones para enrutamiento directo](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Configuración

### <a name="calling-plans-sites"></a>Sitios de planes de llamadas

Para obtener licencias y asignar números de teléfono a los usuarios, Contoso siguió los pasos de [Configurar planes de llamadas.](set-up-calling-plans.md) 

Debido al número de usuarios a los que había que asignar números de teléfono, Contoso decidió usar PowerShell para asignar los números de teléfono. Para obtener información sobre cómo asignar números mediante PowerShell, además de otras opciones de configuración, Contoso usó el Teams información general &mdash; &mdash; de [PowerShell.](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>Sitios de enrutamiento directo

Para conectar la infraestructura de telefonía local de Contoso a Microsoft Teams, el administrador de Contoso siguió los pasos de [Configurar](direct-routing-configure.md) enrutamiento directo y revisó el vídeo Enrutamiento directo [en Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obtener instrucciones.  Contoso también hizo referencia a la documentación de implementación de enrutamiento directo del proveedor certificado de SBC. 

Una vez que el enrutamiento directo se configuró entre el sistema SBC y Teléfono Microsoft, era necesario que Contoso probara la configuración. Para ello, los administradores de Contoso usaron el cliente probador SIP que se debatió en la sesión Actualizaciones para enrutamiento directo en [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) El script y la documentación del cliente de Prueba SIP se descargaron desde el script de PowerShell para probar las conexiones del controlador de borde de sesión de enrutamiento directo.   


### <a name="local-media-optimization"></a>Optimización de medios locales

Contoso vio la oportunidad de aprovechar la optimización de medios locales en las diferentes regiones de todo el mundo. Los escenarios admitidos para Contoso se describen en [Optimización de medios locales para enrutamiento directo.](direct-routing-media-optimization.md) La configuración de la optimización de medios locales se completó siguiendo las instrucciones del proveedor de SBC y microsoft. Los pasos de configuración de optimización de medios locales incluyen: 

- Configurar el usuario y los sitios de SBC 

- Configurar el SBC según la especificación de proveedor de SBC, 

- Agregar direcciones IP de confianza externa a cada sitio que se usa para la optimización de medios locales    

- Definir la topología de red 

- Definir la topología de red virtual 

- Determinar el modo: Omitir siempre o Solo para usuarios locales 

## <a name="networking-considerations"></a>Consideraciones de red

Contoso tenía un número de usuarios que necesitaban trabajar de forma remota durante un período prolongado de tiempo después de que se habilitara para Sistema telefónico. Los usuarios usaron VPN para acceder a determinadas aplicaciones de línea de negocio. Mientras se encuentra en VPN, Sistema telefónico usuarios experimentaron una degradación de la calidad de las llamadas. 

Para resolver el problema de calidad, Contoso implementó el túnel dividido de VPN, que permitía que su tráfico de Office 365 atravesara Internet mientras la conexión a las aplicaciones internas permanecía en la VPN. Para implementar el túnel dividido de VPN, Contoso siguió las instrucciones de [Implementar túneles](/office365/enterprise/office-365-vpn-implement-split-tunnel)divididos de VPN para Office 365 .  

