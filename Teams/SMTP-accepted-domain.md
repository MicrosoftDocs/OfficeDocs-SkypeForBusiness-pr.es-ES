---
title: Agregar el dominio SMTP de los equipos de Microsoft como un dominio de remitente permitidos en Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: anprakas
search.appverid: MET150
description: Aprenda a agregar el dominio SMTP de los equipos de Microsoft como un dominio de remitente permitidos en Exchange Online para enviar notificaciones a los miembros del equipo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f99503d91f9d2c674cea6ec1aaf9c5b747a1047
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014712"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Agregar el dominio SMTP de los equipos de Microsoft como un dominio de remitente permitidos en Exchange Online 
=============================================================================

Tanto si crea un grupo de Office 365 en la consola de administración o usa Outlook, debe usar Exchange Online para enviar notificaciones de un miembro del equipo que se agrega a un grupo. Estos mensajes se generan desde su inquilino, ya que representan el FQDN de su dominio SMTP predeterminado.

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Los equipos usa Microsoft Exchange Online así como para enviar notificaciones a los miembros del equipo cuando se ha añadido. La diferencia está en el FQDN del mensaje SMTP del dominio es "@email.teams.microsoft.com" y se pudo detectar el filtrado de spam.

![Captura de pantalla de un encabezado de mensaje de correo electrónico de Outlook de ejemplo donde se ve que se ha agregado un usuario a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Para obtener mejores resultados y un funcionamiento ininterrumpido, considere la posibilidad de agregar el dominio SMTP de los equipos de Microsoft a la lista "permitido de dominios de remitente" en su configuración de correo no deseado de Exchange Online:

![Captura de pantalla de la sección Permitir listas de las opciones de configuración de correo no deseado de Exchange Online.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
