---
title: Configurar análisis de llamadas para Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
description: Configure los análisis de llamadas por usuario para identificar y solucionar problemas de calidad de llamadas de Microsoft Teams.
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085316"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="3a429-103">Configurar análisis de llamadas para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3a429-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="3a429-104">Como administrador de Microsoft Teams, puede usar análisis de llamadas por usuario para solucionar problemas de calidad y problemas de conexión de **los equipos de los usuarios individuales**.</span><span class="sxs-lookup"><span data-stu-id="3a429-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="3a429-105">Para sacar el máximo provecho de los análisis de llamadas, configure lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3a429-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="3a429-106">Asigne roles de soporte técnico especializados a personas, como agentes de asistencia, para permitirles ver análisis de llamadas para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3a429-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="3a429-107">Estos roles de soporte no pueden acceder al resto del centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="3a429-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="3a429-108">Agregue información sobre edificios, sitios y espacios empresariales a análisis de llamadas por usuario al cargar un archivo de datos. TSV o. csv.</span><span class="sxs-lookup"><span data-stu-id="3a429-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="3a429-109">Cuando esté listo para empezar a usar análisis de llamadas por usuario, lea [usar análisis de llamadas por usuario para solucionar problemas de baja calidad de las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="3a429-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="3a429-110">Otorgar permiso al personal de soporte técnico y de asistencia</span><span class="sxs-lookup"><span data-stu-id="3a429-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="3a429-111">Como administrador de equipos, tiene acceso completo a información de análisis de llamadas para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3a429-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="3a429-112">Hemos creado algunos roles de Azure Active Directory especializados que puede asignar al personal de soporte técnico y a los agentes del Departamento de soporte técnico para que también puedan tener acceso al análisis de llamadas por usuario (sin tener acceso al resto del centro de administración de Teams).</span><span class="sxs-lookup"><span data-stu-id="3a429-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="3a429-113">Asigne el rol de **especialista de soporte de comunicaciones de Teams** a los usuarios que tengan una vista limitada de análisis de llamadas por usuario (soporte técnico de nivel 1).</span><span class="sxs-lookup"><span data-stu-id="3a429-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="3a429-114">Asigne el rol de **Ingeniero de soporte de comunicaciones de Teams** a los usuarios que necesiten acceso total a análisis de llamadas por usuario (soporte técnico de nivel 2).</span><span class="sxs-lookup"><span data-stu-id="3a429-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="3a429-115">Ninguna de las funciones tiene acceso al resto del centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="3a429-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="3a429-116">Para obtener información sobre lo que hace cada uno de estos roles, vea [¿Qué hace cada equipo con soporte técnico](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span><span class="sxs-lookup"><span data-stu-id="3a429-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="3a429-117">Para obtener más información sobre los roles de administrador de Teams, vea [usar roles de administrador de Teams para administrar equipos](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="3a429-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="3a429-118">Para obtener información sobre cómo asignar roles de administrador en Azure Active Directory, vea [ver y asignar roles en Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="3a429-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="3a429-119">Para obtener información sobre cómo asignar roles administrativos en Azure Active Directory, vea [ver y asignar roles en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="3a429-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="3a429-120">Cargar un archivo. TSV o. csv para agregar información de creación, sitio y espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="3a429-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="3a429-121">Puede agregar información de creación, sitio y espacio empresarial a análisis de llamadas por usuario al cargar un archivo. csv o. TSV.</span><span class="sxs-lookup"><span data-stu-id="3a429-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="3a429-122">Con toda esta información, el análisis de llamadas puede asignar direcciones IP a ubicaciones físicas.</span><span class="sxs-lookup"><span data-stu-id="3a429-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="3a429-123">Los administradores y los agentes del Departamento de soporte técnico pueden usar esta información para ayudar a detectar tendencias en problemas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3a429-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="3a429-124">Por ejemplo, ¿por qué los usuarios del mismo edificio tienen problemas similares con la calidad de las llamadas?</span><span class="sxs-lookup"><span data-stu-id="3a429-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="3a429-125">Si es un equipo de administración o un administrador de Skype empresarial, puede usar un inquilino existente y crear un archivo de datos de los equipos o del panel de calidad de llamadas de Skype empresarial (CQD).</span><span class="sxs-lookup"><span data-stu-id="3a429-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="3a429-126">En primer lugar, descargará el archivo desde el CQD y luego lo cargará en el análisis de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3a429-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="3a429-127">Para descargar un archivo de datos existente, vaya a la carga del panel de administración de llamadas de **Microsoft Teams**  >  **Call Quality Dashboard**  >  **Upload now**.</span><span class="sxs-lookup"><span data-stu-id="3a429-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="3a429-128">En la lista **mis cargas** , haga clic en **Descargar** junto al archivo que desee.</span><span class="sxs-lookup"><span data-stu-id="3a429-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="3a429-129">Para cargar el nuevo archivo, vaya a ubicaciones del **centro de administración de Microsoft Teams**  >  **Locations**y, a continuación, seleccione **cargar datos de ubicación** o **reemplazar datos de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="3a429-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="3a429-130">Si va a crear el archivo. TSV o. csv desde el principio, vea [cargar espacio empresarial y datos de compilación](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="3a429-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3a429-131">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3a429-131">Related topics</span></span>

[<span data-ttu-id="3a429-132">Usar análisis de llamadas por usuario para solucionar problemas de baja calidad de las llamadas</span><span class="sxs-lookup"><span data-stu-id="3a429-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="3a429-133">Solución de problemas de Teams</span><span class="sxs-lookup"><span data-stu-id="3a429-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
