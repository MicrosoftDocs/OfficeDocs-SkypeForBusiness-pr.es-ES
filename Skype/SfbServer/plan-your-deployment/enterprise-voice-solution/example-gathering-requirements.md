---
title: Ejemplo de recopilación de requisitos para el control de admisión de llamadas en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
description: Proporciona un ejemplo detallado de la planeación del control de admisión de llamadas en Skype Empresarial Server Telefonía IP empresarial, incluida la recopilación de información sobre los sitios, las regiones y el ancho de banda de la red.
ms.openlocfilehash: a51ffe9248a8d5daf1e21a9c20bb753ddb26898f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825690"
---
# <a name="example-gathering-requirements-for-call-admission-control-in-skype-for-business-server"></a>Ejemplo: Recopilación de requisitos para el control de admisión de llamadas en Skype Empresarial Server

Proporciona un ejemplo detallado de la planeación del control de admisión de llamadas en Skype Empresarial Server Telefonía IP empresarial, incluida la recopilación de información sobre los sitios, las regiones y el ancho de banda de la red.

Este ejemplo muestra cómo planear e implementar el control de admisión de llamadas (CAC). De forma general, esto consta de las siguientes actividades:

1. Identificar todos los concentradores de red y redes troncales (llamados regiones de red).

2. Identifique el sitio central de Skype Empresarial Server que administrará el CAC para cada región de red.

3. Identificar y definir los sitios de red que están conectados a cada región de red.

4. Para cada sitio de red cuya conexión a la WAN tenga ancho de banda restringido, describa la capacidad de ancho de banda de la conexión WAN y los límites de ancho de banda que el administrador de red ha establecido para el tráfico de medios de Skype Empresarial Server, si procede. No es necesario incluir sitios cuya conexión a la red WAN no tiene ancho de banda restringido.

5. Asociar cada subred de la red a un sitio de red.

6. Asignar los vínculos entre las regiones de red. Para cada vínculo, describa su capacidad de ancho de banda y los límites que el administrador de red haya establecido en el tráfico multimedia de Skype Empresarial Server.

7. Definir una ruta entre cada par de regiones de red.

## <a name="gather-the-required-information"></a>Recopilar la información necesaria

Para preparar el control de admisión de llamadas, recopile la información descrita en los pasos siguientes:

1. Identificar las regiones de red. Una región de red representa una red troncal de red o un concentrador de red. 

    Una red troncal de red o un concentrador de red forma parte de una infraestructura de red informática que interconecta diversas partes de red, que proporciona una ruta de acceso para el intercambio de información entre distintas redes LAN o subredes. Una red troncal puede asociar diversas redes, desde una ubicación pequeña a una amplia zona geográfica. La capacidad de la red troncal suele ser mayor que la de las redes conectadas a ella.

    Nuestra topología de ejemplo tiene tres regiones de red: Norteamérica, EMEA y APAC. Una región de red incluye una colección de sitios de red. Trabaje con el administrador de la red para definir las regiones de red de su empresa.

2. Identificar el sitio central asociado de cada región de red. Un sitio central contiene al menos un servidor front-end y es la implementación de Skype Empresarial Server que administrará el CAC para todo el tráfico de medios que pasa a través de la conexión WAN de la región de red.

   **Red de empresa de ejemplo dividida en tres regiones de red**

     ![Ejemplo de topología de red con 3 regiones de red](../../media/Plan_CS_VoiceCAC_example3networkregions.jpg)

    > [!NOTE]
    > Una red de conmutación de etiquetas multiprotocolo (MPLS) debe representarse como una región de red en la que cada ubicación geográfica tiene un sitio de red correspondiente. Para obtener más información, consulte [Componentes y topologías para el control de admisión de llamadas en Skype Empresarial.](components-and-topologies.md) 

    En el ejemplo anterior de topología de red, hay tres regiones de red, cada una con un sitio central de Skype Empresarial Server que administra el CAC. El sitio central adecuado para una región de red se elige por la proximidad geográfica. Como el tráfico de medios será mayor dentro de las regiones de red, la propiedad por proximidad geográfica lo hace independiente y seguirá siendo funcional aunque otros sitios centrales dejen de estar disponibles. 

    En este ejemplo, una implementación de Skype Empresarial denominada Chicago es el sitio central de la región Norteamérica.

    Todos los usuarios de Skype Empresarial en Norteamérica se encuentran en servidores de la implementación de Chicago. En la tabla siguiente se muestran los sitios centrales de las tres regiones de red.

    **Regiones de red y sus sitios centrales asociados**

    |**Región de red**|**Sitio central**|
    |:-----|:-----|
    |Norteamérica  <br/> |Guadalajara  <br/> |
    |EMEA  <br/> |Londres  <br/> |
    |APAC  <br/> |Beijing  <br/> |

    > [!NOTE]
    > Según la topología de Skype Empresarial Server, el mismo sitio central puede asignarse a varias regiones de red. 

