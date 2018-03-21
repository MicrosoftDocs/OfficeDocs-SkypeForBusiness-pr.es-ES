---
title: "Retener grandes archivos adjuntos a un Skype para la reunión de negocios"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Puede adjuntar archivos a un Skype para reuniones de negocios, que los participantes, a continuación, pueden abrir y descargar. Archivos adjuntos de Skype para reuniones de negocios se mantienen en los buzones de cualquier participante cuyo buzón se coloca en retención para litigios, tiene aplicada una política de retención de Office 365 o se coloca en una suspensión de un caso de eDiscovery en la seguridad de Office 365 &amp; Centro de cumplimiento. Este contenido se guarda en las carpetas de elementos recuperables de los participantes en sus buzones."
ms.openlocfilehash: fb20055106362143b5c4573115e095637d873599
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Retener grandes archivos adjuntos a un Skype para la reunión de negocios

Puede adjuntar archivos a un Skype para reuniones de negocios, que los participantes, a continuación, pueden abrir y descargar. Archivos adjuntos de Skype para reuniones de negocios se mantienen en los buzones de cualquier participante cuyo buzón se coloca en retención para litigios, tiene aplicada una política de retención de Office 365 o se coloca en una suspensión de un caso de eDiscovery en la seguridad de Office 365 &amp; Centro de cumplimiento. Este contenido se guarda en las carpetas de **Elementos recuperables** de los participantes en sus buzones.
  
Archivos que se mantienen en los buzones de correo en espera están indizados y, por tanto, puede buscar cuando se ejecuta una búsqueda de contenido en la seguridad &amp; centro de cumplimiento de normas al buscar buzones de un participante. Sin embargo, archivos adjuntos mayores de 39 MB están divididas en dos o más archivos más pequeños y se guardan como archivos comprimidos (.zip). El *contenido* de estos archivos más pequeños no está indexado para búsqueda y no se puede devolver en una búsqueda de contenido. Sin embargo, los *metadatos* de estos archivos (por ejemplo, el nombre de archivo y el autor) está indexado para búsqueda y pueden devolver en una búsqueda de contenido.
  
> [!NOTE]
> Si el buzón está lleno o la administración de inquilinos configuró MaxSendSize para tener menos de 39 MB, carga el archivo de datos no se conservarán en todos. El predeterminado MaxSendSize es 150 MB, pero los administradores de inquilinos pueden configurar MaxSendSize para ser tan pequeña como 1 MB. 
  
Los buzones que no están suspendidos no tendrá todos los datos reunión guardado. Por ejemplo, en una reunión de tres personas en que los buzones de dos participantes se marcan para la retención, se guardan los datos de la reunión a los buzones de esos dos participantes, pero no en el buzón del tercer participante, cuyo buzón no está en mantenga.
  
## <a name="related-topics"></a>See also
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Transferencias de archivos punto a punto de bloque](block-point-to-point-file-transfers.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de la conferencia de la organización](set-up-conferencing-policies-for-your-organization.md)
  
## <a name="feedback"></a>¿Comentarios?
Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).