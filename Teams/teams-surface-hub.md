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
description: Obtenga información sobre cómo instalar y configurar la aplicación Teams para Surface Hub para que Teams es la aplicación de llamadas y reuniones predeterminada.
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
ms.openlocfilehash: d65f94b3f1e71a59ac2debc04828c5fa25f000f7
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587009"
---
# <a name="deploy-microsoft-teams-for-surface-hub"></a>Implementar Microsoft Teams para Surface Hub

Antes de instalar Teams para Surface Hub, asegúrese de hacer lo siguiente:

 □ Asegúrese de que se cumplen los requisitos de hardware, sistema operativo y otros requisitos. Para obtener más información, vea la [guía Microsoft Surface Hub administrador](/surface-hub/).<br>
 □ Asegúrese de que la actualización mínima del sistema operativo necesaria para Teams está instalada: [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ asignar una Teams a la cuenta del dispositivo Hub.<br>
 □ Si va a realizar la transición desde Skype Empresarial Online, confirme que una licencia de Teams está asignada al usuario.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Instalar Teams para Surface Hub desde el Microsoft Store 

Estas instrucciones son para instalar Teams para Surface Hub desde el Microsoft Store. 
 
1. Inicie el Microsoft Store:<br>
   a. Pulse **Iniciar**  >  **todas las aplicaciones**  >  **Configuración**.<br> b. Pulse **Surface Hub Cuenta del dispositivo, administración**.<br>
   c. A la izquierda, pulse la **pestaña Aplicaciones & características.**<br> d. A la derecha, pulse el **botón Abrir** tienda. 
2. En el Microsoft Store, busque *Microsoft Teams*. Se **Microsoft Teams la Surface Hub** se mostrará. Pulse el **botón Obtener la aplicación** para instalarlo.  
3. Cuando se complete la instalación, reinicie el Surface Hub. 

> [!NOTE]
> No pulse Iniciar **desde** la página de descripción de Store.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Crear Teams la aplicación de llamadas y reuniones predeterminada
 
Hay dos opciones para configurar la directiva de aplicación de llamadas y reuniones predeterminada: 

- **Opción 1:** Configurar mediante la tecla USB. 
- **Opción 2:** Configurar mediante MDM como Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opción 1: Configurar mediante la tecla USB 
 
Los paquetes se pueden encontrar en esta [página de descarga.](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g) Elija la adecuada para el paquete que está planeando instalar y cópielo en una clave USB. El archivo .ppkg correcto que se va a usar depende de la directiva de aplicación predeterminada que quiera aplicar de la siguiente manera: 

|Número  |Descripción  |
|---------|---------|
|0     | Skype aplicación preferida en la pantalla Inicio, Teams reuniones disponibles        |
|1     | Teams aplicación preferida en la pantalla Inicio, Skype reuniones disponibles        |
|2     | Teams aplicación exclusiva en la pantalla Inicio (Skype aplicación no disponible)        |
 
1. Adjunte la tecla USB al Surface Hub dispositivo. 
2. Abra la **Configuración** en un Surface Hub dispositivo. 
3. Abra **Surface Hub administración de cuentas de dispositivos**.
4. Abra **Administración de dispositivos**. 
5. Haga **clic en Agregar o quitar un paquete de aprovisionamiento.** 
6. Haga clic **en Agregar paquete.**
7. Seleccione la **opción Multimedia extraíble** en el menú desplegable. 
8. Agregue el paquete <strong>TeamsRTMMode*.ppkg</strong> adecuado que se copió previamente en la clave USB. 
9. Reinicie el Surface Hub dispositivo. 
10. Después de reiniciar el dispositivo, debería poder iniciar la aplicación Teams desde la pantalla Inicio y unirse a una reunión desde el calendario. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opción 2: Configurar a través de MDM como Intune 

Use lo siguiente para configurar la directiva de aplicación de llamadas y reuniones predeterminada a través de Intune. Vea también el blog Implementar [la aplicación Microsoft Teams para Surface Hub con Intune.](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|Setting   |Valor    |Descripción    |
|----------|---------|---------|
| Ruta de acceso      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo de datos | entero (0-2)   |0: Skype aplicación preferida en la pantalla Inicio, Teams reuniones disponibles<br>1: Teams aplicación preferida en la pantalla Inicio, Skype reuniones disponibles<br>2: Teams aplicación exclusiva en la pantalla Inicio (Skype aplicación no disponible) |
|Operaciones| Obtener, Establecer        |

|Setting   |Valor    |
|----------|---------|
| Ruta de acceso      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo de datos | cadena: establezca cadena en Teams de paquete de aplicación como **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams** |
|Operaciones| Obtener, Establecer        |

Reinicie el Surface Hub dispositivo. Después de reiniciar el dispositivo, debería poder iniciar la aplicación Teams desde la pantalla Inicio y unirse a una reunión desde el calendario.