3. En cada región de red, identifique todos los sitios de red (oficinas o ubicaciones) cuyas conexiones WAN no tienen ancho de banda restringido. Como estos sitios no tienen ancho de banda restringido, no es necesario aplicarles directivas de ancho de banda de CAC.

    En el ejemplo que se muestra en la siguiente tabla, tres sitios de red no tienen vínculos WAN de ancho de banda restringido: Nueva York, Chicago y Detroit.

   **Sitios de red no restringidos por el ancho de banda de WAN**


   | **Sitio de red** | **Región de red**   |
   |:-----------------|:---------------------|
   | Nueva York  <br/>  | Norteamérica  <br/> |
   | Guadalajara  <br/>   | Norteamérica  <br/> |
   | Detroit  <br/>   | Norteamérica  <br/> |


4. En cada región de red, identifique todos los sitios de red que se conectan a la región de red a través de vínculos WAN de ancho de banda restringido.

    Para asegurar la calidad de audio y vídeo, se recomienda que estos sitios de red de ancho de banda restringido tengan las redes WAN supervisadas y directivas de ancho de banda del CAC que limiten el flujo del tráfico de medios (voz o vídeo) hacia la región de red y desde ella.

    En el ejemplo que se muestra en la siguiente tabla, hay tres sitios de red que están restringidos por el ancho de banda de WAN: Portland, Reno y Albuquerque.

   **Sitios de red restringidos por el ancho de banda de WAN**

   |**Sitio de red**|**Región de red**|
   |:-----|:-----|
   |Albuquerque  <br/> |Norteamérica  <br/> |
   |Reno  <br/> |Norteamérica  <br/> |
   |Portland  <br/> |Norteamérica  <br/> |

   **Región de red para CAC Norteamérica con tres sitios de red que no están restringidos por el ancho de banda (Chicago, Nueva York y Detroit) y tres sitios de red que están restringidos por el ancho de banda de WAN (Portland, Reno y Albuquerque)**

     ![Sitios de red de ejemplo restringidos por ancho de banda WAN](../../media/Plan_CS_VoiceCAC_comparisonof6regionsandconstraints.jpg)

5. Para cada vínculo WAN de ancho de banda restringido, determine lo siguiente:

   - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio. Si una nueva sesión de audio hace que se supere este límite, Skype Empresarial Server no permite que se inicie la sesión.

   - Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.

   - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo. Si una nueva sesión de vídeo hace que se supere este límite, Skype Empresarial Server no permite que se inicie la sesión.

   - Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.

     **Sitios de red con información de restricción de ancho de banda de WAN (ancho de banda en kbps)**


     | **Sitio de red**   | **Región de red**   | **Límite de ancho de banda**      | **Límite de audio**   | **Límite de sesión de audio** | **Límite de vídeo**   | **Límite de sesión de vídeo** |
     |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|
     | Albuquerque  <br/> | Norteamérica  <br/> | 5,000  <br/>      | 2,000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              |
     | Reno  <br/>        | Norteamérica  <br/> | 10 000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | Portland  <br/>    | Norteamérica  <br/> | 5,000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              |
     | Nueva York  <br/>    | Norteamérica  <br/> | (sin límite)  <br/> | (sin límite)  <br/> | (sin límite)  <br/>       | (sin límite)  <br/> | (sin límite)  <br/>       |
     | Guadalajara  <br/>     | Norteamérica  <br/> | (sin límite)  <br/> | (sin límite)  <br/> | (sin límite)  <br/>       | (sin límite)  <br/> | (sin límite)  <br/>       |
     | Detroit  <br/>     | Norteamérica  <br/> | (sin límite)  <br/> | (sin límite)  <br/> | (sin límite)  <br/>       | (sin límite)  <br/> | (sin límite)  <br/>       |


