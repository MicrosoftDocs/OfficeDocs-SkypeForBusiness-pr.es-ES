---
title: Conservar archivos de gran tamaño adjuntos a una reunión Skype Empresarial reunión
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
description: Puede adjuntar archivos a una reunión Skype Empresarial, que los participantes pueden abrir y descargar. Los archivos adjuntos Skype Empresarial las reuniones de Skype Empresarial se conservan en los buzones de cualquier participante cuyo buzón se coloca en retención por juicio, tiene una directiva de retención Microsoft 365 o Office 365 aplicada o se coloca en una retención asociada a un caso de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365. Este contenido se guarda en las carpetas Elementos recuperables de los participantes en sus buzones.
ms.openlocfilehash: 74605b9aebf6d83619282d9cfc9094216d2fe6f1
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240112"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a><span data-ttu-id="6d716-105">Conservar archivos de gran tamaño adjuntos a una reunión Skype Empresarial reunión</span><span class="sxs-lookup"><span data-stu-id="6d716-105">Retaining large files attached to a Skype for Business meeting</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="6d716-106">Puede adjuntar archivos a una reunión Skype Empresarial, que los participantes pueden abrir y descargar.</span><span class="sxs-lookup"><span data-stu-id="6d716-106">You can attach files to a Skype for Business meeting, which participants can then open and download.</span></span> <span data-ttu-id="6d716-107">Los archivos adjuntos Skype Empresarial las reuniones de Skype Empresarial se conservan en los buzones de cualquier participante cuyo buzón se coloca en retención por juicio, tiene una directiva de retención Microsoft 365 o Office 365 aplicada o se coloca en una retención asociada a un caso de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d716-107">Files attached to Skype for Business meetings are retained in the mailboxes of any participant whose mailbox is placed on Litigation Hold, has a Microsoft 365 or Office 365 retention policy applied, or is placed on a hold associated with an eDiscovery case in the Microsoft 365 Compliance Center.</span></span> <span data-ttu-id="6d716-108">Este contenido se guarda en las carpetas Elementos **recuperables** de los participantes en sus buzones.</span><span class="sxs-lookup"><span data-stu-id="6d716-108">This content is saved to participants' **Recoverable Items** folders in their mailboxes.</span></span>
  
