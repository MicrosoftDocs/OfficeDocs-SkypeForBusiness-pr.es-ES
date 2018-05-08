---
title: Ejemplo de recopilación de requisitos de control de admisión de llamadas en Skype para Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: Proporciona un ejemplo detallado de la planeación para el control de admisión de llamadas en Skype para Business Server Enterprise Voice, incluida la recopilación de información acerca de sitios, regiones y ancho de banda de la red.
ms.openlocfilehash: 11cf309c47143411a10d32eacf0305ead3d01294
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server-2015"></a>Ejemplo: recopilación de los requisitos para el servicio de control de admisión de llamadas en Skype Empresarial Server 2015
 
Proporciona un ejemplo detallado de la planeación para el control de admisión de llamadas en Skype para Business Server Enterprise Voice, incluida la recopilación de información acerca de sitios, regiones y ancho de banda de la red.
  
Este ejemplo muestra cómo planificar e implementar el servicio de control de admisión de llamadas (CAC). De forma general, esto consta de las siguientes actividades:
  
1. Identificar todos los concentradores de red y redes troncales (llamados regiones de red).
    
2. Identificar el Skype para sitio central Business Server que administrará el CAC para cada región de red.
    
3. Identificar y definir los sitios de red que están conectados a cada región de red.
    
4. Para cada sitio de red cuya conexión a la red WAN está limitada por el ancho de banda, se describe la capacidad de ancho de banda de la conexión WAN y los límites de ancho de banda que al administrador de red ha establecido para Skype para el tráfico de medios Business Server, si procede. No necesitas incluir sitios cuya conexión a la red WAN no tiene ancho de banda restringido.
    
5. Asocia cada subred de la red a un sitio de red.
    
6. Asigna los vínculos entre las regiones de red. Para cada vínculo, describir su capacidad de ancho de banda y los límites que el Administrador de red ha colocado en Skype para el tráfico de medios de Business Server.
    
7. Define una ruta entre cada par de regiones de red.
    
## <a name="gather-the-required-information"></a>Recopilar la información necesaria

Para preparar el servicio de control de admisión de llamadas, recopila la información descrita en los pasos siguientes:
  
1. Identifica las regiones de red. Una región de red representa una red troncal de red o un concentrador de red. 
    
    Una red troncal de red o un concentrador de red forma parte de una infraestructura de red informática que interconecta diversas partes de red, que proporciona una ruta de acceso para el intercambio de información entre distintas redes LAN o subredes. Una red troncal puede asociar diversas redes, desde una ubicación pequeña a una amplia zona geográfica. La capacidad de la red troncal suele ser mayor que la de las redes conectadas a ella.
    
    Nuestra topología de ejemplo tiene tres regiones de red: Norteamérica, EMEA y APAC. Una región de red incluye una colección de sitios de red. Trabaja con el administrador de la red para definir las regiones de red de tu empresa.
    
2. Identificar el sitio central de cada región de red asociado. Un sitio central contiene al menos un servidor Front-End y el Skype para la implementación de Business Server que administrará el CAC para todo el tráfico de medios que pasa a través de la conexión WAN de la región de red.
    
   **Una red de la empresa de ejemplo, se divide en tres regiones de red**

     ![Ejemplo de topología de red con 3 regiones de red](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)
  
    > [!NOTE]
    > Una red de conmutación de etiquetas multiprotocolo (MPLS) necesita representarse como una región de red en la que cada ubicación geográfica tiene un sitio de red correspondiente. Para obtener información detallada, vea el tema "de[componentes y topologías para llamar al control de admisión de Skype para profesionales de 2015](components-and-topologies.md)" en la documentación de planeación. 
  
    En el anterior ejemplo de topología de red, hay tres regiones de red, cada uno con un Skype para sitio central Business Server que administra el CAC. El sitio central adecuado para una región de red se elige por la proximidad geográfica. Como el tráfico de medios será mayor dentro de las regiones de red, la propiedad por proximidad geográfica lo hace independiente y seguirá siendo funcional aunque otros sitios centrales dejen de estar disponibles. 
    
    En este ejemplo, un Skype para la implementación de empresa denominada a Chicago es el sitio central para la región de América del Norte.
    
    Todos los Skype para los usuarios de negocio en Norteamérica están hospedados en servidores de la implementación de Chicago. En la tabla siguiente se muestran los sitios centrales de las tres regiones de red.
    
    **Regiones de red y sus sitios centrales asociados**

    |**Región de red**|**Sitio central**|
    |:-----|:-----|
    |Norteamérica  <br/> |Chicago  <br/> |
    |EMEA  <br/> |Londres  <br/> |
    |APAC  <br/> |Pekín  <br/> |
   
    > [!NOTE]
    > Según su Skype de topología de servidores de negocio, el mismo sitio central puede asignarse a varias regiones de red. 
  
