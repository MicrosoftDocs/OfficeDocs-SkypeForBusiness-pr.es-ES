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
description: En este artículo se comentan los problemas conocidos de Sala de Microsoft Teams por área de características.
ms.openlocfilehash: d71b209784f4737ac4433e2eececb1f9ada3ebc8
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33363012"
---
# <a name="known-issues"></a>Problemas conocidos 
 
En este artículo se indican los problemas conocidos de Sala de Microsoft Teams por área de características.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Actualización 

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            | --- |
|  Aplicación obsoleta         |    La consola de Microsoft Teams salas muestra un error "configuración del sistema obsoleta".                |   [Usar la herramienta de recuperación de Sala de Microsoft Teams](recovery-tool.md)             |  Ninguna |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interfaz de usuario 

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            | --- |
|Falta el teclado virtual   | El teclado virtual no aparece cuando necesita especificar información en Salas de Microsoft Teams. Este problema se produce después de instalar Windows 10 Creators Update (versión 1703) en un Surface Pro 4 en el que se ejecuta Sala de Microsoft Teams. | Para solucionar este problema, abra manualmente el teclado virtual. Para ello, siga estos pasos:<br><br> **1.** Mantenga presionada la barra de tareas y, después, pulse el botón **Mostrar teclado táctil**. Se mostrará un icono de teclado en el lado derecho de la barra de tareas. <br><br> **2.** Pulse el icono de teclado para abrir el teclado virtual. | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            |   --- |
| No se detectan los monitores | Cuando ejecuta Sala de Microsoft Teams en un dispositivo Surface Pro (modelo 2017), no se detectan los monitores. |  Mantenga presionado el botón de encendido del Surface Pro durante 20 segundos o más. Al hacer esto, el dispositivo se reinicia y borra la caché de gráficos. |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitaciones y comportamiento esperado
***
Sala de Microsoft Teams no admite la incorporación de HDCP, ya que se ha visto que provoca problemas con la funcionalidad de transmisión por HDMI (vídeo, audio). Asegúrese de que los conmutadores conectados a Sala de Microsoft Teams tienen desactivadas las opciones de HDCP. 
***
Si se usa un televisor como pantalla, debe ser compatible con la característica Control de electrónica de consumidor (CEC) de HDMI o habilitarla para que puede cambiar automáticamente a un origen de vídeo activo desde el modo de espera. Esta característica no es compatible con todos los televisores. 
***
Use siempre una conexión de red cableada de 1 Gbps para garantizar que dispondrá de la banda ancha necesaria. 
***
Si su dispositivo de Sala de Microsoft Teams pierde la confianza en el dominio (por ejemplo, si elimina Sala de Microsoft Teams del dominio tras haberse unido a él), no podrá autenticarse en el dispositivo ni abrir Configuración. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
***
La versión de 64 bits de la edición de Windows 10 Enterprise Anniversary (en inglés, versión 1607) ya no se admite desde la versión 3.0.12.0 de Salas de Microsoft Teams. 
***

<a name="See"> </a>  
## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)