<span data-ttu-id="6d716-109">Los archivos que se conservan en buzones en espera se indexa y, por lo tanto, se pueden buscar al ejecutar una búsqueda de contenido en el Centro de cumplimiento de seguridad al buscar en el buzón de un &amp; participante.</span><span class="sxs-lookup"><span data-stu-id="6d716-109">Files that are retained in mailboxes on hold are indexed and can therefore be searched when running a Content Search in the Security &amp; Compliance Center when searching a participant's mailbox.</span></span> <span data-ttu-id="6d716-110">Sin embargo, los archivos adjuntos de más de 30 MB se dividen en dos o más archivos más pequeños y se guardan como archivos comprimidos (.zip).</span><span class="sxs-lookup"><span data-stu-id="6d716-110">However, attached files that are larger than 30 MB are split into two or more smaller files and saved as compressed (.zip) files.</span></span> <span data-ttu-id="6d716-111">El  *contenido*  de estos archivos más pequeños no se indexa para la búsqueda y es posible que no se devuelva en una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="6d716-111">The  *content*  of these smaller files is not indexed for search and might not be returned in a Content Search.</span></span> <span data-ttu-id="6d716-112">Sin embargo, *los metadatos*  de estos archivos (como el nombre de archivo y el autor) se indexan para la búsqueda y pueden devolverse en una búsqueda de contenido.</span><span class="sxs-lookup"><span data-stu-id="6d716-112">However, the *metadata*  of these files (such as the file name and author) is indexed for search and might be returned in a Content Search.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6d716-113">La configuración MaxReceiveSize y MaxSendSize para un buzón de Exchange Online puede afectar a la capacidad de retener archivos grandes de Skype Empresarial reuniones.</span><span class="sxs-lookup"><span data-stu-id="6d716-113">The MaxReceiveSize and MaxSendSize settings for an Exchange Online mailbox can affect the ability to retain large files from Skype for Business meetings.</span></span> <span data-ttu-id="6d716-114">La configuración predeterminada de MaxReceiveSize y MaxSendSize es de 36 MB y 35 MB, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6d716-114">The default settings for MaxReceiveSize and MaxSendSize are 36 MB and 35 MB, respectively.</span></span> <span data-ttu-id="6d716-115">Sin embargo, esta configuración predeterminada es demasiado pequeña para conservar cualquier archivo de una reunión Skype Empresarial que sea superior a 30 MB.</span><span class="sxs-lookup"><span data-stu-id="6d716-115">However, these default settings are too small to retain any file from a Skype for Business meeting that's larger than 30 MB.</span></span> <span data-ttu-id="6d716-116">Esto se debe a Exchange Online codificación Base64 de datos adjuntos de mensajes y otros datos binarios.</span><span class="sxs-lookup"><span data-stu-id="6d716-116">This is because Exchange Online uses Base64 encoding of message attachments and other binary data.</span></span> <span data-ttu-id="6d716-117">Cuando se codifica un mensaje, su tamaño aumenta aproximadamente un 33 %.</span><span class="sxs-lookup"><span data-stu-id="6d716-117">When a message is encoded, its size is increased by approximately 33%.</span></span> <span data-ttu-id="6d716-118">Por lo tanto, para asegurarse de que se conservan archivos grandes de reuniones de Skype Empresarial, le recomendamos que aumente el valor de MaxReceiveSize y MaxSendSize a 39 MB (que es aproximadamente un 33 % mayor que el límite de tamaño de 30 MB que se explicó anteriormente) para los usuarios que se encuentran en espera.</span><span class="sxs-lookup"><span data-stu-id="6d716-118">Therefore, to ensure that large files from Skype for Business meetings are retained, we recommend that you increase the value for both MaxReceiveSize and MaxSendSize to 39 MB (which is approximately 33% larger than the 30 MB size limit that was previously explained) for users who are placed on hold.</span></span> <span data-ttu-id="6d716-119">En caso contrario, es posible que no se conserve un archivo grande adjunto a Skype Empresarial reunión.</span><span class="sxs-lookup"><span data-stu-id="6d716-119">Otherwise, a large file attached to a Skype for Business meeting might not be retained.</span></span> <span data-ttu-id="6d716-120">Para obtener más información sobre el uso de los comandos **Set-Mailbox -MaxReceiveSize** y **Set-Mailbox -MaxSendSize** en Exchange Online PowerShell, vea [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).</span><span class="sxs-lookup"><span data-stu-id="6d716-120">For more information  about using the **Set-Mailbox -MaxReceiveSize** and **Set-Mailbox -MaxSendSize** commands in Exchange Online PowerShell, see [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).</span></span>
  
<span data-ttu-id="6d716-121">Los buzones que no estén en espera no tendrán ningún dato de reunión guardado.</span><span class="sxs-lookup"><span data-stu-id="6d716-121">Mailboxes that are not on hold will not have any meeting data saved.</span></span> <span data-ttu-id="6d716-122">Por ejemplo, en una reunión de tres personas en la que los buzones de dos participantes están marcados para la retención, los datos de la reunión se guardan en los buzones de esos dos participantes, pero no en el buzón del tercer participante, cuyo buzón no está en espera.</span><span class="sxs-lookup"><span data-stu-id="6d716-122">For example, in a three-person meeting in which the mailboxes of two participants are marked for retention, the meeting data is saved to the mailboxes of those two participants, but not to the mailbox of the third participant, whose mailbox is not on hold.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6d716-123">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6d716-123">Related topics</span></span>
[<span data-ttu-id="6d716-124">Crear directivas personalizadas de acceso externo</span><span class="sxs-lookup"><span data-stu-id="6d716-124">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="6d716-125">Bloquear las transferencias de archivos punto a punto</span><span class="sxs-lookup"><span data-stu-id="6d716-125">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="6d716-126">Establecer directivas de cliente en su organización</span><span class="sxs-lookup"><span data-stu-id="6d716-126">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="6d716-127">Configurar directivas de conferencia en su organización</span><span class="sxs-lookup"><span data-stu-id="6d716-127">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)
  
  