3. En cada región de red, identifica todos los sitios de red (oficinas o ubicaciones) cuyas conexiones WAN no tienen ancho de banda restringido. Como estos sitios no tienen ancho de banda restringido, no necesitas aplicarles directivas de ancho de banda de CAC.
    
    En el ejemplo que se muestra en la siguiente tabla, tres sitios de red no tienen vínculos WAN de ancho de banda restringido: Nueva York, Chicago y Detroit.
    
   **Sitios de red no restringidos por el ancho de banda de WAN**

   |**Sitio de red**|**Región de red**|
   |:-----|:-----|
   |Nueva York  <br/> |Norteamérica  <br/> |
   |Chicago  <br/> |Norteamérica  <br/> |
   |Detroit  <br/> |Norteamérica  <br/> |
   
4. En cada región de red, identifica todos los sitios de red que se conectan a la región de red a través de vínculos WAN de ancho de banda restringido.
    
    Para asegurar la calidad de audio y vídeo, recomendamos que estos sitios de red de ancho de banda restringido tengan las redes WAN supervisadas y directivas de ancho de banda del CAC que limiten el flujo del tráfico de medios (voz o vídeo) hacia la región de red y desde ella.
    
    En el ejemplo que se muestra en la siguiente tabla, hay tres sitios de red que están restringidos por el ancho de banda de WAN: Portland, Reno y Albuquerque.
    
   **Sitios de red restringidos por el ancho de banda de WAN**

   |**Sitio de red**|**Región de red**|
   |:-----|:-----|
   |Albuquerque  <br/> |Norteamérica  <br/> |
   |Reno  <br/> |Norteamérica  <br/> |
   |Portland  <br/> |Norteamérica  <br/> |
   
   **CAC red región Norteamérica con tres sitios de red que no tienen restricciones de ancho de banda (Chicago, Nueva York y Detroit) y tres sitios de red que están restringidos por el ancho de banda de WAN (Portland, Reno y Albuquerque)**

     ![Ejemplo de sitios de la red restringidos por el ancho de banda de la WAN](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)
  
5. Para cada vínculo WAN de ancho de banda restringido, determina lo siguiente:
    
  - Límite general de ancho de banda que deseas establecer para todas las sesiones simultáneas de audio. Si una nueva sesión de audio hará que este límite que se supere, Skype para Business Server no permite la sesión iniciar.
    
  - Límite de ancho de banda que deseas establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.
    
  - Límite general de ancho de banda que deseas establecer para todas las sesiones simultáneas de vídeo. Si una nueva sesión de vídeo hará que este límite que se supere, Skype para Business Server no permite la sesión iniciar.
    
  - Límite de ancho de banda que deseas establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.
    
    **Sitios de red con información de restricciones de ancho de banda WAN (ancho de banda en kbps)**

    |**Sitio de red**|**Región de red**|**Límite de ancho de banda**|**Límite de audio**|**Límite de sesión de audio**|**Límite de vídeo**|**Límite de sesión de vídeo**|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |Albuquerque  <br/> |Norteamérica  <br/> |5.000  <br/> |2.000  <br/> |175  <br/> |1.400  <br/> |700  <br/> |
    |Reno  <br/> |Norteamérica  <br/> |10.000  <br/> |4.000  <br/> |175  <br/> |2.800  <br/> |700  <br/> |
    |Portland  <br/> |Norteamérica  <br/> |5.000  <br/> |4.000  <br/> |175  <br/> |2.800  <br/> |700  <br/> |
    |Nueva York  <br/> |Norteamérica  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |
    |Chicago  <br/> |Norteamérica  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |
    |Detroit  <br/> |Norteamérica  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |
   
