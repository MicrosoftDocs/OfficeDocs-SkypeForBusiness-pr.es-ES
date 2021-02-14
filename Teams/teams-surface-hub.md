---
title: Implementar Microsoft Teams para Surface Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Obtenga información sobre cómo instalar y configurar la aplicación Teams para Surface Hub para que Teams sea la aplicación predeterminada para llamadas y reuniones.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 589bbfe75f0beea88066b5a6188b1d29c98ddd5f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905652"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Implementar Microsoft Teams para Surface Hub
======================================

Antes de instalar Teams para Surface Hub, asegúrese de hacer lo siguiente:

 □ asegúrese de que se cumplen los requisitos de hardware, sistema operativo y otros requisitos. Para obtener más información, consulta la [guía del administrador de Microsoft Surface Hub.](https://docs.microsoft.com/surface-hub/)<br>
 □ Asegúrese de que está instalada la actualización mínima del sistema operativo necesaria para Teams: [KB4343889.](https://support.microsoft.com/help/4343889)<br>
 □ asignar una licencia de Teams a la cuenta del dispositivo Hub.<br>
 □ Si va a realizar la transición desde Skype Empresarial Online, confirme que se ha asignado una licencia de Teams al usuario.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Instalar Teams para Surface Hub desde Microsoft Store 

Estas instrucciones son para instalar Teams para Surface Hub desde Microsoft Store. 
 
1. Inicia Microsoft Store:<br>
   a. Pulse Iniciar **la configuración** de  >  **todas las**  >  **aplicaciones.**<br> b. Pulse cuenta **de dispositivo Surface Hub, administración.**<br>
   c. A la izquierda, pulse la pestaña **& Características.**<br> d. A la derecha, pulse el **botón Abrir** tienda. 
2. En Microsoft Store, busque *Microsoft Teams.* Se mostrará Microsoft Teams para **Surface Hub.** Pulse el **botón Obtener la aplicación** para instalar.  
3. Cuando se complete la instalación, reinicia Surface Hub. 

> [!NOTE]
> No pulse Inicio **desde la** página de descripción de Store.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Hacer que Teams sea la aplicación predeterminada para llamadas y reuniones
 
Hay dos opciones para configurar la directiva de aplicación de llamadas y reuniones predeterminada: 

- **Opción 1:** Configurar mediante tecla USB. 
- **Opción 2:** Configurar a través de MDM como Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opción 1: Configurar mediante tecla USB 
 
Los paquetes se pueden encontrar en esta página [de descarga.](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g) Elige el adecuado para el paquete que estás planeando instalar y cópielo en una tecla USB. El archivo .ppkg correcto que se use depende de la directiva de aplicación predeterminada que le gustaría aplicar de la siguiente manera: 

|Número  |Descripción  |
|---------|---------|
|0     | Aplicación preferida de Skype en la pantalla Inicio, reuniones de Teams disponibles        |
|1     | Aplicación preferida de Teams en la pantalla Inicio, reuniones de Skype disponibles        |
|2     | Aplicación exclusiva de Teams en la pantalla Inicio (la aplicación Skype no está disponible)        |
 
1. Conecte la tecla USB al dispositivo Surface Hub. 
2. Abre la **aplicación Configuración** en un dispositivo Surface Hub. 
3. Abra la **administración de cuentas de dispositivos de Surface Hub.**
4. Abra **Administración de dispositivos.** 
5. Haga clic **en Agregar o quitar un paquete de aprovisionamiento.** 
6. Haga **clic en Agregar paquete.**
7. Selecciona la **opción Multimedia extraíble** en el menú desplegable. 
8. Agregue el paquete <strong>TeamsRTMMode*.ppkg</strong> adecuado copiado previamente a la clave USB. 
9. Reinicia el dispositivo Surface Hub. 
10. Una vez que se reinicie el dispositivo, debería poder iniciar la aplicación Teams desde la pantalla Inicio y unirse a una reunión desde el calendario. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opción 2: Configurar a través de MDM como Intune 

Use lo siguiente para configurar la directiva de aplicación de llamadas y reuniones predeterminada a través de Intune. Consulte también el blog, [Implementar la aplicación Microsoft Teams para Surface Hub con Intune.](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|Setting   |Valor    |Descripción    |
|----------|---------|---------|
| Ruta de acceso      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo de datos | entero (0-2)   |0: aplicación preferida de Skype en la pantalla Inicio, reuniones de Teams disponibles<br>1: Aplicación preferida de Teams en la pantalla Inicio, reuniones de Skype disponibles<br>2- Aplicación exclusiva de Teams en la pantalla Inicio (la aplicación Skype no está disponible) |
|Operations| Obtener, establecer        |

|Setting   |Valor    |
|----------|---------|
| Ruta de acceso      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo de datos | cadena: establezca la cadena en el id. del paquete de aplicación de Teams **como Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams** |
|Operations| Obtener, establecer        |

Reinicia el dispositivo Surface Hub. Una vez que se reinicie el dispositivo, debería poder iniciar la aplicación Teams desde la pantalla Inicio y unirse a una reunión desde el calendario.

