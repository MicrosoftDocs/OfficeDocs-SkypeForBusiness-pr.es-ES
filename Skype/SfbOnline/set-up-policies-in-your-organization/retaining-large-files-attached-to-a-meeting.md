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
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="752ec-105">Retener grandes archivos adjuntos a un Skype para la reunión de negocios</span><span class="sxs-lookup"><span data-stu-id="752ec-105">Retaining large files attached to a Skype for Business meeting</span></span>

<span data-ttu-id="752ec-106">Puede adjuntar archivos a un Skype para reuniones de negocios, que los participantes, a continuación, pueden abrir y descargar.</span><span class="sxs-lookup"><span data-stu-id="752ec-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="752ec-107">Archivos adjuntos de Skype para reuniones de negocios se mantienen en los buzones de cualquier participante cuyo buzón se coloca en retención para litigios, tiene aplicada una política de retención de Office 365 o se coloca en una suspensión de un caso de eDiscovery en la seguridad de Office 365 &amp; Centro de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="752ec-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has an Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="752ec-108">Este contenido se guarda en las carpetas de **Elementos recuperables** de los participantes en sus buzones.</span><span class="sxs-lookup"><span data-stu-id="752ec-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="752ec-109">Archivos que se mantienen en los buzones de correo en espera están indizados y, por tanto, puede buscar cuando se ejecuta una búsqueda de contenido en la seguridad &amp; centro de cumplimiento de normas al buscar buzones de un participante.</span><span class="sxs-lookup"><span data-stu-id="752ec-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="752ec-110">Sin embargo, archivos adjuntos mayores de 39 MB están divididas en dos o más archivos más pequeños y se guardan como archivos comprimidos (.zip).</span><span class="sxs-lookup"><span data-stu-id="752ec-110">However, attached files that are larger than 39 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="752ec-111">El *contenido* de estos archivos más pequeños no está indexado para búsqueda y no se puede devolver en una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="752ec-111">The  *content*  of these smaller files is not indexed for search, and might not be returned in a Content Search.</span></span> <span data-ttu-id="752ec-112">Sin embargo, los *metadatos* de estos archivos (por ejemplo, el nombre de archivo y el autor) está indexado para búsqueda y pueden devolver en una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="752ec-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search, and might be returned in a Content Search.</span></span>
  
> [!NOTE]
> <span data-ttu-id="752ec-113">Si el buzón está lleno o la administración de inquilinos configuró MaxSendSize para tener menos de 39 MB, carga el archivo de datos no se conservarán en todos.</span><span class="sxs-lookup"><span data-stu-id="752ec-113">If the mailbox is full or the tenant admin has configured MaxSendSize to be smaller than 39 MB, uploaded file data will not be retained at all.</span></span> <span data-ttu-id="752ec-114">El predeterminado MaxSendSize es 150 MB, pero los administradores de inquilinos pueden configurar MaxSendSize para ser tan pequeña como 1 MB.</span><span class="sxs-lookup"><span data-stu-id="752ec-114">The default MaxSendSize is 150 MB, but tenant admins can configure MaxSendSize to be as small as 1 MB.</span></span> 
  
<span data-ttu-id="752ec-115">Los buzones que no están suspendidos no tendrá todos los datos reunión guardado.</span><span class="sxs-lookup"><span data-stu-id="752ec-115">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="752ec-116">Por ejemplo, en una reunión de tres personas en que los buzones de dos participantes se marcan para la retención, se guardan los datos de la reunión a los buzones de esos dos participantes, pero no en el buzón del tercer participante, cuyo buzón no está en mantenga.</span><span class="sxs-lookup"><span data-stu-id="752ec-116">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="752ec-117">See also</span><span class="sxs-lookup"><span data-stu-id="752ec-117">Related topics</span></span>
[<span data-ttu-id="752ec-118">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="752ec-118">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="752ec-119">Transferencias de archivos punto a punto de bloque</span><span class="sxs-lookup"><span data-stu-id="752ec-119">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="752ec-120">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="752ec-120">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="752ec-121">Configurar directivas de la conferencia de la organización</span><span class="sxs-lookup"><span data-stu-id="752ec-121">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
## <a name="feedback"></a><span data-ttu-id="752ec-122">¿Comentarios?</span><span class="sxs-lookup"><span data-stu-id="752ec-122">Feedback?</span></span>
<span data-ttu-id="752ec-123">Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="752ec-123">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>