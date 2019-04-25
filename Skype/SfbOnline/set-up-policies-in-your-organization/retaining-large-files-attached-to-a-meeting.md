---
title: Conservación de grandes archivos adjuntos a un Skype para la reunión de negocios
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Puede adjuntar archivos a un Skype para la reunión de negocios, qué participantes, a continuación, pueden abrir y descargan. Archivos adjuntos a Skype para reuniones de negocios se conservan en los buzones de correo de cualquier participante cuyo buzón de correo se pondrá en suspensión por litigio, tiene aplicada una directiva de retención de Office 365 o se coloca en una espera asociada con un caso de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; Centro de cumplimiento. Este contenido se guarda en las carpetas de elementos recuperables de los participantes en sus buzones de correo.
ms.openlocfilehash: f9a18aaf556427ccc1fad2700b40f40ff057be6a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237522"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservación de grandes archivos adjuntos a un Skype para la reunión de negocios

Puede adjuntar archivos a un Skype para la reunión de negocios, qué participantes, a continuación, pueden abrir y descargan. Archivos adjuntos a Skype para reuniones de negocios se conservan en los buzones de correo de cualquier participante cuyo buzón de correo se pondrá en suspensión por litigio, tiene aplicada una directiva de retención de Office 365 o se coloca en una espera asociada con un caso de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; Centro de cumplimiento. Este contenido se guarda en las carpetas de **Elementos recuperables** de los participantes en sus buzones de correo.
  
Los archivos que se conservan en los buzones de correo en espera se indizan y, por tanto, se puede buscar cuando se ejecuta una búsqueda de contenido en la seguridad &amp; centro de cumplimiento al buscar en el buzón de correo de los participantes. Sin embargo, los archivos adjuntos que superan los 30 MB están divididas en dos o más archivos más pequeños y se guardan como archivos comprimidos (.zip). El *contenido* de estos archivos más pequeños no se indiza para la búsqueda y es posible que no se devuelven en una búsqueda de contenido. Sin embargo, los *metadatos* de estos archivos (por ejemplo, el nombre de archivo y el autor) se indizan para la búsqueda y es posible que se devuelven en una búsqueda de contenido.
  
> [!IMPORTANT]
> La configuración de MaxReceiveSize y MaxSendSize para un buzón de Exchange Online puede afectar a la capacidad para conservar archivos grandes de Skype para reuniones de negocios. La configuración predeterminada de MaxReceiveSize y MaxSendSize es 36 y 35 MB, respectivamente. Sin embargo, estos valores predeterminados son demasiado pequeños para conservar cualquier archivo desde una Skype para la reunión de negocios que es mayor que 30 MB. Esto es debido a que Exchange Online utiliza la codificación Base64 de los datos adjuntos de mensajes y otros datos binarios. Cuando se codifica un mensaje, su tamaño se incrementa en aproximadamente un 33%. Por lo tanto, para asegurarse de que se conservan los archivos de gran tamaño de Skype para reuniones de negocios, se recomienda que aumente el valor de MaxReceiveSize y MaxSendSize a 39 MB (que es aproximadamente un 33% mayor que el límite de tamaño de 30 MB que se explicó anteriormente) para los usuarios que se colocan en espera. De lo contrario, no es posible que se conserva un archivo de gran tamaño adjunto a un Skype para la reunión de negocios. Para obtener más información acerca del uso de los comandos de **Set-Mailbox-MaxSendSize** y **Set-Mailbox-MaxReceiveSize** en Exchange Online PowerShell, consulte [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Los buzones que no están en espera no tendrán guardados los datos de la reunión. Por ejemplo, en una reunión de tres personas en que los buzones de correo de dos participantes se marcan para la retención, se guardan los datos de la reunión a los buzones de esos dos participantes, pero no para el buzón de correo del tercer participante, cuyo buzón de correo no está en suspensión.
  
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Transferencias de archivos punto a punto de bloque](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar las directivas de conferencia en la organización](set-up-conferencing-policies-for-your-organization.md)
  
  
 