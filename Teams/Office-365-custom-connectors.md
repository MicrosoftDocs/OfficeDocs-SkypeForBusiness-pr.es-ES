---
title: Usar Office 365 y conectores personalizados en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara, lucarras
description: "Los conectores mantienen a su equipo al día al brindarles, directamente en un canal, contenido y actualizaciones de servicios que se utilizan con frecuencia."
appliesto:
- Microsoft Teams
ms.openlocfilehash: 119d2a7bac94f3695a068e64f56b5613b5687e2f
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Usar Office 365 y conectores personalizados en Microsoft Teams
=======================================================

Los conectores mantienen a su equipo al día al brindarles, directamente en un canal, contenido y actualizaciones de servicios que se utilizan con frecuencia. Con los conectores, los usuarios de Microsoft Teams pueden recibir actualizaciones de servicios populares como Twitter, Trello, Wunderlist, GitHub y VSTS en el flujo de chat de su equipo.

Cualquier miembro de un equipo puede conectar su equipo con servicios en la nube populares a través de los conectores, y se notifica a todos los miembros del equipo sobre las actividades de ese servicio. Si se quita a un usuario de un equipo, los conectores que el usuario eliminado agregó dejan de funcionar. Las reuniones programadas siguen en efecto porque se encuentran en el calendario del grupo.

Los conectores de Office 365 pueden utilizarse con Microsoft Teams y grupos de Office 365, lo cual facilita que todos los miembros puedan estar sincronizados y recibir información relevante rápidamente. Tanto Microsoft Teams como Exchange utilizan el mismo modelo de conectores, lo que permite que pueda usar los mismos conectores en ambas plataformas.

Actualmente, es posible agregar conectores mediante los clientes de escritorio y web de Microsoft Teams. Sin embargo, la información publicada por estos conectores puede verse en **todos los clientes**, incluso el móvil.

1.  Para agregar un conector a un canal, haga clic en los **puntos suspensivos (...)** a la derecha del nombre del canal y, a continuación, haga clic en **Conectores**.

    ![Captura de pantalla de la interfaz de Teams con un nombre de canal seleccionado y la opción Conectores seleccionada.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2.  Los usuarios pueden seleccionar entre una variedad de conectores disponibles y, a continuación, deben hacer clic en **Agregar**.

    ![Captura de pantalla del cuadro de diálogo Conectores donde se ven los conectores disponibles que se van a agregar.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3.  Complete la información necesaria del conector seleccionado y haga clic en **Guardar**. Cada conector requiere un conjunto diverso de información para funcionar correctamente; incluso es posible que algunos le pidan iniciar sesión en el servicio mediante los vínculos provistos en la página de configuración del conector.

    ![Captura de pantalla de la página de configuración para el conector de RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4.  Los datos proporcionados por el conector se publican automáticamente en el canal.

    ![Captura de pantalla de la interfaz de Teams donde se ve una conversación en un canal.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Desarrollar conectores personalizados
-----------------------------

Es muy fácil desarrollar conectores personalizados que puedan integrarse en sus aplicaciones de línea de negocio (LOB). Puede usar el conector integrado **webhook entrante** para crear un perímetro para un canal, que extraiga datos de cualquier ubicación mediante métodos de registro HTTP.

1.  Agregue **webhook entrante** como lo haría con cualquier otro conector.

    ![Captura de pantalla de la opción para agregar el conector de webhook entrante.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2.  Para crear un webhook, especifique un **nombre**, actualice la imagen de webhook y haga clic en **Crear**.

    ![Captura de pantalla de la página de configuración para el conector de webhook entrante. ](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3.  Las aplicaciones que insertan datos en este canal requieren una URL del conector webhook. Se crea una **URL única** al crear el **webhook**. Comparta esta URL con sus desarrolladores, de modo que puedan configurar sus aplicaciones para insertar datos, según sea necesario.

    ![Captura de pantalla de la URL exclusiva del webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4.  Cuando una aplicación externa inserta datos en un conector, el mensaje se muestra en la lista de conversaciones del canal como un mensaje especial denominado mensaje de **tarjeta de conector**.

    ![Captura de pantalla de la interfaz de Teams donde se ve un mensaje de la tarjeta de conector.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

Los desarrolladores pueden configurar sus aplicaciones para crear estas tarjetas. Para esto, deben enviar una solicitud HTTP con una carga JSON simple a una dirección de webhook de Microsoft Teams, que es una URL única para ese perímetro, proporcionada por el asistente. Pídales a sus desarrolladores que consulten [Comenzar a trabajar con conectores de Office 365 para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855783), en Microsoft Developer Network, que incluye instrucciones detalladas y ejemplos de conectores. Otros recursos que pueden consultar son [Conectar aplicaciones a sus grupos en Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) y [Office Dev Center para Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=855784).