6. Para cada subred de la red, especifica el sitio de red asociado.
    
    > [!IMPORTANT]
    > Cada subred de la red necesita estar asociada a un sitio de red, aunque el sitio de red no esté restringido por el ancho de banda. Esto es porque el servicio de control de admisión de llamadas usa la información de la subred para determinar el sitio de red en que está situado un extremo. Cuando se determinan las ubicaciones de ambas partes de la sesión, el servicio de control de admisión de llamadas puede determinar si existe suficiente ancho de banda para establecer una llamada. Cuando se establece una sesión a través de un vínculo que no tiene límites de ancho de banda, se genera una alerta. 
  
    > [!IMPORTANT]
    > Si implementas servidores perimetrales de audio o vídeo, las direcciones IP públicas de cada servidor perimetral necesitan estar asociadas al sitio de red en el que se implementa el servidor perimetral. Cada dirección IP pública del servidor perimetral A/V necesita agregarse a las opciones de configuración de la red como subred con una máscara de subred de 32. Por ejemplo, si implementas servidores perimetrales A/V en Chicago, para cada dirección IP externa de los servidores, crea una subred con una máscara de subred de 32 y asocia el sitio de red Chicago a dichas subredes. Para obtener información detallada acerca de las direcciones IP públicas, vea [Planear los requisitos de red de Skype para profesionales de 2015](../../plan-your-deployment/network-requirements/network-requirements.md). 
  
    Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red, pero que no están asociadas a una subred; o bien, la subred que incluye las direcciones IP no está asociada a un sitio de red. Esta alerta no aparecerá más que una vez en un período de 8 horas. A continuación se ofrece la información sobre las alertas relevante y un ejemplo:
    
    **Origen**: servicio de directivas de ancho de banda CS (principal) 
    
    **Número de evento**: 36034
    
    **Nivel**: 2
    
    **Descripción**: las subredes de las siguientes direcciones IP: \<lista de direcciones IP\> no son está configurada o las subredes no están asociadas a un sitio de red. 
    
    **Causa**: las subredes de las correspondientes direcciones IP faltan en las opciones de configuración de la red o las subredes no están asociadas a un sitio de red. 
    
    **Solución**: agregue las subredes correspondientes a la lista anterior de direcciones IP a las opciones de configuración de red y asocie cada subred a un sitio de red.
    
    Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera:
    
    a. Asegúrese de que la dirección IP 10.121.248.226 esté asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 esté asociada a la subred 10.121.249.0/24.
    
    b. Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 esté asociada a un sitio de red.
    
   **Sitios de red y subredes asociadas (ancho de banda en kbps)**

   |**Sitio de red**|**Región de red**|**Límite de ancho de banda**|**Límite de audio**|**Límite de sesión de audio**|**Límite de vídeo**|**Límite de sesión de vídeo**|**Subredes**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Albuquerque  <br/> |Norteamérica  <br/> |5.000  <br/> |2.000  <br/> |175  <br/> |1.400  <br/> |700  <br/> |172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   |Reno  <br/> |Norteamérica  <br/> |10.000  <br/> |4.000  <br/> |175  <br/> |2.800  <br/> |700  <br/> |157.57.210.0/23, 172.28.151.128/25  <br/> |
   |Portland  <br/> |Norteamérica  <br/> |5.000  <br/> |4.000  <br/> |175  <br/> |2.800  <br/> |700  <br/> |172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/> |
   |Nueva York  <br/> |Norteamérica  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   |Chicago  <br/> |Norteamérica  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |157.57.211.0/23, 172.28.152.128/25  <br/> |
   |Detroit  <br/> |Norteamérica  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |(sin límite)  <br/> |172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/> |
   
