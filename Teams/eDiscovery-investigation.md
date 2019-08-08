---
title: Realizar una investigación de eDiscovery en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: Conozca los pasos que debe seguir cuando necesite realizar una investigación de eDiscovery, como por ejemplo, cuando debe entregar toda la información almacenada electrónicamente para procedimientos legales.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6831ec2cef16e65e2fd8dd722d436c12b7548a5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236362"
---
<a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Realizar una investigación de eDiscovery en Microsoft Teams
============================

Las grandes empresas suelen estar expuestas a un procedimiento legal de alta multa que exige el envío de toda la información almacenada electrónicamente (ESI).

Todos los equipos 1:1 o chats grupales se registran en el diario de los buzones de los usuarios respectivos, y todos los mensajes de canal se registran en el buzón del grupo que representa al equipo. Los archivos cargados están cubiertos por la funcionalidad de eDiscovery para SharePoint Online y OneDrive para la empresa.

1.  Para realizar una investigación de eDiscovery con el contenido de Microsoft Teams, revise el paso 1 de [este](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) vínculo.

2.  Los datos de Microsoft Teams aparecerán como mensajes instantáneos o conversaciones en la salida de la exportación de eDiscovery de Excel, y puede montar el. PST en Outlook para ver los mensajes después de la exportación.

    Al montar el. PST para el equipo, tenga en cuenta que todas las conversaciones se guardan en la carpeta chat de equipo en historial de conversaciones. El título del mensaje se alinea con el equipo y el canal. Desde revisar la imagen a continuación, puede ver este mensaje de Bob que ha expuesto el canal 7 del equipo de especificaciones de fabricación.

    ![Captura de pantalla de una carpeta de chat de equipo en el buzón de un usuario en Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

3.  Para ver chats privados en el buzón de un usuario, tenga en cuenta que también se encuentran en la carpeta Chat de equipo en Historial de conversaciones.

## <a name="ediscovery-of-guest-to-guest-chats"></a>eDiscovery de conversaciones de invitado a invitado

Sin un buzón de correo, los chats entre invitados (1xN chats en los que no hay usuarios de inquilinos domésticos) no se indizarán y, como resultado, no se incluirían en eDiscovery. Para facilitar la exhibición de mensajes instantáneos a los chats entre invitados, se crea un buzón de correo basado en la nube (o un buzón de correo fantasma) para almacenar los datos de 1xN. Una vez que los datos de la conversación de equipos se almacenan en el buzón basado en la nube, están indizados para eDiscovery y la búsqueda de contenido de cumplimiento.

En la ilustración siguiente se muestra cómo funciona eDiscovery para los chats entre invitados en los que no hay un buzón.

![invitado a invitado: chats con sin buzón de correo](media/conduct-an-ediscovery-investigation-of-content-in-microsoft-teams-image2.png)
