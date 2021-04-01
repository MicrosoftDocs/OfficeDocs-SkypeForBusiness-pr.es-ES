---
title: Informe de uso de dispositivos de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de dispositivos de Teams en el Centro de administración de Microsoft Teams para ver cómo los usuarios de su organización se conectan a Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d47888884ce86bfa56546a9df600ce958380e0d
ms.sourcegitcommit: 66e7b28ba1c0433535eb6a3e7d883851c27d9d1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "51478360"
---
# <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de dispositivos de Teams en el Centro de administración de Microsoft Teams le proporciona información sobre cómo se conectan los usuarios a Teams. Puede usar el informe para ver los dispositivos que se usan en toda la organización, incluidos cuántos usan Teams desde sus dispositivos móviles cuando se está desen marcha.  

## <a name="view-the-device-usage-report"></a>Ver el informe de uso del dispositivo

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic **en Análisis & informes de**  >  **uso.** En la pestaña **Ver informes,** **en** Informe, seleccione Uso del dispositivo de **Teams.**
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

    ![Captura de pantalla del informe de uso de dispositivos de Teams en el Centro de administración de Teams con llamadas](../media/teams-reports-device-usage-with-callouts.png "Captura de pantalla del informe de uso de dispositivos de Teams en el Centro de administración de Teams con llamadas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |El informe de uso de dispositivos de Teams se puede ver para ver las tendencias de los últimos 7 días o 30 días.  |
|**2**   |Cada informe tiene una fecha para cuando se generó el informe. Los informes normalmente reflejan una latencia de 24 horas desde el momento de la actividad. |
|**3**   |<ul><li>El eje X del gráfico representa los distintos dispositivos **(Windows,** **Mac,** **Linux,** **iOS,** **Android Phone,** **Web)** usados para conectarse a Teams. </li><li>El eje Y es el número de usuarios que usan el dispositivo durante el período de tiempo seleccionado.</li> </ul>Mantenga el puntero sobre la barra que representa un dispositivo para ver el número de usuarios que usan el dispositivo para conectarse a Teams.|
|**4**   |La tabla le proporciona un desglose del uso del dispositivo por usuario. <ul><li>**Nombre** de usuario es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams. </li><li>**Windows** se selecciona si el usuario estaba activo en el cliente de escritorio de Teams en un equipo basado en Windows.</li><li>**Mac** está seleccionado si el usuario estaba activo en el cliente de escritorio de Teams en un equipo macOS. </li> <li>**Linux** está seleccionado si el usuario estaba activo en el cliente de escritorio de Teams en un equipo Linux. </li> <li>**iOS** está seleccionado si el usuario estaba activo en el cliente móvil e Teams para iOS.</li><li>**El teléfono Android** está seleccionado si el usuario estaba activo en el cliente móvil de Teams para Android. <li><li>**Web** está seleccionado si el usuario estaba activo en el cliente web de Teams. <li>**La última actividad** es la última fecha (UTC) en la que el usuario participó en una actividad de Teams.</li> </ul> Tenga en cuenta que si una cuenta de usuario ya no existe en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Haga **clic en Exportar a Excel** y, a continuación, en la pestaña **Descargas,** haga clic en Descargar para descargar el informe cuando esté listo. <br><br>![Captura de pantalla de la pestaña Descargas que muestra los informes exportados](../media/teams-reports-export-to-csv.png)|


## <a name="make-the-user-specific-data-anonymous"></a>Convertir en anónimos los datos específicos del usuario

Para que los datos del informe de uso de dispositivos de Teams sean anónimos, debe ser administrador global. Esto ocultará información identificable, como el nombre para mostrar, el correo electrónico y el id. de AAD en el informe y su exportación.

1. En el Centro de administración de  Microsoft 365, vaya a Configuración de la organización Configuración y, en la pestaña \> Servicios, elija **Informes.** 
    
2. Seleccione **Informes** y, a continuación, **elija Mostrar identificadores anónimos.** Esta configuración se aplica tanto a los informes de uso del Centro de administración de Microsoft 365 como al Centro de administración de Teams.
  
3. Seleccione **Guardar cambios**.

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
