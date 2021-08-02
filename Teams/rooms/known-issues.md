---
title: Problemas conocidos
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: El administrador puede obtener información sobre una lista de problemas conocidos para Salas de Microsoft Teams, incluida la actualización, la interfaz de usuario, el hardware y las limitaciones y los comportamientos esperados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3656e73226f29f6580a4ae3a1807ee8273731a8
ms.sourcegitcommit: ad215c120d7e550a7aebf2e1bb620c69039e5d8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2021
ms.locfileid: "53679785"
---
# <a name="known-issues"></a>Problemas conocidos 
 
En este artículo se indican los problemas conocidos de Sala de Microsoft Teams por área de características.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Actualización 

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            | --- |
| Aplicación que no se inicia |  Después de actualizar a la versión 4.4.41.0 de la aplicación, el sistema se inicia en pantalla negra o ve a la pantalla de inicio de sesión después de unos minutos. | Siga los pasos de Salas de Microsoft Teams aplicación no se inicia después de actualizar a la [versión 4.4.41.0 para](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) solucionar este problema.  | Ninguna |
|  Volumen de reunión bajo después del uso compartido de contenido         |   Salas de Microsoft Teams dispositivos en Windows 10 20H2 experimentan una disminución del volumen de los medios y de la reunión después de compartir contenido a través de HDMI en la sala. Esto se debe a un problema de audio en Windows 10 20H2. | La corrección para este problema está disponible en la [versión 4.9.12.0 de la aplicación.](/microsoftteams/rooms/rooms-release-note#49120-7282021) | Ninguna |
|  Aplicación obsoleta         |    La consola de Microsoft Teams salas muestra un error "configuración del sistema obsoleta".                |   [Usar la herramienta de recuperación de Sala de Microsoft Teams](recovery-tool.md)             |  Ninguna |
|  Dispositivo actualizado a una versión no compatible de Windows 10   |    Windows 10 dispositivo actualizado de la versión 1803 a la versión 1809, que no es compatible. La versión compatible es 1903. |   Esto puede ocurrir si la configuración de Directiva de grupo o MDM para [DeferFeatureUpdatesPeriodinDays,](/windows/deployment/update/waas-configure-wufb) que le permite aplazar las actualizaciones de características para un número especificado de días, está establecida en el máximo de 365 días. <br><br> Windows 10 versión 1809 no es compatible con Salas de Microsoft Teams, mientras que la versión 1903 es compatible. Sin embargo, a partir del 27 de marzo de 2020, la versión 1809 tiene más de 365 días de antigüedad. Si esta configuración no cambia, Windows intenta instalar la versión 1809, lo que puede causar problemas con Salas de Microsoft Teams.<br><br>Para evitar esta situación, **quite cualquier configuración** de directiva de grupo o MDM para aplazar las actualizaciones. Esto permite Windows actualizar a la versión del sistema operativo compatible más reciente. <br><br>**IMPORTANTE** La configuración de directiva de grupo o MDM debe **quitarse** (no configurarse a la izquierda) y **no establecerse en 0**. Si la directiva se establece en 0, Windows la última versión disponible que puede no ser compatible. |  Ninguna |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interfaz de usuario 

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            | --- |
|Falta el teclado virtual   | El teclado virtual no aparece cuando necesita especificar información en Salas de Microsoft Teams. Este problema se produce en Windows 10, versión 1903. | Instale la actualización acumulativa 2020-04 para Windows 10, versión 1903 para sistemas basados en x64 a través de Windows actualizaciones.  | Ninguna | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            |   --- |
| No se detectan los monitores | Cuando ejecuta Sala de Microsoft Teams en un dispositivo Surface Pro (modelo 2017), no se detectan los monitores. |  Mantenga presionado el botón de encendido del Surface Pro durante 20 segundos o más. Al hacer esto, el dispositivo se reinicia y borra la caché de gráficos. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitaciones y comportamiento esperado

***

Sala de Microsoft Teams no admite la incorporación de HDCP, ya que se ha visto que provoca problemas con la funcionalidad de transmisión por HDMI (vídeo, audio). Asegúrese de que los conmutadores conectados a Sala de Microsoft Teams tienen desactivadas las opciones de HDCP. 

***

Si desea que una pantalla frontal de la sala cambie automáticamente a una fuente de vídeo activa (como una consola MTR) cuando la fuente se reactiva del modo de espera, deben cumplirse determinadas condiciones. Esta característica es opcional, pero es compatible Salas de Microsoft Teams software, siempre que el hardware subyacente admita la característica. Un televisor para consumidores que se usa como pantalla frontal de la sala debe admitir la característica control de electrónica de consumo (CEC) de HDMI.  Dependiendo de la base o consola seleccionada (que podría no ser compatible con CEC, consulte documentación de soporte técnico del fabricante), es posible que sea necesario un controlador como [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron para habilitar el comportamiento deseado. 

***

Use siempre una conexión de red cableada de 1 Gbps para asegurarse de que tiene el ancho de banda necesario. 

***

Si el Salas de Microsoft Teams pierde la confianza con el dominio, no podrá autenticarse en el dispositivo y abrir Configuración. Por ejemplo, si quita el Salas de Microsoft Teams del dominio después de que se ha unido al dominio, se perderá la confianza. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
***
Salas de Microsoft Teams es una aplicación de varias ventanas y requiere que una pantalla frontal de la sala esté conectada al puerto HDMI del dispositivo, para que la aplicación funcione correctamente. Asegúrese de que tiene una pantalla HDMI conectada o de usar un conector HDMI ficticio si está probando y aún no tiene una pantalla comprada.
***
<a name="See"> </a>  
## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](rooms-manage.md)
