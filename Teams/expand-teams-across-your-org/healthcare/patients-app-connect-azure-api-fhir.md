---
title: Conectar la aplicación Pacientes a la API de Azure para FHIR
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Obtenga información sobre cómo conectar la aplicación Pacientes de Microsoft Teams a la API de Azure para FHIR (Fast Healthcare Interoperability Resources).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096272"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="28935-103">Conectar la aplicación Pacientes a la API de Azure para FHIR</span><span class="sxs-lookup"><span data-stu-id="28935-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="28935-104">Desde el 30 de octubre de 2020, la aplicación Pacientes se retiró y se reemplazó por la aplicación [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams.</span><span class="sxs-lookup"><span data-stu-id="28935-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="28935-105">Los datos de la aplicación Pacientes se almacenan en el buzón de correo del grupo de Office 365 que respalda al equipo.</span><span class="sxs-lookup"><span data-stu-id="28935-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="28935-106">Todos los datos asociados con la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="28935-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="28935-107">Los usuarios pueden volver a crear sus listas mediante la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="28935-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="28935-108">Con Listas, los equipos del cuidado de la salud de su organización sanitaria pueden crear listas de pacientes para escenarios que van desde guardias y reuniones interdisciplinarias de equipo, hasta el seguimiento general de pacientes.</span><span class="sxs-lookup"><span data-stu-id="28935-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="28935-109">Consulte la plantilla Pacientes en Listas para comenzar.</span><span class="sxs-lookup"><span data-stu-id="28935-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="28935-110">Para obtener más información sobre cómo administrar la aplicación Listas en su organización, consulte [Administrar la aplicación Listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="28935-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="28935-111">Siga estos pasos para permitir que la aplicación Pacientes de Microsoft Teams acceda a una instancia de API de Azure para FHIR.</span><span class="sxs-lookup"><span data-stu-id="28935-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="28935-112">En este artículo se presupone que tiene una instancia de API de [Azure para FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada y configurada en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="28935-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="28935-113">Si aún no ha creado una instancia de API de Azure para FHIR en su inquilino, vea Inicio rápido: Implementar la API de Azure para [FHIR con Azure Portal.](/azure/healthcare-apis/fhir-paas-portal-quickstart)</span><span class="sxs-lookup"><span data-stu-id="28935-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="28935-114">Haga [clic aquí](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) para conceder el consentimiento de administrador para la aplicación Pacientes.</span><span class="sxs-lookup"><span data-stu-id="28935-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="28935-115">Cuando se le solicite, inicie sesión con sus credenciales de administrador de inquilinos o de administrador global y, a continuación, haga clic en Aceptar **para** conceder los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="28935-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Captura de pantalla de la solicitud de permiso para la aplicación Pacientes](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="28935-117">Después de aceptar, cierre la ventana.</span><span class="sxs-lookup"><span data-stu-id="28935-117">After you accept, close the window.</span></span> <span data-ttu-id="28935-118">Verá una página que puede tener este aspecto.</span><span class="sxs-lookup"><span data-stu-id="28935-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="28935-119">Puede ignorar el mensaje de error de la página.</span><span class="sxs-lookup"><span data-stu-id="28935-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="28935-120">Es inofensivo e indica que se concede el consentimiento.</span><span class="sxs-lookup"><span data-stu-id="28935-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="28935-121">(Estamos trabajando en una página más fácil de usar para esta dirección URL.</span><span class="sxs-lookup"><span data-stu-id="28935-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="28935-122">¡Manténgase atento!)</span><span class="sxs-lookup"><span data-stu-id="28935-122">Stay tuned!)</span></span>

    ![Captura de pantalla de la solicitud de permiso para la aplicación Pacientes](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="28935-124">Inicie sesión en [Azure Portal con](https://portal.azure.com) sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="28935-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="28935-125">En el panel de navegación izquierdo, **seleccione Azure Active Directory** y, a continuación, seleccione Aplicaciones **empresariales.**</span><span class="sxs-lookup"><span data-stu-id="28935-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="28935-126">Busque una fila denominada **Pacientes (dev)** y, después, copie el valor de la columna **Id.** de objeto en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="28935-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Captura de pantalla de la fila Pacientes (dev) en Azure Portal](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="28935-128">Vaya a la instancia de recursos de la API de Azure para FHIR a la que desea conectar la aplicación Pacientes (ya sea buscándolo o explorando sus recursos) y, a continuación, abra la configuración de esa instancia.</span><span class="sxs-lookup"><span data-stu-id="28935-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Captura de pantalla de la configuración de instancia de La API de Azure para FHIR en Azure Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="28935-130">Haga **clic en** Autenticación y, a continuación, pegue el id. de objeto que copió en el paso 3 en el cuadro Identificadores de objeto **permitidos.**</span><span class="sxs-lookup"><span data-stu-id="28935-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="28935-131">Esto permite que la aplicación Pacientes acceda al servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="28935-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="28935-132">Después de pegar el id. de objeto, Azure Active Directory lo valida y aparece una marca de verificación verde junto a él.</span><span class="sxs-lookup"><span data-stu-id="28935-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Captura de pantalla de la configuración de autenticación en Azure Portal](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="28935-134">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28935-134">Click **Save**.</span></span> <span data-ttu-id="28935-135">Esto vuelve a implementar la instancia, que puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="28935-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="28935-136">Haga clic **en Información** general y, a continuación, copie la dirección URL del punto de conexión **de metadatos FHIR.**</span><span class="sxs-lookup"><span data-stu-id="28935-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="28935-137">Quite la etiqueta de metadatos para obtener la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="28935-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="28935-138">Por ejemplo, `https://test02-teamshealth.azurehealthcareapis.com/` .</span><span class="sxs-lookup"><span data-stu-id="28935-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![el punto de conexión de metadatos en Azure Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="28935-140">En Teams, vaya a la instancia de la aplicación Pacientes que se  carga en su equipo, haga clic en Configuración y, a continuación, en el cuadro Vínculo, escriba la dirección URL del punto de conexión del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="28935-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="28935-141">A continuación, **haga clic en Conectar** para establecer una conexión y buscar y agregar pacientes a la lista.</span><span class="sxs-lookup"><span data-stu-id="28935-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="28935-142">Configuración de la aplicación Pacientes en Teams</span><span class="sxs-lookup"><span data-stu-id="28935-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="28935-143">Si recibe un error al conectarse a Teams durante este paso, envíe una captura de pantalla detallada del error, los registros de [Fiddler](https://www.telerik.com/download/fiddler) y cualquier otro paso de reprobación en un correo electrónico con una línea de asunto de "Aplicación para pacientes: solución de problemas del modo DER" a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="28935-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="28935-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="28935-144">Related topics</span></span>

- [<span data-ttu-id="28935-145">Información general de la aplicación Pacientes</span><span class="sxs-lookup"><span data-stu-id="28935-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="28935-146">Integración de los registros sanitarios electrónicos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28935-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)