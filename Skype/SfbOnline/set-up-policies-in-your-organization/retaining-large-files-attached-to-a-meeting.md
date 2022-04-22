---
title: Conservar archivos grandes adjuntos a una reunión de Skype Empresarial
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, v-tophillips
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Puede adjuntar archivos a una reunión Skype Empresarial, que los participantes pueden abrir y descargar. Los archivos adjuntos a Skype Empresarial reuniones se conservan en los buzones de cualquier participante cuyo buzón se coloca en retención por juicio, tiene una Microsoft 365 o Office 365 directiva de retención aplicada, o se coloca en una retención asociada a un caso de exhibición de documentos electrónicos en el portal de cumplimiento de Microsoft Purview. Este contenido se guarda en las carpetas Elementos recuperables de los participantes en sus buzones.
ms.openlocfilehash: b799c1a471ac3884aa1b22cc1a681e53ee8284e9
ms.sourcegitcommit: 7d5266ae7e4a440ee45ab1873a30f4056bdcca1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2022
ms.locfileid: "65031875"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservar archivos grandes adjuntos a una reunión de Skype Empresarial

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Puede adjuntar archivos a una reunión Skype Empresarial, que los participantes pueden abrir y descargar. Los archivos adjuntos a Skype Empresarial reuniones se conservan en los buzones de cualquier participante cuyo buzón se coloca en retención por juicio, tiene una Microsoft 365 o Office 365 directiva de retención aplicada, o se coloca en una retención asociada a un caso de exhibición de documentos electrónicos en el portal de cumplimiento de Microsoft Purview. Este contenido se guarda en las carpetas **Elementos recuperables** de los participantes en sus buzones.
  
Los archivos que se conservan en buzones en espera se indexa y, por lo tanto, se pueden buscar al ejecutar una búsqueda de contenido en el Centro de cumplimiento de seguridad &amp; al buscar en el buzón de un participante. Sin embargo, los archivos adjuntos de más de 30 MB se dividen en dos o más archivos más pequeños y se guardan como archivos comprimidos (.zip). El  *contenido*  de estos archivos más pequeños no se indexa para la búsqueda y es posible que no se devuelva en una búsqueda de contenido. Sin embargo, los *metadatos*  de estos archivos (como el nombre de archivo y el autor) se indexan para la búsqueda y pueden devolverse en una búsqueda de contenido.
  
> [!IMPORTANT]
> La configuración de MaxReceiveSize y MaxSendSize para un buzón de Exchange Online puede afectar a la capacidad de conservar archivos grandes de Skype Empresarial reuniones. La configuración predeterminada para MaxReceiveSize y MaxSendSize es de 36 MB y 35 MB, respectivamente. Sin embargo, esta configuración predeterminada es demasiado pequeña para conservar cualquier archivo de una reunión de Skype Empresarial que supere los 30 MB. Esto se debe a que Exchange Online usa la codificación Base64 de datos adjuntos de mensajes y otros datos binarios. Cuando un mensaje está codificado, su tamaño aumenta en aproximadamente un 33 %. Por lo tanto, para asegurarse de que se conservan archivos grandes de Skype Empresarial reuniones, le recomendamos que aumente el valor de MaxReceiveSize y MaxSendSize a 39 MB (que es aproximadamente un 33 % mayor que el límite de tamaño de 30 MB que se explicó anteriormente) para los usuarios que se ponen en espera. En caso contrario, es posible que no se conserve un archivo grande adjunto a una reunión de Skype Empresarial. Para obtener más información sobre el uso de los comandos **Set-Mailbox -MaxReceiveSize** y **Set-Mailbox -MaxSendSize** en Exchange Online PowerShell, vea [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Los buzones que no estén en espera no tendrán ningún dato de reunión guardado. Por ejemplo, en una reunión de tres personas en la que los buzones de dos participantes se marcan para su retención, los datos de la reunión se guardan en los buzones de esos dos participantes, pero no en el buzón del tercer participante, cuyo buzón no está en espera.
  
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Bloquear transferencias de archivos punto a punto](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)
  
  
