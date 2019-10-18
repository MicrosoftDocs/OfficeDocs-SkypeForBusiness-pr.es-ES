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
description: Configure las opciones de administración de Microsoft Teams para Surface Hub.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37c38577fe3bda9ed2a1c2e224390e89f44de96b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570107"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Implementar Microsoft Teams para Surface Hub
======================================

Antes de instalar Team Hub, asegúrese de hacer lo siguiente:

 □ Asegurarse de que se cumplan el hardware, el sistema operativo y otros requisitos. Para obtener más información, consulte la [Guía del administrador de Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).<br>
 □ Asegurarse de que la actualización de sistema operativo necesaria para Teams esté instalada: [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ Asignar una licencia de Teams a la cuenta del dispositivo concentrador.<br>
 □ Si va a realizar una transición desde Skype empresarial online, confirme que se asigna una licencia de Teams al usuario.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Instalar Teams para Surface Hub desde Microsoft Store 

Estas instrucciones son para instalar Teams en Surface Hub desde Microsoft Store. 
 
1. Inicie Microsoft Store:<br>
   a. Puntee en **iniciar** > la**configuración**de**todas las aplicaciones** > .<br> b. Toca la **cuenta de dispositivo de Surface Hub y la administración**.<br>
   c. En la parte izquierda, pulse la pestaña **aplicaciones & características** .<br> d. En la parte derecha, pulse el botón **Abrir Tienda** . 
2. En Microsoft Store, busque *Microsoft Teams*. Se mostrará **Microsoft Teams para Surface Hub** . Toca el botón **obtener la aplicación** para instalar.  
3. Cuando haya finalizado la instalación, reinicie Surface Hub. 

> [!NOTE]
> No toca **iniciar** desde la página de descripción de la tienda.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Hacer que Teams sea la aplicación de llamadas y reuniones predeterminada
 
Hay dos opciones para configurar la Directiva de aplicación de llamadas y reuniones predeterminada: 

- **Opción 1**: configurar mediante la tecla USB. 
- **Opción 2**: configurar a través de MDM, como Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opción 1: configurar la tecla USB 
 
Los paquetes se pueden encontrar en esta [Página de descarga](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Elija el que corresponda al paquete que está planificando instalar y cópielo en una llave USB. El archivo. ppkg correcto depende de la Directiva de aplicación predeterminada que le gustaría aplicar de la siguiente manera: 

|Número  |Descripción  |
|---------|---------|
|,0     | Aplicación de Skype preferida en la pantalla Inicio, reuniones de Teams disponibles        |
|1     | Aplicación de Teams preferida en la pantalla Inicio, reuniones de Skype disponibles        |
|1     | Aplicación equipos exclusivos en la pantalla Inicio (aplicación de Skype no disponible)        |
 
1. Adjunte la llave USB al dispositivo Surface Hub. 
2. Abra la aplicación **configuración** en un dispositivo Surface Hub. 
3. Abra **Administración de cuentas de dispositivos de Surface Hub**.
4. Abra **Administración de dispositivos**. 
5. Haga clic en **Agregar o quitar un paquete de aprovisionamiento**. 
6. Haga clic en **Agregar paquete**.
7. Seleccione la opción **medios extraíbles** en el menú desplegable. 
8. Agregue el paquete de <strong>TeamsRTMMode *. ppkg</strong> adecuado que se ha copiado previamente a la tecla USB. 
9. Reinicie el dispositivo Surface Hub. 
10. Después de reiniciar el dispositivo, debe poder iniciar la aplicación de Teams desde la pantalla de inicio y unirse a una reunión desde el calendario. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opción 2: configurar a través de MDM, como Intune 

Use el siguiente procedimiento para configurar la Directiva de aplicación de llamadas y reuniones predeterminada a través de Intune. También puede ver el blog, [implementar Microsoft Teams para la aplicación Surface Hub con Intune](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/).

|Configuración   |Valor    |Descripción    |
|----------|---------|---------|
| Ruta de acceso      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo de datos | entero (0-2)   |0-aplicación preferida de Skype en la pantalla Inicio, reuniones de Teams disponibles<br>1-aplicación preferida de equipos en la pantalla Inicio, reuniones de Skype disponibles<br>2-aplicación exclusiva de Teams en la pantalla Inicio (aplicación de Skype no disponible) |
|Operations| Obtener, establecer        |

|Configuración   |Valor    |
|----------|---------|
| Ruta de acceso      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo de datos | cadena: establecer cadena en el identificador del paquete de la aplicación de Teams como **Microsoft. MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams** |
|Operations| Obtener, establecer        |

Reinicie el dispositivo Surface Hub. Después de reiniciar el dispositivo, debe poder iniciar la aplicación de Teams desde la pantalla de inicio y unirse a una reunión desde el calendario.

