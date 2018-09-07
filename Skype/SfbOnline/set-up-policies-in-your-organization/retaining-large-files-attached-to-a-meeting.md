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
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="023f2-105">Conservación de grandes archivos adjuntos a un Skype para la reunión de negocios</span><span class="sxs-lookup"><span data-stu-id="023f2-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="023f2-106">Puede adjuntar archivos a un Skype para la reunión de negocios, qué participantes, a continuación, pueden abrir y descargan.</span><span class="sxs-lookup"><span data-stu-id="023f2-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="023f2-107">Archivos adjuntos a Skype para reuniones de negocios se conservan en los buzones de correo de cualquier participante cuyo buzón de correo se pondrá en suspensión por litigio, tiene aplicada una directiva de retención de Office 365 o se coloca en una espera asociada con un caso de exhibición de documentos electrónicos en la seguridad de Office 365 &amp; Centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="023f2-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="023f2-108">Este contenido se guarda en las carpetas de **Elementos recuperables** de los participantes en sus buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="023f2-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="023f2-109">Los archivos que se conservan en los buzones de correo en espera se indizan y, por tanto, se puede buscar cuando se ejecuta una búsqueda de contenido en la seguridad &amp; centro de cumplimiento al buscar en el buzón de correo de los participantes.</span><span class="sxs-lookup"><span data-stu-id="023f2-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="023f2-110">Sin embargo, los archivos adjuntos que superan los 39 MB están divididas en dos o más archivos más pequeños y se guardan como archivos comprimidos (.zip).</span><span class="sxs-lookup"><span data-stu-id="023f2-110">However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="023f2-111">El *contenido* de estos archivos más pequeños no se indiza para la búsqueda y es posible que no se devuelven en una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="023f2-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="023f2-112">Sin embargo, los *metadatos* de estos archivos (por ejemplo, el nombre de archivo y el autor) se indizan para la búsqueda y es posible que se devuelven en una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="023f2-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="023f2-113">Si el buzón está lleno o la administración de inquilinos ha configurado MaxSendSize para ser menor de 39 MB, carga el archivo de datos no se conservarán en absoluto.</span><span class="sxs-lookup"><span data-stu-id="023f2-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all.</span></span> <span data-ttu-id="023f2-114">El valor predeterminado MaxSendSize es de 150 MB, pero los administradores de inquilinos pueden configurar MaxSendSize para ser tan pequeños como 1 MB.</span><span class="sxs-lookup"><span data-stu-id="023f2-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="023f2-115">Los buzones que no están en espera no tendrán guardados los datos de la reunión.</span><span class="sxs-lookup"><span data-stu-id="023f2-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="023f2-116">Por ejemplo, en una reunión de tres personas en que los buzones de correo de dos participantes se marcan para la retención, se guardan los datos de la reunión a los buzones de esos dos participantes, pero no para el buzón de correo del tercer participante, cuyo buzón de correo no está en suspensión.</span><span class="sxs-lookup"><span data-stu-id="023f2-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="023f2-117">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="023f2-117">Related topics</span></span>
[<span data-ttu-id="023f2-118">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="023f2-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="023f2-119">Transferencias de archivos punto a punto de bloque</span><span class="sxs-lookup"><span data-stu-id="023f2-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="023f2-120">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="023f2-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="023f2-121">Configurar las directivas de conferencia en la organización</span><span class="sxs-lookup"><span data-stu-id="023f2-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
 