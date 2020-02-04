---
title: Retener archivos grandes adjuntos a una reunión de Skype empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Puede adjuntar archivos a una reunión de Skype empresarial, que los participantes pueden abrir y descargar. Los archivos adjuntos a reuniones de Skype empresarial se conservan en los buzones de cualquier participante cuyo buzón se coloca en retención por juicio, tiene una directiva de retención de Office 365 o se coloca en espera asociada a un caso de exhibición de &amp; correo en el centro de cumplimiento de seguridad de Office 365. Este contenido se guarda en las carpetas de elementos recuperables de los participantes en sus buzones.
ms.openlocfilehash: fdd6786cb9b7e5535abee47eb1f0b538b6a22b45
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706655"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Retener archivos grandes adjuntos a una reunión de Skype empresarial

Puede adjuntar archivos a una reunión de Skype empresarial, que los participantes pueden abrir y descargar. Los archivos adjuntos a reuniones de Skype empresarial se conservan en los buzones de cualquier participante cuyo buzón se coloca en retención por juicio, tiene una directiva de retención de Office 365 o se coloca en espera asociada a un caso de exhibición de &amp; correo en el centro de cumplimiento de seguridad de Office 365. Este contenido se guarda en las carpetas de **elementos recuperables de los** participantes en sus buzones.
  
Los archivos que se conservan en los buzones en espera se indizan y, por lo tanto, se pueden buscar cuando &amp; se ejecuta una búsqueda de contenido en el centro de cumplimiento de seguridad al buscar el buzón de un participante. Sin embargo, los archivos adjuntos de más de 30 MB se dividen en dos o más archivos más pequeños y se guardan como archivos comprimidos (. zip). El *contenido* de estos archivos más pequeños no está indizado para la búsqueda y es posible que no se devuelva en una búsqueda de contenido. Sin embargo, los *metadatos* de estos archivos (como el nombre de archivo y el autor) están indizados para la búsqueda y pueden devolverse en una búsqueda de contenido.
  
> [!IMPORTANT]
> La configuración de MaxReceiveSize y MaxSendSize para un buzón de Exchange Online puede afectar a la capacidad de conservar archivos grandes de reuniones de Skype empresarial. La configuración predeterminada de MaxReceiveSize y MaxSendSize son 36 MB y 35 MB, respectivamente. Sin embargo, esta configuración predeterminada es demasiado pequeña para retener cualquier archivo de una reunión de Skype empresarial que sea superior a 30 MB. Esto se debe a que Exchange online usa la codificación Base64 de datos adjuntos de mensajes y otros datos binarios. Cuando se codifica un mensaje, su tamaño aumenta en aproximadamente 33%. Por lo tanto, para asegurarse de que se conservan los archivos grandes de las reuniones de Skype empresarial, le recomendamos que aumente el valor de MaxReceiveSize y MaxSendSize a 39 MB (es decir, aproximadamente 33% más que el límite de tamaño de 30 MB que se explicó anteriormente). para los usuarios que se encuentran en espera. En caso contrario, es posible que no se conserve un archivo grande adjunto a una reunión de Skype empresarial. Para obtener más información sobre el uso de los comandos **set-Mailbox-MaxReceiveSize** y **set-Mailbox-MaxSendSize** en Exchange Online PowerShell, consulte [set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Los buzones que no estén en espera no tendrán ningún dato de la reunión guardado. Por ejemplo, en una reunión de tres personas en la que los buzones de dos participantes están marcados para retención, los datos de la reunión se guardan en los buzones de esos dos participantes, pero no en el buzón del tercer participante, cuyo buzón de correo no está en espera.
  
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Bloquear las transferencias de archivos punto a punto](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)
  
  
 