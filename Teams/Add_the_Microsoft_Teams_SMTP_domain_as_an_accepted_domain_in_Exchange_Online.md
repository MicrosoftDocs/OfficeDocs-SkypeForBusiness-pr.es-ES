---
title: "Agregar dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/10/2017
ms.topic: solution
ms.prod: teams
description: Aprenda a agregar el dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online para enviar notificaciones a miembros del equipo.
ms.openlocfilehash: 5e006f8074bd7d5675d84502ccafb0adf29698e3
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>Agregar dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online 
=============================================================================

Tanto si crea un grupo de Office 365 en la consola de administración o usa Outlook, debe usar Exchange Online para enviar notificaciones de un miembro del equipo que se agrega a un grupo. Estos mensajes se generan desde su inquilino, ya que representan el FQDN de su dominio SMTP predeterminado.

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Microsoft Teams también usa Microsoft Exchange Online para enviar notificaciones a los miembros del equipo cuando se han agregado. La diferencia de ser el FQDN del dominio del mensaje SMTP es que se usa “@email.teams.microsoft.com” y podría ser detectado por el filtrado contra correo no deseado. Como puede ver en la imagen de abajo, Outlook considera este mensaje como un remitente externo, el cual está sujeto a las características de seguridad habituales, como el bloqueo de imágenes y cierto contenido.

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Para obtener los mejores resultados y un funcionamiento perfecto, le sugerimos que agregue el dominio SMTP de Microsoft Teams a la lista de “dominios aceptados” en la configuración de correo no deseado de Exchange Online: 

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
