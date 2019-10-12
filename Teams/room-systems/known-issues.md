---
title: Problemas conocidos
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection: M365-voice
description: En este artículo se comentan los problemas conocidos de Sala de Microsoft Teams por área de características.
ms.openlocfilehash: eaf95f8afd470376ee4f14549b50df8b38d93d34
ms.sourcegitcommit: e84becc101232b8017aab519378480c5dbebbb48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2019
ms.locfileid: "37468492"
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

Si desea que la pantalla frontal de la sala de espera cambie automáticamente a una fuente de video activa (como una consola de MTR) cuando el origen se reactiva al modo de espera, deben cumplirse ciertas condiciones. Esta característica es opcional pero es compatible con el software de las salas de Microsoft Teams, siempre que el hardware subyacente admita esta característica. Un televisor de consumo que se usa como parte frontal de la presentación de la sala debe admitir la característica control de electrónica de consumo (CEC) de HDMI.  Según el Dock o la consola seleccionados (que podrían no admitir CEC, consulte la documentación de soporte del fabricante), es posible que se necesite un controlador de área de trabajo como [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) para habilitar el comportamiento deseado. 

***

Use siempre una conexión de red cableada de 1 Gbps para asegurarse de que tiene el ancho de banda necesario. 

***

Si el dispositivo de las salas de Microsoft Teams pierde la confianza con el dominio, no podrá autenticarse en el dispositivo y abrir la configuración. Por ejemplo, si quita las salas de Microsoft Teams del dominio después de que se haya unido a un dominio, se perderá la confianza. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
***
La versión de 64 bits de la edición de Windows 10 Enterprise Anniversary (en inglés, versión 1607) ya no se admite desde la versión 3.0.12.0 de Salas de Microsoft Teams. 
***
Salas de Microsoft Teams es una aplicación de varias ventanas y requiere que se conecte al puerto HDMI del dispositivo una parte delantera de la sala para que la aplicación funcione correctamente. Asegúrese de que tiene una pantalla HDMI conectada o use una conexión de HDMI ficticia si está probando y no ha comprado aún una pantalla.
***
Windows 10 1903 aún no se ofrece en dispositivos de salas de Microsoft Teams desde Crestron debido a problemas con un controlador de gráficos.

***
<a name="See"> </a>  
## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)
