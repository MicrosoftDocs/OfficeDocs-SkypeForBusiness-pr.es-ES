---
title: Agregar dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anprakas
description: Aprenda a agregar el dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online para enviar notificaciones a miembros del equipo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f671d64b2928c3b5a81d38993143d9755ce42ba
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Agregar dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online 
=============================================================================

Tanto si crea un grupo de Office 365 en la consola de administración o usa Outlook, debe usar Exchange Online para enviar notificaciones de un miembro del equipo que se agrega a un grupo. Estos mensajes se generan desde su inquilino, ya que representan el FQDN de su dominio SMTP predeterminado.

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Microsoft Teams también usa Microsoft Exchange Online para enviar notificaciones a los miembros del equipo cuando se han agregado. La diferencia de ser el FQDN del dominio del mensaje SMTP es que se usa “@email.teams.microsoft.com” y podría ser detectado por el filtrado contra correo no deseado. Como puede ver en la imagen de abajo, Outlook considera este mensaje como un remitente externo, el cual está sujeto a las características de seguridad habituales, como el bloqueo de imágenes y cierto contenido.

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Para obtener los mejores resultados y un funcionamiento perfecto, le sugerimos que agregue el dominio SMTP de Microsoft Teams a la lista de “dominios aceptados” en la configuración de correo no deseado de Exchange Online: 

![Captura de pantalla de la sección Permitir listas de las opciones de configuración de correo no deseado de Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