6. Para cada subred de la red, especifique el sitio de red asociado.

    > [!IMPORTANT]
    > Cada subred de la red debe estar asociada a un sitio de red, aunque el sitio de red no esté restringido por el ancho de banda. Esto se debe a que el control de admisión de llamadas usa la información de la subred para determinar el sitio de red en que está situado un extremo. Cuando se determinan las ubicaciones de ambas partes de la sesión, el control de admisión de llamadas puede determinar si existe suficiente ancho de banda para establecer una llamada. Cuando se establece una sesión a través de un vínculo que no tiene límites de ancho de banda, se genera una alerta. 

    > [!IMPORTANT]
    > Si implementa servidores perimetrales de audio/vídeo, las direcciones IP públicas de cada servidor perimetral deben estar asociadas al sitio de red en el que se implementa el servidor perimetral. Cada dirección IP pública del servidor perimetral A/V debe agregarse a las opciones de configuración de la red como subred con una máscara de subred de 32. Por ejemplo, si implementa servidores perimetrales A/V en Chicago, para cada dirección IP externa de los servidores, cree una subred con una máscara de subred de 32 y asocie el sitio de red Chicago a dichas subredes. Para obtener más información sobre las direcciones IP públicas, consulte [Plan network requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md). 

    Aparecerá una alerta de indicador de estado clave (KHI), que especifica una lista de direcciones IP que están incluidas en la red pero que no están asociadas a una subred, o bien la subred que incluye las direcciones IP no está asociada a un sitio de red. Esta alerta no aparecerá más que una vez en un período de ocho horas. A continuación se ofrece la información de alerta relevante y un ejemplo:

    **Origen**: Servicio de directivas de ancho de banda CS (núcleo) 

    **Número de evento**: 36034

    **Nivel**: 2

    **Descripción:** las subredes de las siguientes direcciones IP: no están configuradas o las subredes no \<List of IP Addresses\> están asociadas a un sitio de red. 

    **Causa**: las subredes de las correspondientes direcciones IP faltan en las opciones de configuración de la red o las subredes no están asociadas a un sitio de red. 

    **Solución**: agregue las subredes correspondientes a la lista anterior de direcciones IP a las opciones de configuración y asocie cada subred a un sitio de red.

    Por ejemplo, si la lista de direcciones IP de la alerta especifica 10.121.248.226 y 10.121.249.20, estas direcciones IP no están asociadas a una subred o la subred a la que están asociadas no pertenece a un sitio de red. Si 10.121.248.0/24 y 10.121.249.0/24 son las subredes correspondientes a estas direcciones, este problema se puede resolver de la siguiente manera:

    a. Asegúrese de que la dirección IP 10.121.248.226 está asociada a la subred 10.121.248.0/24 y la dirección IP 10.121.249.20 está asociada a la subred 10.121.249.0/24.

    b. Asegúrese de que cada una de las subredes 10.121.248.0/24 y 10.121.249.0/24 está asociada a un sitio de red.

   **Sitios de red y subredes asociadas (ancho de banda en kbps)**


   | **Sitio de red**   | **Región de red**   | **Límite de ancho de banda**      | **Límite de audio**   | **Límite de sesión de audio** | **Límite de vídeo**   | **Límite de sesión de vídeo** | **Subredes**                                                            |
   |:-------------------|:---------------------|:------------------|:------------------|:------------------------|:------------------|:------------------------|:-----------------------------------------------------------------------|
   | Albuquerque  <br/> | Norteamérica  <br/> | 5,000  <br/>      | 2,000  <br/>      | 175  <br/>              | 1,400  <br/>      | 700  <br/>              | 172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24  <br/> |
   | Reno  <br/>        | Norteamérica  <br/> | 10 000  <br/>     | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 157.57.210.0/23, 172.28.151.128/25  <br/>                              |
   | Portland  <br/>    | Norteamérica  <br/> | 5,000  <br/>      | 4,000  <br/>      | 175  <br/>              | 2,800  <br/>      | 700  <br/>              | 172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23  <br/>                  |
   | Nueva York  <br/>    | Norteamérica  <br/> | (sin límite)  <br/> | (sin límite)  <br/> | (sin límite)  <br/>       | (sin límite)  <br/> | (sin límite)  <br/>       | 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24  <br/> |
   | Guadalajara  <br/>     | Norteamérica  <br/> | (sin límite)  <br/> | (sin límite)  <br/> | (sin límite)  <br/>       | (sin límite)  <br/> | (sin límite)  <br/>       | 157.57.211.0/23, 172.28.152.128/25  <br/>                              |
   | Detroit  <br/>     | Norteamérica  <br/> | (sin límite)  <br/> | (sin límite)  <br/> | (sin límite)  <br/>       | (sin límite)  <br/> | (sin límite)  <br/>       | 172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23  <br/>                  |


