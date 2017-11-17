---
title: "Agregar dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online | Soporte técnico de Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Aprenda a agregar el dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online para enviar notificaciones a miembros del equipo.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 2006cde3cf2fc41a64b98fdc14004aa64876cb1a
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a><span data-ttu-id="2228a-103">Agregar dominio SMTP de Microsoft Teams como un dominio aceptado en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2228a-103">Add the Microsoft Teams SMTP domain as an accepted domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="2228a-p101">Tanto si crea un grupo de Office 365 en la consola de administración o usa Outlook, debe usar Exchange Online para enviar notificaciones de un miembro del equipo que se agrega a un grupo. Estos mensajes se generan desde su inquilino, ya que representan el FQDN de su dominio SMTP predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2228a-p101">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group. These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="2228a-p102">Microsoft Teams también usa Microsoft Exchange Online para enviar notificaciones a los miembros del equipo cuando se han agregado. La diferencia de ser el FQDN del dominio del mensaje SMTP es que se usa “@email.teams.microsoft.com” y podría ser detectado por el filtrado contra correo no deseado. Como puede ver en la imagen de abajo, Outlook considera este mensaje como un remitente externo, el cual está sujeto a las características de seguridad habituales, como el bloqueo de imágenes y cierto contenido.</span><span class="sxs-lookup"><span data-stu-id="2228a-p102">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added. The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering. As you can see from the image below, Outlook considers this message as an external sender which is subject to standard security features such as blocking images and certain content.</span></span>

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="2228a-111">Para obtener los mejores resultados y un funcionamiento perfecto, le sugerimos que agregue el dominio SMTP de Microsoft Teams a la lista de “dominios aceptados” en la configuración de correo no deseado de Exchange Online: </span><span class="sxs-lookup"><span data-stu-id="2228a-111">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “accepted domains” list in your Exchange Online spam configuration:</span></span>

![Captura de pantalla de la sección Permitir listas de las opciones de configuración de correo no deseado de Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
