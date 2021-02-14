---
title: Retención de archivos grandes adjuntos a una reunión de Skype Empresarial
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
description: Puede adjuntar archivos a una reunión de Skype Empresarial para que los participantes puedan abrirlos y descargarlos. Los archivos adjuntos a reuniones de Skype Empresarial se conservan en los buzones de cualquier participante cuyo buzón se coloque en retención por juicio, tenga aplicada una directiva de retención de Microsoft 365 u Office 365 o se coloque en una retención asociada a un caso de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365. Este contenido se guarda en las carpetas Elementos recuperables de los participantes en sus buzones.
ms.openlocfilehash: 23566272cec4f1afef2a0a067fdebdd2f497e312
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164079"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Retención de archivos grandes adjuntos a una reunión de Skype Empresarial

Puede adjuntar archivos a una reunión de Skype Empresarial para que los participantes puedan abrirlos y descargarlos. Los archivos adjuntos a reuniones de Skype Empresarial se conservan en los buzones de cualquier participante cuyo buzón se coloque en retención por juicio, tenga aplicada una directiva de retención de Microsoft 365 u Office 365 o se coloque en una retención asociada a un caso de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365. Este contenido se guarda en las carpetas **Elementos** recuperables de los participantes en sus buzones.
  
Los archivos que se conservan en buzones en retención están indexados y, por lo tanto, se pueden buscar al ejecutar una búsqueda de contenido en el Centro de cumplimiento de seguridad al buscar en el buzón &amp; de un participante. Sin embargo, los archivos adjuntos de más de 30 MB se dividen en dos o más archivos más pequeños y se guardan como archivos comprimidos (.zip). El  *contenido*  de estos archivos más pequeños no está indexado para la búsqueda y es posible que no se devuelva en una búsqueda de contenido. Sin embargo, *los metadatos*  de estos archivos (como el nombre de archivo y el autor) están indexados para la búsqueda y pueden devolverse en una búsqueda de contenido.
  
> [!IMPORTANT]
> La configuración de MaxReceiveSize y MaxSendSize de un buzón de Exchange Online puede afectar a la capacidad de conservar archivos grandes de reuniones de Skype Empresarial. La configuración predeterminada para MaxReceiveSize y MaxSendSize es de 36 MB y 35 MB, respectivamente. Sin embargo, esta configuración predeterminada es demasiado pequeña para conservar cualquier archivo de una reunión de Skype Empresarial que sea superior a 30 MB. Esto se debe a que Exchange Online usa la codificación Base64 de datos adjuntos de mensajes y otros datos binarios. Cuando un mensaje se codifica, su tamaño aumenta en aproximadamente un 33 %. Por lo tanto, para asegurarse de que se conservan archivos grandes de reuniones de Skype Empresarial, le recomendamos que aumente el valor de MaxReceiveSize y MaxSendSize a 39 MB (que es aproximadamente un 33 % mayor que el límite de tamaño de 30 MB que se explicó anteriormente) para los usuarios que están en espera. En caso contrario, es posible que no se conserve un archivo grande adjunto a una reunión de Skype Empresarial. Para obtener más información sobre cómo usar los comandos **Set-Mailbox -MaxReceiveSize** y **Set-Mailbox -MaxSendSize** en PowerShell de Exchange Online, vea [Set-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox)
  
Los buzones que no están en espera no tendrán los datos de la reunión guardados. Por ejemplo, en una reunión de tres personas en la que los buzones de dos participantes están marcados para ser retención, los datos de la reunión se guardan en los buzones de esos dos participantes, pero no en el buzón del tercer participante, cuyo buzón no está en espera.
  
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Bloquear las transferencias de archivos de punto a punto](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)
  
  
 
