---
title: Experiencia de Teams en un entorno multilingüe habilitado de Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: En este artículo, obtendrá información sobre el uso de Teams en un entorno multilingüe habilitado de Microsoft 365.
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757755"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="6e693-103">Experiencia de Teams en un inquilino multilingüe habilitado en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6e693-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="6e693-104">Microsoft Teams es un software de chats grupales, el hub para el trabajo en equipo de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e693-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365.</span></span> <span data-ttu-id="6e693-105">Es alimentado por el servicio Microsoft 365 Groups, junto con SharePoint y OneDrive para la experiencia de los archivos.</span><span class="sxs-lookup"><span data-stu-id="6e693-105">It is powered by the Microsoft 365 Groups service along with SharePoint and OneDrive for its files experience.</span></span> <span data-ttu-id="6e693-106">En una organización multigeográfica en la que el inquilino se extiende a muchas ubicaciones geográficas, como América del norte, Europa y Australia, la experiencia de archivos subyacentes es la que tiene conciencia múltiple, por lo que la experiencia de los equipos con la colaboración de archivos también está preparada para varios países.</span><span class="sxs-lookup"><span data-stu-id="6e693-106">In a Multi-Geo organization in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="6e693-107">Esto permite a los equipos exponer archivos alojados en varias ubicaciones geográficas en la experiencia de los archivos nativos.</span><span class="sxs-lookup"><span data-stu-id="6e693-107">This allows Teams to surface files hosted across multiple geo locations in its native files experience.</span></span>

<span data-ttu-id="6e693-108">Por ejemplo, en una empresa de Contoso con Europa como una geo de satélite y Norteamérica como la geo central, un usuario de satélite europeo verá sus archivos de OneDrive en la pestaña archivos en el panel izquierdo, aunque los archivos se hospeden en la ubicación de datos de Europa y los Estados Unidos sean la ubicación central del inquilino.</span><span class="sxs-lookup"><span data-stu-id="6e693-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="6e693-109">Además, el usuario puede acceder a los archivos usados recientemente en el blade de la vista recientes.</span><span class="sxs-lookup"><span data-stu-id="6e693-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="6e693-110">Los archivos recientes pueden incluir archivos compartidos de usuarios en otras ubicaciones geográficas.</span><span class="sxs-lookup"><span data-stu-id="6e693-110">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="6e693-111">Un sitio de SharePoint de un equipo determinado también es compatible con multigeografía.</span><span class="sxs-lookup"><span data-stu-id="6e693-111">A given Team’s SharePoint site is also Multi-Geo aware.</span></span> <span data-ttu-id="6e693-112">Es decir, si un usuario satélite europeo está creando un equipo, el sitio de SharePoint correspondiente se creará en la ubicación Europa y los archivos asociados con ese equipo se mantendrán en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="6e693-112">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location and the files associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="6e693-113">Cualquier experiencia posterior, como cargar un archivo nuevo o editar el archivo, se almacenará en esa ubicación Europea, manteniendo la promesa de la residencia de datos para esos archivos.</span><span class="sxs-lookup"><span data-stu-id="6e693-113">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="6e693-114">Tenga en cuenta que las conversaciones en los chats y en las notas de mensajería instantánea de reuniones dentro de la experiencia de Teams no son muy importantes y se guardan solo dentro de la ubicación central de la organización.</span><span class="sxs-lookup"><span data-stu-id="6e693-114">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the organization.</span></span>

<span data-ttu-id="6e693-115">Para obtener más información sobre multi-Geo, vea [funciones multigeo de Microsoft](https://aka.ms/multi-geo).</span><span class="sxs-lookup"><span data-stu-id="6e693-115">For more information about Multi-Geo, see [Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span></span>
