---
title: Configurar análisis de llamadas para Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configure análisis de llamadas por usuario para identificar y solucionar problemas Microsoft Teams de calidad de llamadas.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117138"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="d52be-103">Configurar análisis de llamadas para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d52be-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="d52be-104">Como administrador Microsoft Teams, puede usar el análisis de llamadas por usuario para solucionar Teams problemas de conexión y calidad de llamadas para **usuarios individuales.**</span><span class="sxs-lookup"><span data-stu-id="d52be-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="d52be-105">Para aprovechar al máximo el análisis de llamadas, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d52be-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="d52be-106">Asigne roles de soporte técnico especializados a personas, como agentes de soporte técnico, para que puedan ver análisis de llamadas para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d52be-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="d52be-107">Estos roles de soporte técnico no pueden tener acceso al resto del Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="d52be-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="d52be-108">Agregue información de creación, sitio e inquilino al análisis de llamadas por usuario cargando un archivo de datos .tsv o .csv de datos.</span><span class="sxs-lookup"><span data-stu-id="d52be-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="d52be-109">Cuando esté listo para empezar a usar el análisis de llamadas por usuario, lea Usar análisis de llamadas por usuario para solucionar problemas de mala calidad [de llamada.](use-call-analytics-to-troubleshoot-poor-call-quality.md)</span><span class="sxs-lookup"><span data-stu-id="d52be-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="d52be-110">Conceder permiso al personal de soporte técnico y soporte técnico</span><span class="sxs-lookup"><span data-stu-id="d52be-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="d52be-111">Como administrador Teams, tiene acceso completo a la información de análisis de llamadas para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d52be-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="d52be-112">Hemos creado algunos roles de Azure Active Directory especializados que puede asignar al personal de soporte técnico y a los agentes del departamento de soporte técnico para que también puedan acceder al análisis de llamadas por usuario (sin tener acceso al resto del centro de administración de Teams usuario).</span><span class="sxs-lookup"><span data-stu-id="d52be-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="d52be-113">Asigne el **Teams** de soporte técnico de comunicaciones a los usuarios que deben tener una vista limitada del análisis de llamadas por usuario (soporte técnico de nivel 1).</span><span class="sxs-lookup"><span data-stu-id="d52be-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="d52be-114">Asigne el **rol Teams** de ingeniero de soporte técnico de comunicaciones a los usuarios que necesiten acceso completo al análisis de llamadas por usuario (soporte técnico de nivel 2).</span><span class="sxs-lookup"><span data-stu-id="d52be-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="d52be-115">Ninguna de las dos funciones tiene acceso al resto del Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="d52be-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="d52be-116">Para obtener información sobre lo que hace cada uno de estos roles, lea ¿Qué hace [cada Teams rol de soporte técnico?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="d52be-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="d52be-117">Para obtener más información sobre Teams de administrador, vea Usar Teams [de administrador para administrar Teams](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d52be-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="d52be-118">Para obtener información sobre cómo asignar roles de administrador en Azure Active Directory, vea Ver [y asignar roles en Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="d52be-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="d52be-119">Para obtener información sobre cómo asignar roles administrativos en Azure Active Directory, vea Ver [y asignar roles en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="d52be-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="d52be-120">Upload un archivo .tsv o .csv para agregar información de edificio, sitio e inquilino</span><span class="sxs-lookup"><span data-stu-id="d52be-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="d52be-121">Puede agregar información de creación, sitio e inquilino al análisis de llamadas por usuario cargando un archivo .csv o .tsv.</span><span class="sxs-lookup"><span data-stu-id="d52be-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="d52be-122">Con toda esta información, el análisis de llamadas puede asignar direcciones IP a ubicaciones físicas.</span><span class="sxs-lookup"><span data-stu-id="d52be-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="d52be-123">Los administradores y agentes del departamento de soporte técnico pueden usar esta información para ayudar a detectar tendencias en problemas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d52be-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="d52be-124">Por ejemplo, ¿por qué los usuarios del mismo edificio tienen problemas similares de calidad de llamada?</span><span class="sxs-lookup"><span data-stu-id="d52be-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="d52be-125">Si es administrador de Teams o Skype Empresarial, puede usar un inquilino existente y crear un archivo de datos desde el panel de calidad de llamadas (CQD) de Teams o Skype Empresarial de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d52be-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="d52be-126">En primer lugar, descargue el archivo desde CQD y, a continuación, cargue el archivo en análisis de llamadas.</span><span class="sxs-lookup"><span data-stu-id="d52be-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="d52be-127">Para descargar un archivo de datos existente, vaya **Microsoft Teams** panel de calidad de llamadas del centro de  >    >  **administración Upload ahora**.</span><span class="sxs-lookup"><span data-stu-id="d52be-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="d52be-128">En la **lista Mis cargas,** haga clic **en Descargar** junto al archivo que desee.</span><span class="sxs-lookup"><span data-stu-id="d52be-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="d52be-129">Para cargar el nuevo archivo, vaya Microsoft Teams a Ubicaciones del centro de administración y, **a** continuación, seleccione Upload datos de ubicación o  >  Reemplazar datos de **ubicación.** </span><span class="sxs-lookup"><span data-stu-id="d52be-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="d52be-130">Si va a crear el archivo .tsv o .csv desde cero, vea Upload inquilino y [generar datos.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="d52be-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d52be-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d52be-131">Related topics</span></span>

[<span data-ttu-id="d52be-132">Usar análisis de llamadas por usuario para solucionar problemas de mala calidad de llamada</span><span class="sxs-lookup"><span data-stu-id="d52be-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="d52be-133">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="d52be-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)