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
description: Configuración de administración para Microsoft Teams para concentrador de superficie.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 086edb4f7c949154dae49cb6a371a1d9d11bc43a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204464"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Implementar Microsoft Teams para Surface Hub
======================================

Antes de instalar los equipos de superficie de concentradores, asegúrese de hacer lo siguiente:

 Se cumple □ hacer seguro de requisitos de hardware, sistema operativo y otro. Para obtener más información, consulte la [Guía de administración de Microsoft Surface concentrador](https://docs.microsoft.com/surface-hub/).<br>
 □ Asegúrese de que está instalada la actualización de sistema operativo mínimo necesaria para los equipos - [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ Asigna una licencia de los equipos a la cuenta del dispositivo concentrador.<br>
 □ Si están realizando la transición de Skype para en línea de negocio, confirme que se asigna una licencia de los equipos al usuario.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Instalación de los equipos para exponer concentrador desde el almacén de Microsoft 

Estas instrucciones son para la instalación de los equipos de concentrador de superficie de Microsoft Store. 
 
1. Iniciar el almacén de Microsoft:<br>
   a. Puntee en **Iniciar** > **todas las aplicaciones** > **configuración**.<br> b. Puntee en **dispositivo de concentrador de superficie de cuenta, administración**.<br>
   c. En la izquierda, puntee en la ficha **aplicaciones & características** .<br> d. En la derecha, puntee en el botón **Abrir almacén** . 
2. De Microsoft Store, busque *Los equipos de Microsoft*. Se mostrarán los **Equipos de Microsoft para el concentrador de superficie** . Puntee en el botón **obtener la aplicación** para instalar.  
3. Una vez finalizada la instalación, reinicie el concentrador de superficie. 

> [!NOTE]
> No puntee en **Iniciar** desde la página de lista de la tienda.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Hacer que los equipos de la aplicación de las reuniones y llamadas de forma predeterminada
 
Hay dos opciones para configurar la directiva de aplicación de llamadas y las reuniones de forma predeterminada: 

- **Opción 1**: configurar a través de la clave USB. 
- **Opción 2**: configurar a través de MDM como Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opción 1: Configurar a través de la clave USB 
 
Los paquetes se pueden encontrar en esta [página de descarga](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Elija la adecuada para el paquete que va a instalar y cópielo a una clave USB. El archivo .ppkg correcto para usar depende de la directiva de aplicación predeterminado que desea aplicar la siguiente manera: 

|Número  |Descripción  |
|---------|---------|
|0     | Aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles        |
|1     | Aplicación preferida de los equipos en la pantalla de inicio, las reuniones de Skype disponibles        |
|2     | Aplicación exclusiva de los equipos en la pantalla de inicio (aplicación de Skype no está disponible)        |
 
1. Adjunta la clave USB en el dispositivo del concentrador de superficie. 
2. Abra la aplicación de **configuración** en un dispositivo concentrador de superficie. 
3. Abra **administración de cuentas de dispositivo concentrador expuesta**.
4. Abra **administración de dispositivos**. 
5. Haga clic en **Agregar o quitar un paquete de aprovisionamiento**. 
6. Haga clic en **Agregar paquete**.
7. Seleccione la opción de **Medios extraíble** en el menú desplegable. 
8. Agregar el paquete apropiado de <strong>TeamsRTMMode*.ppkg</strong> que anteriormente se ha copiado a la clave USB. 
9. Reinicie el dispositivo concentrador de superficie. 
10. Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opción 2: Configurar a través de MDM como Intune 

Use lo siguiente para configurar la directiva de aplicación predeterminada llamadas y reuniones a través de Intune. Vea también el blog, [implementar los equipos de Microsoft para aplicación de concentrador de superficie con Intune](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/).

|Configuración   |Valor    |Descripción    |
|----------|---------|---------|
| Ruta de acceso      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo de datos | entero (0-2)   |0 - aplicación preferida de Skype en la pantalla de inicio, las reuniones de los equipos disponibles<br>1 - equipos aplicación preferida en la pantalla de inicio, las reuniones de Skype disponibles<br>2 - equipos aplicación exclusivo en la pantalla de inicio (aplicación de Skype no está disponible) |
|Operations| Obtener, establecer        |

|Configuración   |Valor    |
|----------|---------|
| Ruta de acceso      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo de datos | ¡cadena - cadena de conjunto a los equipos el identificador del paquete de aplicación como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Los equipos** |
|Operations| Obtener, establecer        |

Reinicie el dispositivo concentrador de superficie. Una vez reiniciado el dispositivo, debe ser capaz de iniciar la aplicación de los equipos desde la pantalla de inicio y unirse a una reunión desde el calendario.