7. En Skype para el control de admisión de llamadas de Business Server, las conexiones entre regiones de red se denominan vínculos de región. Para cada vínculo de región, determina lo siguiente, tal como has hecho para los sitios de red:
    
   - Límite general de ancho de banda que deseas establecer para todas las sesiones simultáneas de audio. Si una nueva sesión de audio hará que este límite que se supere, Skype para Business Server no permite la sesión iniciar.
    
   - Límite de ancho de banda que deseas establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.
    
   - Límite general de ancho de banda que deseas establecer para todas las sesiones simultáneas de vídeo. Si una nueva sesión de vídeo hará que este límite que se supere, Skype para Business Server no permite la sesión iniciar.
    
   - Límite de ancho de banda que deseas establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.
    
   **Vínculos de región de red con los límites de ancho de banda asociados**

     ![Ejemplo de limitaciones entre 3 regiones](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)
  
   **Información de ancho de banda del vínculo de región (ancho de banda en kbps)**

   |**Nombre del vínculo de región**|**Primera región**|**Segunda región**|**Límite de ancho de banda**|**Límite de audio**|**Límite de sesión de audio**|**Límite de vídeo**|**Límite de sesión de vídeo**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |NA-EMEA-LINK  <br/> |Norteamérica  <br/> |EMEA  <br/> |50.000  <br/> |20.000  <br/> |175  <br/> |14.000  <br/> |700  <br/> |
   |EMEA-APAC-LINK  <br/> |EMEA  <br/> |APAC  <br/> |25.000  <br/> |10.000  <br/> |175  <br/> |7.000  <br/> |700  <br/> |
   
8. Define una ruta entre cada par de regiones de red.
    
    > [!NOTE]
    > Se requieren dos vínculos para la ruta entre las regiones Norteamérica y APAC porque no existe ningún vínculo de región que las conecte directamente. 
  
   **Rutas de región**

   |**Nombre de ruta de región**|**Primera región**|**Segunda región**|**Vínculos de región**|
   |:-----|:-----|:-----|:-----|
   |NA-EMEA-ROUTE  <br/> |Norteamérica  <br/> |EMEA  <br/> |NA-EMEA-LINK  <br/> |
   |EMEA-APAC-ROUTE  <br/> |EMEA  <br/> |APAC  <br/> |EMEA-APAC-LINK  <br/> |
   |NA-APAC-ROUTE  <br/> |Norteamérica  <br/> |APAC  <br/> |NA-EMEA-LINK, EMEA-APAC-LINK  <br/> |
   
9. Para cada par de sitios de red que están conectados directamente por un solo vínculo (denominado vínculo entre sitios), determine lo siguiente:
    
     - Límite general de ancho de banda que deseas establecer para todas las sesiones simultáneas de audio. Si una nueva sesión de audio hará que este límite que se supere, Skype para Business Server no permite la sesión iniciar.
    
     - Límite de ancho de banda que deseas establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.
    
     - Límite general de ancho de banda que deseas establecer para todas las sesiones simultáneas de vídeo. Si una nueva sesión de vídeo hará que este límite que se supere, Skype para Business Server no permite la sesión iniciar.
    
     - Límite de ancho de banda que deseas establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.
    
   **Región de red CAC Norteamérica con los límites de ancho de banda del vínculo entre sitios entre Reno y Albuquerque y las capacidades de ancho de banda**

     ![Ejemplo de sitios de la red restringidos por el ancho de banda de la WAN](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)
  
   **Información de ancho de banda para un vínculo entre sitios entre dos sitios de red (ancho de banda en kbps)**

   |**Nombre del vínculo entre sitios**|**Primer sitio**|**Segundo sitio**|**Límite de ancho de banda**|**Límite de audio**|**Límite de sesión de audio**|**Límite de vídeo**|**Límite de sesión de vídeo**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Reno-Albu-Intersite-Link  <br/> |Reno  <br/> |Albuquerque  <br/> |20.000  <br/> |12.000  <br/> |175  <br/> |5.000  <br/> |700  <br/> |
   
### <a name="next-steps"></a>Pasos siguientes

Una vez recopilada la información necesaria, puede realizar la implementación de CAC mediante el Skype para Shell de administración de servidor empresarial o Skype para el Panel de Control de servidor empresarial.
  
> [!NOTE]
> Si bien puede realizar la mayoría de las tareas de configuración de red mediante el uso de Skype para el Panel de Control de servidor empresarial, para crear subredes y vínculos entre sitios, debe usar Skype para Shell de administración de servidor empresarial. Para obtener información detallada, vea [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps) y [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps). 
  

