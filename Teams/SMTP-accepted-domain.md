---
title: Agregar dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anprakas
description: Aprenda a agregar el dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online para enviar notificaciones a miembros del equipo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: dcddc2f2d36ed4ec6dd0bc12038b88ac0ec93103
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2018
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Agregar dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online 
=============================================================================

Tanto si crea un grupo de Office 365 en la consola de administración o usa Outlook, debe usar Exchange Online para enviar notificaciones de un miembro del equipo que se agrega a un grupo. Estos mensajes se generan desde su inquilino, ya que representan el FQDN de su dominio SMTP predeterminado.

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Microsoft Teams también usa Microsoft Exchange Online para enviar notificaciones a los miembros del equipo cuando se han agregado. La diferencia de ser el FQDN del dominio del mensaje SMTP es que se usa “@email.teams.microsoft.com” y podría ser detectado por el filtrado contra correo no deseado. Como puede ver en la imagen de abajo, Outlook considera este mensaje como un remitente externo, el cual está sujeto a las características de seguridad habituales, como el bloqueo de imágenes y cierto contenido.

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Para obtener los mejores resultados y un funcionamiento perfecto, le sugerimos que agregue el dominio SMTP de Microsoft Teams a la lista de “dominios aceptados” en la configuración de correo no deseado de Exchange Online: 

![Captura de pantalla de la sección Permitir listas de las opciones de configuración de correo no deseado de Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
