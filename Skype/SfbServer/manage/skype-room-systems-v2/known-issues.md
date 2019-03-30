---
title: Problemas conocidos
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: En este artículo se describe los problemas conocidos para salas de equipos de Microsoft, por área de característica.
ms.openlocfilehash: d71b209784f4737ac4433e2eececb1f9ada3ebc8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013090"
---
# <a name="known-issues"></a>Problemas conocidos 
 
En este artículo se enumera los problemas conocidos para salas de equipos de Microsoft, por área de característica.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Actualización 

| Título del problema |  Comportamiento de \/ síntoma | Solución conocida | Artículo KB |
|  ---        |      ---             |   ---            | --- |
|  Aplicación caducada         |    La consola de salas de equipos de Microsoft muestra un error "sistema config caducada".                |   [Utilizar la herramienta de recuperación de salas de equipos de Microsoft](recovery-tool.md)             |  Ninguno |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interfaz de usuario 

| Título del problema |  Comportamiento de \/ síntoma | Solución conocida | Artículo KB |
|  ---        |      ---             |   ---            | --- |
|Falta el teclado virtual   | El teclado virtual no aparece cuando se necesita escribir información en salas de equipos de Microsoft. Este problema se produce después de instalar la actualización de los creadores de 10 (versión 1703) de Windows en el 4 Surface Pro donde se ejecuta Microsoft los equipos locales. | Para solucionar este problema, abra manualmente el teclado virtual. Para ello, siga estos pasos:<br><br> Puntee en **1.** y mantenga la barra de tareas y, a continuación, puntee el botón **Mostrar pantalla táctil** . Debería aparecer un icono de teclado en el lado derecho de la barra de tareas. <br><br> **2.** puntee el icono de teclado para abrir el teclado virtual. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Título del problema |  Comportamiento de \/ síntoma | Solución conocida | Artículo KB |
|  ---        |      ---             |   ---            |   --- |
| Monitores no detectados | Cuando ejecuta salones de los equipos de Microsoft en un dispositivo Surface Pro (modelo de 2017), no se detectan los monitores. |  Mantenga presionado el botón de alimentación Surface Pro de 20 o más segundos. En este caso, el dispositivo se reinicia y borra la memoria caché de gráficos. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitaciones y comportamientos esperados
***
Salones de los equipos de Microsoft no admite entrada HDCP, que se ha observado para provocar problemas con HDMI ingesta funcionalidad (vídeo, audio). Tenga cuidado para asegurarse de que los conmutadores conectados a las salas de los equipos de Microsoft tienen opciones HDCP desactivadas. 
***
Una televisión de consumo usada como una parte delantera del salón de mostrar las necesidades de soporte técnico o habilitar la característica de Control de electrónica de consumidor (CEC) de HDMI para que puede cambiar automáticamente a un origen de vídeo activo de modo de espera. Esta característica no se admite en todos los televisores. 
***
Use siempre una conexión de red de 1 Gbps por cable para asegurarse de que tiene el ancho de banda necesaria. 
***
Si su dispositivo de salas de equipos de Microsoft pierde la relación de confianza con el dominio (por ejemplo, si quita las salas de los equipos de Microsoft desde el dominio después de está unido al dominio), no podrá autenticar en el dispositivo y abrir seguridad de la configuración. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
***
La versión de 64 bits de Windows 10 Enterprise aniversario edition (en inglés, versión 1607) ya no se admite a partir de salas de equipos de Microsoft de la versión 3.0.12.0. 
***

<a name="See"> </a>  
## <a name="see-also"></a>Consulte también

[Ayuda de salas de equipos de Microsoft](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar las salas de equipos de Microsoft](skype-room-systems-v2.md)