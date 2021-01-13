---
title: Resoluciones de vídeo del cliente de Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Resumen: revise los requisitos de vídeo del cliente durante la planeación de Skype Empresarial Server.'
ms.openlocfilehash: 9be23512462781c55ef94b72b4dbbba60e15e5ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816060"
---
# <a name="skype-for-business-client-video-resolutions"></a>Resoluciones de vídeo del cliente de Skype Empresarial
 
**Resumen:** Revise los requisitos de vídeo del cliente durante la planeación de Skype Empresarial Server.
  
En este artículo se describe la compatibilidad de hardware de vídeo para las videollamadas de Skype Empresarial y se describe cómo determinar la calidad de vídeo esperada para diversas configuraciones de equipos, tabletas y dispositivos móviles. 
  
Los profesionales de TI encontrarán esta información útil para evaluar la idoneidad de los portátiles que ya están en uso en su organización o en consideración para su uso. También pueden buscar información en [dispositivos](https://partnersolutions.skypeforbusiness.com/solutionscatalog) específicos en el Catálogo de soluciones.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Requisitos y funcionalidades de vídeo para equipos de escritorio, Mac y tabletas de Windows

Skype Empresarial usa la aceleración de hardware para codificar y decodificar vídeo en función del estándar de codificación avanzada de vídeo H.264/MPEG-4, parte 10. Esto permite a los equipos con velocidades de reloj de CPU inferiores codificar y descodificar vídeo de mayor resolución. Los requisitos de hardware de vídeo varían en función de la configuración del equipo y de la resolución de vídeo que se desea.
  
Consulta también los [requisitos de hardware de Windows y Mac.](https://products.office.com/office-system-requirements)
  
### <a name="video-hardware-requirements"></a>Requisitos de hardware de vídeo

|**Característica**|**Requisito**|
|:-----|:-----|
|Descodificación H.264 acelerada por hardware mediante DirectX Video Acceleration (DXVA)  <br/> |• La tarjeta gráfica debe admitir DirectX 9.0 y debe exponer el modo de DXVA2_ModeH264_VLD_NoFGT y la API de DirectX 9.  <br/> • El controlador de tarjeta gráfica más reciente debe estar instalado.  <br/> |
|Codificación H.264 acelerada por hardware: requisitos del conjunto de chips  <br/> |Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware intel:  <br/> • Conjuntos de chips Intel HD Graphics 2000, 2500, 3000 y 4000 de segunda y tercera generación (o versiones posteriores) con codificadores de vídeo de hardware integrados. Se requiere la instalación del controlador Intel HD Graphics 15.28.9.2884 o el controlador más reciente que contenga lo siguiente:  <br/> • Controlador de pantalla 9.17.10.2884 o el controlador más reciente  <br/> • Hardware Media Foundation Transform (HMFT) versión 3.12.10.31 o la última HMFT  <br/> Se admiten las siguientes soluciones de codificación de vídeo acelerada por hardware AMD:  <br/> • Motor de códecs de vídeo AMD, que está disponible en varias tarjetas gráficas discretas y en unidades de procesamiento acelerado integradas de procesadores acelerados amd A-Series. El controlador del motor de códecs de vídeo AMD 9.12.0.0 o superior debe estar instalado.  <br/> |
|Codificación H.264 acelerada por hardware: requisitos de la cámara  <br/> |Cámaras de vídeo USB con codificador de hardware H.264 integrado que cumplan la especificación USB Video Class (UVC) versión 1.5.  <br/> **Nota:** Skype Empresarial admite cámaras UVC 1.5 con Windows 8 o Windows 8.1, que incluye compatibilidad con UVC 1.5. Como Windows 7 no incluye compatibilidad con UVC 1.5, Skype Empresarial trata las cámaras UVC 1.5 como cámaras normales sin compatibilidad con codificación de hardware. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinación de las capacidades de codificación y decodificación de vídeo H.264

Por lo general, son cuatro los factores principales que determinan la capacidad máxima de codificación y descodificación de una configuración de equipo determinada:
  
- Compatibilidad para descodificación acelerada por hardware mediante DXVA
    
- Compatibilidad para codificación acelerada por hardware
    
- Número de núcleos físicos
    
- Evaluación de la experiencia de Windows (WEI)
    
La Herramienta de evaluación del sistema de Windows (WinSAT) determina la WEI. Cuando se ejecuta la herramienta WinSAT, genera un documento XML Formal.Assessment en el equipo, en el directorio %windir%\Performance\WinSAT\DataStore. Este archivo XML contiene las siguientes dos puntuaciones que son especialmente importantes para determinar la capacidad de codificación y descodificación:
  
- VideoEncodeScore indica la capacidad de codificación de vídeo basada en software del equipo.
    
- El valor de GraphicsScore indica la capacidad de codificación acelerada por hardware del equipo.
    
Las siguientes tres tablas explican la capacidad máxima de codificación y descodificación de diferentes tipos de PC en función de la aceleración de hardware que admitan. Para resoluciones de 640x360 y superiores, la velocidad de fotogramas máxima admitida es de 30 fotogramas por segundo (fps). Para resoluciones inferiores a 640x360, la velocidad de fotogramas máxima admitida es de 15 fps.
  
**Equipo sin DXVA y sin codificador acelerado por hardware**

|**Resolución del codificador habilitado**|**Resolución del descodificador habilitado**|**Requisito**|
|:-----|:-----|:-----|
|424 x 240  <br/> |424x240 (640x360 a 15 fps para escenarios solo de recepción)  <br/> |1 núcleo y VideoEncodeScore ≥ 4,0  <br/> |
|640 x 360  <br/> |640 x 360  <br/> |2 núcleos y VideoEncodeScore = 4,5  <br/> |
|640 x 360  <br/> |1280 x 720  <br/> |2 núcleos y VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1920x1080  <br/> |4 núcleos y VideoEncodeScore ≥ 4,5  <br/> |
|1280 x 720  <br/> |1280 x 720  <br/> |4 núcleos y VideoEncodeScore ≥ 7,3  <br/> |
|1280 x 720  <br/> |1920x1080  <br/> |4 núcleos y VideoEncodeScore ≥ 7,3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |N/D  <br/> |
   
**Equipo con DXVA pero sin codificador acelerado por hardware**

|**Resolución del codificador habilitado**|**Resolución del descodificador habilitado**|**Requisito**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920x1080  <br/> |1 núcleo y VideoEncodeScore ≥ 3,0  <br/> |
|640 x 360  <br/> |1920x1080  <br/> |2 núcleos y VideoEncodeScore ≥ 4,5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 núcleos y VideoEncodeScore ≥ 6,0  <br/> |
|1280 x 720  <br/> |1920x1080  <br/> |4 núcleos y VideoEncodeScore ≥ 6,7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 núcleos y VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> La puntuación de WinSAT en Windows 7 se limita a un máximo de 7,9. Por lo tanto, la capacidad de codificación para un equipo sin un codificador acelerado por hardware solo se puede lograr en Windows 8 o Windows 8.1, donde la puntuación máxima de WinSAT es 9,9. 
  
**Equipo con DXVA y con codificador acelerado por hardware Intel HD Graphics**

|**Resolución del codificador habilitado**|**Resolución del descodificador habilitado**|**Requisito**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920x1080  <br/> |Todos los modelos de Intel HD Graphics de segunda y tercera generación  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |Todos los modelos de Intel HD Graphics de segunda y tercera generación y GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Funcionalidades de vídeo de dispositivo móvil

En la tabla siguiente se describen las resoluciones de vídeo máximas disponibles en los dispositivos móviles compatibles. Para obtener más información acerca de la compatibilidad con dispositivos móviles, comparación de características [de cliente móvil para Skype Empresarial.](mobile-feature-comparison.md)
  
|**Característica**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Resolución máxima de codificación H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S y versiones posteriores  <br/> |VGA: iPad 2 y versiones posteriores/iPad mini 1 y posteriores  <br/> 720p: iPad Air/iPad mini 2/iPad Pro y versiones posteriores  <br/> |Hasta VGA según el modelo de dispositivo  <br/> |
|Resolución máxima de decodificación H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S y versiones posteriores  <br/> |VGA: iPad 2 y versiones posteriores/iPad mini 1 y posteriores  <br/> 720p: iPad Air/iPad mini 2/iPad Pro y versiones posteriores  <br/> |Hasta VGA según el modelo de dispositivo  <br/> |
   

