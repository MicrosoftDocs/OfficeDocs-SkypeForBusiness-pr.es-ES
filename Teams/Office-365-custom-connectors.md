---
title: Usar Office 365 y conectores personalizados en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: Los conectores mantienen a su equipo al día al brindarles, directamente en un canal, contenido y actualizaciones de servicios que se utilizan con frecuencia.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce087aed26c22fb97a0ad9b5161927f6a6afea4d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35222049"
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
-----------------------------

Es muy fácil desarrollar conectores personalizados que puedan integrarse con las aplicaciones de línea de negocio (LOB). Puede usar el conector de enlace de **entrada de correo entrante** integrado para crear un extremo de un canal que extrae datos de cualquier aplicación que use métodos http post.

1. Agregue **webhook entrante** como lo haría con cualquier otro conector.

    ![Captura de pantalla de la opción para agregar el conector de webhook entrante.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. Para crear un webhook, especifique un **nombre**, actualice la imagen de webhook y haga clic en **Crear**.

    ![Captura de pantalla de la página de configuración del conector de entrada del Web entrante.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. Las aplicaciones que insertan datos en este canal requieren la dirección URL del conector para webhook. Se crea una dirección URL única al crear el webhook. Comparta esta dirección URL con sus desarrolladores para que puedan configurar sus aplicaciones para insertar datos, según sea necesario.

    ![Captura de pantalla de la URL exclusiva del webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. Cuando una aplicación externa inserta datos en un conector, el mensaje se muestra en la lista de conversaciones del canal como un mensaje especial denominado mensaje de **tarjeta de conector**.

    ![Captura de pantalla de la interfaz de Teams donde se ve un mensaje de la tarjeta de conector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     Los desarrolladores pueden configurar sus aplicaciones para crear estas tarjetas enviando una solicitud HTTP con una carga de JSON simple a la dirección webhook de un equipo, que es una dirección URL única de ese extremo proporcionado por el asistente. Haga que los programadores consulten [Introducción a Office 365 Connectors for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), en la red de programadores de Microsoft, que tiene instrucciones detalladas y ejemplos de conectores. Otros recursos incluyen [las aplicaciones Connect para los grupos de Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) y el [centro de desarrollo de Office (Microsoft Teams)](https://go.microsoft.com/fwlink/?linkid=855784).
