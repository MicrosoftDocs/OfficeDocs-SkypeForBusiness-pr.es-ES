---
title: Skype para resoluciones de vídeo de cliente empresarial
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Resumen: Revise los requisitos de vídeo del cliente durante la planeación de Skype para Business Server.'
ms.openlocfilehash: a17e3e269f24e74c5403c053723d544898560f34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207240"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype para resoluciones de vídeo de cliente empresarial
 
**Resumen:** Revise los requisitos de vídeo del cliente durante la planeación de Skype para Business Server.
  
En este artículo se describe la compatibilidad de hardware de vídeo para Skype para las llamadas de vídeo empresarial y se describen los procedimientos para determinar la calidad de vídeo esperada para diversas equipo, tableta y las configuraciones de dispositivos móviles. 
  
LOS profesionales de TI encontrarán esta información útil en la evaluación de la idoneidad de equipos portátiles ya está en uso en su organización, o en consideración para su uso. Asimismo, puede buscar el [Catálogo de soluciones](https://partnersolutions.skypeforbusiness.com/solutionscatalog) para obtener información sobre dispositivos específicos.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Escritorio de Windows, Mac y tablet requisitos de vídeo y capacidades

Skype para la empresa utiliza la aceleración de hardware de vídeo de codificación y descodificación basada en el estándar H.264, MPEG-4 parte 10 avanzada codificación de vídeo. Esto permite que los equipos con velocidades de reloj de CPU inferiores para codificar y descodificar vídeo mayor resolución. Los requisitos de hardware de vídeo varían en función de la configuración del equipo y de la resolución de vídeo que se desea.
  
Vea también [los requisitos de hardware de Windows y Mac](https://products.office.com/en-us/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Requisitos de hardware de vídeo

|**Característica**|**Requisito**|
|:-----|:-----|
|Descodificación H.264 acelerada por hardware mediante DirectX Video Acceleration (DXVA)  <br/> |• Tarjeta de gráficos debe admitir DirectX 9.0 y debe exponer el modo de decodificación DXVA2_ModeH264_VLD_NoFGT y la API de DirectX 9.  <br/> • Debe estar instalado el controlador más reciente de la tarjeta de gráficos.  <br/> |
|Codificación H.264 acelerada por hardware: requisitos del conjunto de chips  <br/> |Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware Intel:  <br/> • Segunda y tercera generación Intel HD Graphics 2000, 2500, 3000 y 4000 conjuntos de chips (o versiones posteriores) con codificadores de vídeo de hardware integrados. Se requiere la instalación del controlador Intel HD Graphics 15.28.9.2884 o el controlador más reciente que contenga lo siguiente:  <br/> Controlador de pantalla • 9.17.10.2884 o el controlador más reciente  <br/> • Foundation de medios de hardware transformar versión (HMFT) 3.12.10.31 o la HMFT más reciente  <br/> Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware AMD:  <br/> • Motor de códec de vídeo de AMD, que está disponible en varias tarjetas gráficas independientes y en integrada acelerada por unidades de procesamiento de procesadores AMD una serie de acelerado. El controlador del motor de códec de vídeo de AMD 9.12.0.0 o superior debe estar instalado.  <br/> |
|Codificación H.264 acelerada por hardware: requisitos de la cámara  <br/> |Cámaras de vídeo USB con codificador de hardware H.264 integrado que cumplan la especificación USB Video Class (UVC) versión 1.5.  <br/> **Nota:** Skype para la empresa es compatible con cámaras de 1,5 UVC con Windows 8 o Windows 8.1, que incluye compatibilidad con UVC 1,5. Debido a que Windows 7 no incluye compatibilidad con 1,5 UVC, Skype para la empresa trata UVC 1,5 cámaras como cámaras regulares sin compatibilidad con la codificación de hardware. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinación de las capacidades de codificación y descodificación de vídeo H.264

Por lo general, son cuatro los factores principales que determinan la capacidad máxima de codificación y descodificación de una configuración de equipo determinada:
  
- Compatibilidad para descodificación acelerada por hardware mediante DXVA
    
- Compatibilidad para codificación acelerada por hardware
    
- Número de núcleos físicos
    
- Evaluación de la experiencia de Windows (WEI)
    
La Herramienta de evaluación del sistema de Windows (WinSAT) determina la WEI. Cuando se ejecuta la herramienta WinSAT, genera un documento XML Formal.Assessment en el equipo, en el directorio %windir%\Performance\WinSAT\DataStore. Este archivo XML contiene las siguientes dos puntuaciones que son especialmente importantes para determinar la capacidad de codificación y descodificación:
  
- VideoEncodeScore indica la capacidad de codificación de vídeo basada en software del equipo.
    
- El valor de GraphicsScore indica la capacidad de codificación acelerada por hardware del equipo.
    
Las siguientes tres tablas explican la capacidad máxima de codificación y descodificación de diferentes tipos de PC en función de la aceleración de hardware que admitan. Para resoluciones de 640 x 360 y superiores, la velocidad de fotogramas máxima admitida es de 30 fotogramas por segundo (fps). Para resoluciones inferiores a 640 x 360, la velocidad de fotogramas máxima admitida es de 15 fps.
  
**Equipo sin DXVA y sin codificador acelerado por hardware**

|**Resolución del codificador habilitado**|**Resolución del descodificador habilitado**|**Requisito**|
|:-----|:-----|:-----|
|424 x 240  <br/> |424 x 240 (640 x 360 a 15 fps para escenarios solo de recepción)  <br/> |1 núcleo y VideoEncodeScore ≥4.0  <br/> |
|640 x 360  <br/> |640 x 360  <br/> |2 núcleos y VideoEncodeScore ≥4.5  <br/> |
|640 x 360  <br/> |1280 x 720  <br/> |2 núcleos y VideoEncodeScore ≥4.5  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |4 núcleos y VideoEncodeScore ≥4.5  <br/> |
|1280 x 720  <br/> |1280 x 720  <br/> |4 núcleos y VideoEncodeScore ≥7.3  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 núcleos y VideoEncodeScore ≥7.3  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |N/D  <br/> |
   
**Equipo con DXVA pero sin codificador acelerado por hardware**

|**Resolución del codificador habilitado**|**Resolución del descodificador habilitado**|**Requisito**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920 x 1080  <br/> |1 núcleo y VideoEncodeScore ≥3.0  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |2 núcleos y VideoEncodeScore ≥4.5  <br/> |
|960 x 540  <br/> |1920 x 1080  <br/> |2 núcleos y VideoEncodeScore ≥6.0  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 núcleos y VideoEncodeScore ≥6.7  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |4 núcleos y VideoEncodeScore ≥8.2  <br/> |
   
> [!NOTE]
> La puntuación de WinSAT en Windows 7 está limitada a un máximo de 7,9. Por lo tanto, la capacidad de codificación de un equipo sin un codificador acelerado por hardware solo se puede lograr en Windows 8 o Windows 8.1, donde la puntuación máxima de WinSAT es de 9,9. 
  
**Equipo con DXVA y con codificador acelerado por hardware Intel HD Graphics**

|**Resolución del codificador habilitado**|**Resolución del descodificador habilitado**|**Requisito**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920 x 1080  <br/> |Todos los modelos de Intel HD Graphics de segunda y tercera generación  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |Todos los modelos de Intel HD Graphics de segunda y tercera generación y GraphicsScore ≥5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Capacidades de vídeo de dispositivos móviles

En la siguiente tabla se describe las resoluciones de vídeo máximas disponibles en dispositivos móviles compatibles. Para obtener más información acerca de la compatibilidad de dispositivos móviles, [comparación de características de cliente móvil de Skype para la empresa](mobile-feature-comparison.md).
  
|**Característica**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Resolución máxima de codificación H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S y versiones posteriores  <br/> |VGA: iPad 2 y versiones posteriores/iPad mini 1 y versiones posteriores  <br/> 720p: iPad Air/iPad mini 2/iPad Pro y versiones posteriores  <br/> |Hasta VGA según el modelo de dispositivo  <br/> |
|Resolución máxima de descodificación H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S y versiones posteriores  <br/> |VGA: iPad 2 y versiones posteriores/iPad mini 1 y versiones posteriores  <br/> 720p: iPad Air/iPad mini 2/iPad Pro y versiones posteriores  <br/> |Hasta VGA según el modelo de dispositivo  <br/> |
   

