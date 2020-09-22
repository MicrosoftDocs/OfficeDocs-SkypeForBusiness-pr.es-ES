---
title: Problemas conocidos
ms.author: v-lanac
author: lanachin
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
description: Administrador puede obtener información sobre una lista de problemas conocidos para salas de Microsoft Teams, como la actualización, la interfaz de usuario, el hardware, así como las limitaciones y comportamientos esperados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 73eab767d7b30182efb204fb8cfb8ceb06137c0b
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177370"
---
# <a name="known-issues"></a>Problemas conocidos 
 
En este artículo se indican los problemas conocidos de Sala de Microsoft Teams por área de características.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Actualización 

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            | --- |
| Aplicación que no se inicia |  Después de actualizar a la versión 4.4.41.0 de la aplicación, el sistema arranca en pantalla negra o ve a la pantalla de inicio de sesión después de unos minutos. | Siga los pasos de [Microsoft Team Rooms la aplicación no se inicia después de actualizar a la versión 4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) para corregir este problema.  | Ninguna |
|  SfB reuniones el uso compartido de contenido no muestra pantalla completa         |    En las reuniones de Skype empresarial, las salas con la parte delantera de la sala que se muestra con la configuración alta de PPP pueden experimentar problemas en los que el contenido compartido en una reunión no muestra la pantalla completa en la parte delantera de la sala. Esto se debe a un problema subyacente en la API de protocolo de escritorio remoto (RDP) de Windows 10. | Use la `<WinRTRdpEnabled>` configuración XML para deshabilitar la API RDP de Windows 10 para resolver este problema. Para deshabilitarlo, debe especificar el valor como `false` . Para obtener más información, vea [administrar la configuración de la consola con un archivo de configuración XML](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file). | Ninguna |
|  Aplicación obsoleta         |    La consola de Microsoft Teams salas muestra un error "configuración del sistema obsoleta".                |   [Usar la herramienta de recuperación de Sala de Microsoft Teams](recovery-tool.md)             |  Ninguna |
|  Dispositivo actualizado a una versión no compatible de Windows 10   |    Dispositivo Windows 10 actualizado desde la versión 1803 a la versión 1809, que no es compatible. La versión compatible es 1903. |   Esto puede ocurrir si la configuración [de directiva de grupo o de MDM para DeferFeatureUpdatesPeriodinDays](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) , que le permite aplazar actualizaciones de características durante un número determinado de días, se establece en el máximo de 365 días. <br><br> Windows 10 versión 1809 no es compatible con salas de Microsoft Teams, mientras que la versión 1903 es compatible. Sin embargo, a partir del 27 de marzo de 2020, la versión 1809 es superior a 365 días. Si esta configuración no se modifica, Windows intenta instalar la versión 1809, lo que puede ocasionar problemas con las salas de Microsoft Teams.<br><br>Para evitar esta situación, **Quite** cualquier directiva de grupo o configuración de MDM para aplazar las actualizaciones. Esto permite a Windows actualizar a la última versión del sistema operativo compatible. <br><br>**Importante** Es necesario **quitar** la configuración de directiva de grupo o MDM (izquierda sin configurar) y **no establecida en 0**. Si la Directiva se establece en 0, Windows toma la última versión disponible, que es posible que no sea compatible. |  Ninguna |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interfaz de usuario 

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            | --- |
|Falta el teclado virtual   | El teclado virtual no aparece cuando necesita especificar información en Salas de Microsoft Teams. Este problema se produce en Windows 10, versión 1903. | Instale la actualización acumulativa 2020-04 para Windows 10, versión 1903 para sistemas basados en x64 a través de actualizaciones de Windows.  | Ninguna | 

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

Si desea que la pantalla frontal de la sala de espera cambie automáticamente a una fuente de video activa (como una consola de MTR) cuando el origen se reactiva al modo de espera, deben cumplirse ciertas condiciones. Esta característica es opcional pero es compatible con el software de las salas de Microsoft Teams, siempre que el hardware subyacente admita esta característica. Un televisor de consumo que se usa como parte frontal de la presentación de la sala debe admitir la característica control de electrónica de consumo (CEC) de HDMI.  Según el Dock o la consola seleccionados (que podrían no admitir CEC, consulte la documentación de asistencia del fabricante), es posible que se necesite un controlador como, por ejemplo, [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) de Extron para habilitar el comportamiento deseado. 

***

Use siempre una conexión de red cableada de 1 Gbps para asegurarse de que tiene el ancho de banda necesario. 

***

Si el dispositivo de las salas de Microsoft Teams pierde la confianza con el dominio, no podrá autenticarse en el dispositivo y abrir la configuración. Por ejemplo, si quita las salas de Microsoft Teams del dominio después de que se haya unido a un dominio, se perderá la confianza. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
***
Salas de Microsoft Teams es una aplicación de varias ventanas y requiere que se conecte al puerto HDMI del dispositivo una parte delantera de la sala para que la aplicación funcione correctamente. Asegúrese de que tiene una pantalla HDMI conectada o use una conexión de HDMI ficticia si está probando y no ha comprado aún una pantalla.
***
<a name="See"> </a>  
## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](rooms-manage.md)
