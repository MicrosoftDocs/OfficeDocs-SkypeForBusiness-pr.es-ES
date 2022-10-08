---
title: Informe de uso de dispositivos de Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de dispositivos de Teams en el Centro de administración de Microsoft Teams para ver cómo se conectan los usuarios de su organización a Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 11a16026bf8d844b4d533316e8680b8aa409b5b2
ms.sourcegitcommit: b2692b3f6c60d8df5ba0677c68ff9c90a75a0d72
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68033808"
---
# <a name="microsoft-teams-device-usage-report"></a>Informe de uso de dispositivos de Microsoft Teams

El informe de uso de dispositivos de Teams del Centro de administración de Microsoft Teams le proporciona información sobre cómo se conectan los usuarios a Teams. Puede usar el informe para ver los dispositivos que se usan en toda la organización, incluido el número de equipos que usan Teams desde sus dispositivos móviles mientras se desplaza.  

## <a name="view-the-device-usage-report"></a>Ver el informe de uso del dispositivo


Para ver los informes en el Centro de administración de Teams, debe ser administrador global, lector global o administrador del servicio de Teams. Consulte [Usar los roles de administrador de Teams para administrar Teams](../using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.


1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Análisis & informes** > **de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione **Uso de dispositivos de Teams**.
2. En **Intervalo de fechas**, seleccione un rango y haga clic en **Ejecutar informe**.

    ![Captura de pantalla del informe de uso de dispositivos de Teams en el Centro de administración de Teams con globos.](../media/teams-reports-device-usage-with-callouts.png "Captura de pantalla del informe de uso de dispositivos de Teams en el Centro de administración de Teams con globos")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe Uso de dispositivos de Teams para ver las tendencias de los últimos 7, 30, 90 y 180 días.  |
|**2**   |Cada informe tiene una fecha en la que se generó el informe. Los informes suelen reflejar una latencia de 24 a 48 horas desde el momento de la actividad. |
|**3**   |<ul><li>El eje X del gráfico representa los diferentes dispositivos (**Windows**, **Mac**, **Linux**, **iOS**, **Android Phone**, **Web**) usados para conectarse a Teams. </li><li>El eje Y es el número de usuarios que usan el dispositivo durante el período de tiempo seleccionado.</li> </ul>Mueva el puntero sobre la barra que representa un dispositivo para ver el número de usuarios que usan el dispositivo para conectarse a Teams.|
|**4**   |La tabla ofrece un desglose del uso del dispositivo por usuario. <ul><li>**Nombre de usuario** es el nombre para mostrar del usuario. Puede hacer clic en el nombre para mostrar para ir a la página de configuración del usuario en el Centro de administración de Microsoft Teams. </li><li>**Windows** se selecciona si el usuario estaba activo en el cliente de escritorio de Teams en un equipo basado en Windows.</li><li>**Mac** está seleccionado si el usuario estaba activo en el cliente de escritorio de Teams en un equipo macOS. </li> <li>**Linux** está seleccionado si el usuario estaba activo en el cliente de escritorio de Teams en un equipo Linux. </li> <li>**iOS** está seleccionado si el usuario estaba activo en el cliente móvil e Teams para iOS.</li><li>**Teléfono Android** está seleccionado si el usuario estaba activo en el cliente móvil de Teams para Android.</li><li>**Chrome OS** se selecciona si el usuario estaba activo en el cliente de escritorio de Teams en un equipo ChromeOS.</li><li>**Web** está seleccionado si el usuario estaba activo en el cliente web de Teams. <li>**Última actividad** es la última fecha (UTC) en la que el usuario ha participado en una actividad de Teams.</li> </ul> Tenga en cuenta que si una cuenta de usuario ya no existe en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla. |
|**6**   |Exporte el informe a un archivo CSV para analizarlo sin conexión. Seleccione el icono **Exportar a Excel** y el informe se descargará en el explorador.|
|**7** |Los datos de series temporales representados en el gráfico superior muestran métricas de uso diferentes agregadas para todo el espacio empresarial|
|**8** |Los datos tabulares representados en la mitad de botton muestran las distintas métricas de uso agregadas por usuario|


## <a name="make-the-user-specific-data-anonymous"></a>Establecer que los datos específicos del usuario sean anónimos

Para que los datos del informe de actividad de los usuarios de Teams sean anónimos, debe ser administrador global. El administrador global puede ocultar la información identificable (con hash MD5) como el nombre para mostrar, el nombre del grupo, el correo electrónico y el id. de AAD en el informe y su exportación.

1. En Centro de administración de Microsoft 365, vaya a **Configuración** \> **de** la organización y, en la pestaña **Servicios**, elija **Informes**.
    
2. Seleccione **Informes** y, a continuación **, elija Mostrar nombres de usuario, grupo y sitio ocultos en todos los informes**. Esta configuración se aplica tanto a los informes de uso de Centro de administración de Microsoft 365 como al Centro de administración de Teams.
  
3. Seleccione **Guardar cambios**.

> [!NOTE]
> Si habilita esta opción, se despersonalizará la información de usuario, grupo y nombre del sitio en el [informe de actividad de los usuarios de Teams](user-activity-report.md), el informe de [uso de dispositivos de Teams](device-usage-report.md) y el [informe de uso de Teams](teams-usage-report.md). A partir del 1 de septiembre de 2021, esta configuración está habilitada de forma predeterminada para todos los usuarios como parte de nuestro compromiso continuo de ayudar a proteger información importante y permitir que las empresas apoyen sus leyes de privacidad local. 
>
>Esta configuración también se aplica a los informes de uso de Microsoft 365 en Centro de administración de Microsoft 365, Microsoft Graph y Power BI.

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
