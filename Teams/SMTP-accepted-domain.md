---
title: Agregar el dominio SMTP de Microsoft Teams como un dominio de remitente permitido en Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: Aprenda a agregar el dominio SMTP de Microsoft Teams como dominio de remitentes permitido en Exchange Online para enviar notificaciones a los miembros del equipo.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ae8be5c4b596b8815b8677b6214163924cbb183
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37567131"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>Agregar el dominio SMTP de Microsoft Teams como un dominio de remitente permitido en Exchange Online 
=============================================================================

Tanto si crea un grupo de Office 365 en la consola de administración o usa Outlook, debe usar Exchange Online para enviar notificaciones de un miembro del equipo que se agrega a un grupo. Estos mensajes se generan desde su inquilino, ya que representan el FQDN de su dominio SMTP predeterminado.

![Captura de pantalla de un encabezado de mensaje que muestra un usuario agregado a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

Teams usa Microsoft Exchange Online para enviar notificaciones a los miembros del equipo cuando se hayan agregado. La diferencia es que el FQDN de dominio del mensaje SMTP es "@email. teams.microsoft.com" para los inquilinos comerciales/empresariales y "@GCC-email.teams.com" para inquilinos de administración pública y podría ser detectado por el filtrado de correo no deseado.

![Captura de pantalla de un encabezado de mensaje que muestra un usuario agregado a un grupo.](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

Para obtener el mejor resultado y el funcionamiento sin problemas, considere la posibilidad de agregar el dominio SMTP de Microsoft Teams a la lista "dominios de remitente permitidos" de su configuración de correo no deseado de Exchange Online:

![Captura de pantalla de la sección permitir listas de opciones de configuración de correo no deseado](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
