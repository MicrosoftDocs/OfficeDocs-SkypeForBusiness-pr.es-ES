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
description: El administrador puede obtener información sobre una lista de problemas conocidos de salas de Microsoft Teams, como la actualización, la interfaz de usuario, el hardware y las limitaciones y los comportamientos esperados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63a646fa6fb404cb46de889c318181146cb44b2a
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055742"
---
# <a name="known-issues"></a>Problemas conocidos 
 
En este artículo se indican los problemas conocidos de Sala de Microsoft Teams por área de características.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Actualización 

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            | --- |
| No se inicia la aplicación |  Después de actualizar a la versión 4.4.41.0 de la aplicación, el sistema se convertiría en pantalla negra o ir a la pantalla de inicio de sesión tras unos minutos. | Siga los pasos que se indican en la aplicación Salas de Microsoft Teams no se inicia después de actualizar a la versión [4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) para corregir este problema.  | Ninguna |
|  El uso compartido de contenido de reuniones sfB no muestra pantalla completa         |    En las reuniones de Skype Empresarial, las salas con pantallas frontales con configuración elevada de PPP pueden experimentar problemas por los que el contenido compartido en una reunión no muestra la pantalla completa en la parte frontal de la pantalla de la sala. Esto se debe a un problema subyacente en la API de Protocolo de Escritorio remoto (RDP) de Windows 10. | Use la configuración XML para deshabilitar la API RDP de `<WinRTRdpEnabled>` Windows 10 para resolver este problema. Para deshabilitarlo, debe especificar el valor como `false` . Para obtener más información, vea [Administrar la configuración de la consola con un archivo de configuración XML.](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file) | Ninguna |
|  Aplicación obsoleta         |    La consola de Microsoft Teams salas muestra un error "configuración del sistema obsoleta".                |   [Usar la herramienta de recuperación de Sala de Microsoft Teams](recovery-tool.md)             |  Ninguna |
|  Dispositivo actualizado a la versión no compatible de Windows 10   |    El dispositivo con Windows 10 se actualizó de la versión 1803 a la 1809, lo que no es compatible. La versión compatible es 1903. |   Esto puede ocurrir si la configuración de Directiva de grupo o MDM para la configuración [DeferFeatureUpdatesPeriodays,](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) que le permite aplazar las actualizaciones de características durante un número especificado de días, está establecida en el máximo de 365 días. <br><br> La versión 1809 de Windows 10 no es compatible con Microsoft Teams Rooms, mientras que la versión 1903 es compatible. Sin embargo, a partir del 27 de marzo de 2020, la versión 1809 tiene más de 365 días de antigüedad. Si no cambia esta configuración, Windows intentará instalar la versión 1809, lo que puede causar problemas con Microsoft Teams Rooms.<br><br>Para evitar esta situación, **quite cualquier** configuración de Directiva de grupo o MDM para aplazar actualizaciones. Esto permite que Windows actualice a la versión más reciente del sistema operativo compatible. <br><br>**IMPORTANTE** Es necesario quitar la configuración de directiva de grupo o MDM **(izquierda** no configurada) y no **establecerla en 0.** Si la directiva se establece en 0, Windows toma la versión disponible más reciente, que es posible que no sea compatible. |  Ninguna |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interfaz de usuario 

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            | --- |
|Falta el teclado virtual   | El teclado virtual no aparece cuando necesita especificar información en Salas de Microsoft Teams. Este problema se produce en la versión 1903 de Windows 10. | Instale la actualización acumulativa 2020-04 para Windows 10, versión 1903 para sistemas basados en x64 a través de las actualizaciones de Windows.  | Ninguna | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Título del problema |  Comportamiento \/ síntoma | Solución conocida | Artículo de KB |
|  ---        |      ---             |   ---            |   --- |
| No se detectan los monitores | Cuando ejecuta Sala de Microsoft Teams en un dispositivo Surface Pro (modelo 2017), no se detectan los monitores. |  Mantenga presionado el botón de encendido del Surface Pro durante 20 segundos o más. Al hacer esto, el dispositivo se reinicia y borra la caché de gráficos. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitaciones y comportamiento esperado

**_

Sala de Microsoft Teams no admite la incorporación de HDCP, ya que se ha visto que provoca problemas con la funcionalidad de transmisión por HDMI (vídeo, audio). Asegúrese de que los conmutadores conectados a Sala de Microsoft Teams tienen desactivadas las opciones de HDCP. 

_*_

Si desea que la pantalla frontal de la sala cambie automáticamente a una fuente de vídeo activa (como una consola MTR) cuando el origen se reactiva del modo de espera, deben cumplirse ciertas condiciones. Esta característica es opcional, pero es compatible con el software salas de Microsoft Teams, siempre que el hardware subyacente admita la característica. Un televisor de consumidor usado frente a la pantalla de la sala debe admitir la característica de control de electrónica de consumidor (CEC) de HDMI.  En función de la base o consola seleccionada (que podría no ser compatible con CEC, consulte la documentación de soporte técnico del fabricante), es posible que se necesite un controlador como [HD-NICE-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) de Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) desde Extron para habilitar el comportamiento deseado. 

_*_

Use siempre una conexión de red cableada de 1 Gbps para garantizar que tiene el ancho de banda necesario. 

_*_

Si el dispositivo de salas de Microsoft Teams pierde la confianza con el dominio, no podrá autenticarse en el dispositivo ni abrir la Configuración. Por ejemplo, si quita Microsoft Teams Rooms del dominio después de que se unió al dominio, se pierde la confianza. La solución alternativa es iniciar sesión con la cuenta de administrador local. 
_*_ Salas de Microsoft Teams es una aplicación de varias ventanas y requiere que la pantalla frontal de la sala esté conectada al puerto HDMI del dispositivo, para que la aplicación funcione correctamente. Asegúrate de que tienes una pantalla HDMI conectada o usa un conector HDMI ficticia si estás probando y todavía no tienes una pantalla comprada.
_** <a name="See"> </a>  
## <a name="see-also"></a>Vea también

[Ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Administrar Salas de Microsoft Teams](rooms-manage.md)
