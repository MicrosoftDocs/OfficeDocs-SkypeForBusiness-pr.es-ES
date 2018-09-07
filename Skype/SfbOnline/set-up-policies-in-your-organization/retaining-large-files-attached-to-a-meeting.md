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
ms.openlocfilehash: b38f2ec56fb53932c08ede2a8c6f39557216a6b8
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864979"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Conservación de grandes archivos adjuntos a un Skype para la reunión de negocios

Puede adjuntar archivos a un Skype para la reunión de negocios, qué participantes, a continuación, pueden abrir y descargan. Archivos adjuntos a Skype para reuniones de negocios se conservan en los buzones de correo de cualquier participante cuyo buzón de correo se pondrá en suspensión por litigio, tiene aplicada una directiva de retención de Office 365 o se coloca en una espera asociada con un caso de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; Centro de cumplimiento. Este contenido se guarda en las carpetas de **Elementos recuperables** de los participantes en sus buzones de correo.
  
Los archivos que se conservan en los buzones de correo en espera se indizan y, por tanto, se puede buscar cuando se ejecuta una búsqueda de contenido en la seguridad &amp; centro de cumplimiento al buscar en el buzón de correo de los participantes. Sin embargo, los archivos adjuntos que superan los 39 MB están divididas en dos o más archivos más pequeños y se guardan como archivos comprimidos (.zip). El *contenido* de estos archivos más pequeños no se indiza para la búsqueda y es posible que no se devuelven en una búsqueda de contenido. Sin embargo, los *metadatos* de estos archivos (por ejemplo, el nombre de archivo y el autor) se indizan para la búsqueda y es posible que se devuelven en una búsqueda de contenido.
  
> [!NOTE]
> Si el buzón está lleno o la administración de inquilinos ha configurado MaxSendSize para ser menor de 39 MB, carga el archivo de datos no se conservarán en absoluto. El valor predeterminado MaxSendSize es de 150 MB, pero los administradores de inquilinos pueden configurar MaxSendSize para ser tan pequeños como 1 MB. 
  
Los buzones que no están en espera no tendrán guardados los datos de la reunión. Por ejemplo, en una reunión de tres personas en que los buzones de correo de dos participantes se marcan para la retención, se guardan los datos de la reunión a los buzones de esos dos participantes, pero no para el buzón de correo del tercer participante, cuyo buzón de correo no está en suspensión.
  
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Transferencias de archivos punto a punto de bloque](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar las directivas de conferencia en la organización](set-up-conferencing-policies-for-your-organization.md)
  
  
 