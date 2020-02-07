---
title: Usar Office 365 y conectores personalizados en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Los conectores mantienen a su equipo al día al brindarles, directamente en un canal, contenido y actualizaciones de servicios que se utilizan con frecuencia.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc65939048fd8e54bd122a4dc52d2a611b8453cc
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834380"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Usar Office 365 y conectores personalizados en Microsoft Teams
=======================================================

Los conectores mantienen actualizado a su equipo mediante la entrega de contenido y actualizaciones de servicio de uso frecuente directamente en un canal. Con los conectores, los usuarios de Microsoft Teams pueden recibir actualizaciones de servicios populares como Twitter, Trello, Wunderlist, GitHub y Azure DevOps dentro del flujo de chat de su equipo.

Cualquier miembro de un equipo puede conectar su equipo a servicios en la nube populares con los conectores si los permisos del equipo lo permiten y todos los miembros del equipo reciben notificaciones de actividades de ese servicio. Los conectores seguirán funcionando incluso después de que el miembro haya dejado de instalar el conector. Cualquier miembro del equipo con los permisos para quitar la configuración de otros miembros puede modificar los conectores.

Los conectores de Office 365 se pueden usar con grupos de Microsoft Teams y Office 365, lo que permite que todos los miembros permanezcan sincronizados y reciban la información relevante rápidamente. Tanto Microsoft Teams como Exchange usan el mismo modelo de conector, que le permite usar los mismos conectores en ambas plataformas. Sin embargo, vale la pena tener en cuentan que deshabilitar conectores para el grupo de Office 365 del que depende un equipo deshabilitará la capacidad de crear conectores para ese equipo también.

<a name="add-a-connector-to-a-channel"></a>Agregar un conector a un canal
----------------------------

En la actualidad, puede Agregar conectores con el escritorio de Microsoft Teams y los clientes Web. Sin embargo, la información publicada por estos conectores puede verse en **todos los clientes** , incluidos los teléfonos móviles.

1. Para agregar un conector a un canal, haga clic en los **puntos suspensivos (...),** a la derecha de un nombre de canal y, a continuación, haga clic en **conectores**.

    ![Captura de pantalla de la interfaz de equipos con la opción conectores seleccionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. Puede elegir entre una variedad de conectores disponibles y, a continuación, hacer clic en **Agregar**.

    ![Captura de pantalla del cuadro de diálogo conectores que muestra los conectores disponibles.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Complete la información necesaria del conector seleccionado y haga clic en **Guardar**. Cada conector requiere un conjunto diverso de información para funcionar correctamente; incluso es posible que algunos le pidan iniciar sesión en el servicio mediante los vínculos provistos en la página de configuración del conector.

    ![Captura de pantalla de la página de configuración para el conector de RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. Los datos proporcionados por el conector se publican automáticamente en el canal.

    ![Captura de pantalla de la interfaz de Teams donde se ve una conversación en un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Desarrollar conectores personalizados
----------------------------

También puede crear conectores personalizados, así como los webhooks entrantes y salientes. Consulte nuestra[ documentación para desarrolladores ](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)para obtener más información.