7. En el control de admisión de llamadas de Skype Empresarial Server, las conexiones entre regiones de red se denominan vínculos de región. Para cada vínculo de región, determine lo siguiente, tal como hizo para los sitios de red:

   - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio. Si una nueva sesión de audio hace que se supere este límite, Skype Empresarial Server no permite que se inicie la sesión.

   - Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.

   - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo. Si una nueva sesión de vídeo hace que se supere este límite, Skype Empresarial Server no permite que se inicie la sesión.

   - Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.

   **Vínculos de región de red con límites de ancho de banda asociados**

     ![Ejemplo de limitaciones entre 3 regiones](../../media/Plan_CS_VoiceCAC_limitsbetween3regions.jpg)

   **Información de ancho de banda de vínculos de región (ancho de banda en kbps)**


   | **Nombre del vínculo de región**  | **Primera región**     | **Segunda región** | **Límite de ancho de banda**  | **Límite de audio** | **Límite de sesión de audio** | **Límite de vídeo** | **Límite de sesión de vídeo** |
   |:----------------------|:---------------------|:------------------|:--------------|:----------------|:------------------------|:----------------|:------------------------|
   | NA-EMEA-LINK  <br/>   | Norteamérica  <br/> | EMEA  <br/>       | 50 000  <br/> | 20,000  <br/>   | 175  <br/>              | 14,000  <br/>   | 700  <br/>              |
   | EMEA-APAC-LINK  <br/> | EMEA  <br/>          | APAC  <br/>       | 25 000  <br/> | 10 000  <br/>   | 175  <br/>              | 7,000  <br/>    | 700  <br/>              |


8. Definir una ruta entre cada par de regiones de red.

    > [!NOTE]
    > Se requieren dos vínculos para la ruta entre las regiones Norteamérica y APAC porque no existe ningún vínculo de región que las conecte directamente. 

   **Rutas de región**


   | **Nombre de la ruta de región**  | **Primera región**     | **Segunda región** | **Vínculos de región**                    |
   |:-----------------------|:---------------------|:------------------|:------------------------------------|
   | NA-EMEA-ROUTE  <br/>   | Norteamérica  <br/> | EMEA  <br/>       | NA-EMEA-LINK  <br/>                 |
   | EMEA-APAC-ROUTE  <br/> | EMEA  <br/>          | APAC  <br/>       | EMEA-APAC-LINK  <br/>               |
   | NA-APAC-ROUTE  <br/>   | Norteamérica  <br/> | APAC  <br/>       | NA-EMEA-LINK, EMEA-APAC-LINK  <br/> |


9. Para cada par de sitios de red que estén conectados directamente por un solo vínculo (denominado vínculo entre sitios), determine lo siguiente:

     - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de audio. Si una nueva sesión de audio hace que se supere este límite, Skype Empresarial Server no permite que se inicie la sesión.

     - Límite de ancho de banda que desea establecer para cada sesión individual de audio. El límite predeterminado de ancho de banda para CAC es de 175 kbps, pero el administrador puede modificarlo.

     - Límite general de ancho de banda que desea establecer para todas las sesiones simultáneas de vídeo. Si una nueva sesión de vídeo hace que se supere este límite, Skype Empresarial Server no permite que se inicie la sesión.

     - Límite de ancho de banda que desea establecer para cada sesión individual de vídeo. El límite predeterminado de ancho de banda para CAC es de 700 kbps, pero el administrador puede modificarlo.

   **Región de red para CAC Norteamérica con indicación de las capacidades de ancho de banda y los límites de ancho de banda del vínculo entre sitios entre Reno y Albuquerque**

     ![Ejemplo de sitios de red restringidos por ancho de banda WAN](../../media/Plan_CS_VoiceCAC_limitsforNAdirectlinksRenoAlbuq.jpg)

   **Información de ancho de banda de un vínculo entre sitios entre dos sitios de red (ancho de banda en kbps)**

   |**Nombre del vínculo entre sitios**|**Primer sitio**|**Segundo sitio**|**Límite de ancho de banda**|**Límite de audio**|**Límite de sesión de audio**|**Límite de vídeo**|**Límite de sesión de vídeo**|
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |Reno-Albu-Intersite-Link  <br/> |Reno  <br/> |Albuquerque  <br/> |20,000  <br/> |12,000  <br/> |175  <br/> |5,000  <br/> |700  <br/> |

### <a name="next-steps"></a>Pasos siguientes

Una vez que haya recopilado la información necesaria, puede realizar la implementación del CAC mediante el Shell de administración de Skype Empresarial Server o el Panel de control de Skype Empresarial Server.

> [!NOTE]
> Aunque puede realizar la mayoría de las tareas de configuración de red con el Panel de control de Skype Empresarial Server, para crear subredes y vínculos entre sitios, debe usar el Shell de administración de Skype Empresarial Server. Para obtener más información, [vea New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps) y [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps). 


