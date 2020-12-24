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
description: Obtenga información sobre cómo conectar la aplicación de pacientes en Microsoft Teams a la API de Azure para FHIR (recursos de interoperabilidad de Fast Healthcare).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e41b071ef1724043f45c3783b062108d29a5190
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731158"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="4ecc3-103">Conectar la aplicación Pacientes a la API de Azure para FHIR</span><span class="sxs-lookup"><span data-stu-id="4ecc3-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="4ecc3-104">Desde el 30 de octubre de 2020, la aplicación de pacientes se ha retirado y se ha sustituido por la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="4ecc3-105">Los datos de la aplicación patients se almacenan en el buzón de grupo del grupo Office 365 que respalda al equipo.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="4ecc3-106">Todos los datos asociados con la aplicación patients se conservan en este grupo, pero ya no se puede obtener acceso a ellos a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="4ecc3-107">Los usuarios pueden volver a crear sus listas con la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="4ecc3-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="4ecc3-108">Con las listas, los equipos de cuidados de la organización de la salud pueden crear listas de pacientes para escenarios que abarcan desde rondas y reuniones interdisciplinarias hasta supervisión general de pacientes.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="4ecc3-109">Consulte la plantilla patients en listas para comenzar.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="4ecc3-110">Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="4ecc3-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="4ecc3-111">Siga estos pasos para permitir que la aplicación de pacientes de Microsoft Teams acceda a una API de Azure para FHIR instancia.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="4ecc3-112">En este artículo se da por hecho que tiene una [API de Azure para la instancia de FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="4ecc3-113">Si todavía no ha creado una API de Azure para FHIR instancia de su inquilino, consulte [Inicio rápido: implementar la API de Azure para FHIR con Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span><span class="sxs-lookup"><span data-stu-id="4ecc3-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="4ecc3-114">Haga clic [aquí](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) para conceder consentimiento de administrador a la aplicación pacientes.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="4ecc3-115">Cuando se le solicite, inicie sesión con el administrador de inquilinos o las credenciales de administrador global y, a continuación, haga clic en **Aceptar** para conceder los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Captura de pantalla de la solicitud de permiso para la aplicación pacientes](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="4ecc3-117">Después de aceptar, cierre la ventana.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-117">After you accept, close the window.</span></span> <span data-ttu-id="4ecc3-118">Verá una página que puede tener el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="4ecc3-119">Puede ignorar el mensaje de error en la página.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="4ecc3-120">Es inofensivo e indica que se concede el consentimiento.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="4ecc3-121">(Estamos trabajando en una página más sencilla para esta dirección URL.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="4ecc3-122">¡ Mantente atento!)</span><span class="sxs-lookup"><span data-stu-id="4ecc3-122">Stay tuned!)</span></span>

    ![Captura de pantalla de solicitud de permiso de la aplicación para pacientes](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="4ecc3-124">Inicie sesión en el [portal de Azure](https://portal.azure.com) con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="4ecc3-125">En el navegación izquierdo, seleccione **Azure Active Directory** y, a continuación, seleccione **aplicaciones empresariales**.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="4ecc3-126">Busque una fila denominada **patients (dev)** y, a continuación, copie el valor de la columna **Object ID** en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Captura de pantalla de la fila pacientes (dev) en Azure portal](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="4ecc3-128">Vaya a la instancia de recursos de la API de Azure para FHIR a la que desea conectar la aplicación de pacientes (ya sea buscándola o desplazándose por los recursos) y, a continuación, abra la configuración de esa instancia.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Captura de pantalla de la configuración de la instancia de Azure API para FHIR en Azure portal](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="4ecc3-130">Haga clic en **autenticación** y, a continuación, pegue el identificador de objeto que ha copiado en el paso 3 en el cuadro **identificadores de objeto permitidos** .</span><span class="sxs-lookup"><span data-stu-id="4ecc3-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="4ecc3-131">Esto permite a la aplicación de pacientes acceder al servidor de FHIR.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="4ecc3-132">Después de pegar el identificador de objeto, Azure Active Directory lo valida y aparece una marca de verificación verde al lado.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Captura de pantalla de la configuración de autenticación en Azure portal](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="4ecc3-134">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-134">Click **Save**.</span></span> <span data-ttu-id="4ecc3-135">Esto vuelve a implementar la instancia, lo que puede demorar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="4ecc3-136">Haga clic en **información general** y copie la dirección URL del **extremo de metadatos de FHIR**.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="4ecc3-137">Quite la etiqueta metadata para obtener la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="4ecc3-138">Por ejemplo, `https://test02-teamshealth.azurehealthcareapis.com/` .</span><span class="sxs-lookup"><span data-stu-id="4ecc3-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![punto final de metadatos en Azure portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="4ecc3-140">En Teams, vaya a la instancia de la aplicación patients cargada en el equipo, haga clic en **configuración** y, a continuación, en el cuadro **vínculo** , escriba la dirección URL del extremo del servidor de FHIR.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="4ecc3-141">Después, haga clic en **conectar** para establecer una conexión y buscar y agregar pacientes a la lista.</span><span class="sxs-lookup"><span data-stu-id="4ecc3-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="4ecc3-142">Configuración de la aplicación de pacientes en Teams</span><span class="sxs-lookup"><span data-stu-id="4ecc3-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="4ecc3-143">Si recibe un error al conectar con Teams durante este paso, envíe una captura de pantalla detallada del error, los registros de [Fiddler](https://www.telerik.com/download/fiddler) y cualquier otro paso de reproducción en un correo electrónico con la línea de asunto "aplicación de pacientes – modo de EMR de solución de problemas" a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="4ecc3-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4ecc3-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4ecc3-144">Related topics</span></span>

- [<span data-ttu-id="4ecc3-145">Información general de la aplicación Pacientes</span><span class="sxs-lookup"><span data-stu-id="4ecc3-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="4ecc3-146">Integración de registros sanitarios electrónicos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ecc3-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
