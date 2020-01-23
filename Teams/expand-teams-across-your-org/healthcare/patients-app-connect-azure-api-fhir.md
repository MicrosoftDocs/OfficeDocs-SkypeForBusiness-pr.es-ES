---
title: Conectar la aplicación de pacientes a la API de Azure para FHIR
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Obtenga información sobre cómo conectar la aplicación de pacientes en Microsoft Teams a la API de Azure para FHIR (recursos de interoperabilidad de Fast Healthcare).
ms.openlocfilehash: e532aa9f9fbecb472db63a1ddad4cd71518a8041
ms.sourcegitcommit: d7fab927e96954f294f28dfb33c0889f736b3ab5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259151"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="eb39b-103">Conectar la aplicación de pacientes a la API de Azure para FHIR</span><span class="sxs-lookup"><span data-stu-id="eb39b-103">Connect the Patients app to Azure API for FHIR</span></span>

<span data-ttu-id="eb39b-104">Siga estos pasos para permitir que la aplicación de pacientes de Microsoft Teams acceda a una API de Azure para FHIR instancia.</span><span class="sxs-lookup"><span data-stu-id="eb39b-104">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="eb39b-105">En este artículo se da por hecho que tiene una [API de Azure para la instancia de FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="eb39b-105">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="eb39b-106">Si todavía no ha creado una API de Azure para FHIR instancia de su inquilino, consulte [Inicio rápido: implementar la API de Azure para FHIR con Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span><span class="sxs-lookup"><span data-stu-id="eb39b-106">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="eb39b-107">Haga clic [aquí](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) para conceder consentimiento de administrador a la aplicación pacientes.</span><span class="sxs-lookup"><span data-stu-id="eb39b-107">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="eb39b-108">Cuando se le solicite, inicie sesión con el administrador de inquilinos o las credenciales de administrador global y, a continuación, haga clic en **Aceptar** para conceder los permisos necesarios.</span><span class="sxs-lookup"><span data-stu-id="eb39b-108">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Captura de pantalla de solicitud de permiso de la aplicación para pacientes](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="eb39b-110">Después de aceptar, cierre la ventana.</span><span class="sxs-lookup"><span data-stu-id="eb39b-110">After you accept, close the window.</span></span> <span data-ttu-id="eb39b-111">Verá una página que puede tener el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="eb39b-111">You'll see a page that may look like this.</span></span> <span data-ttu-id="eb39b-112">Puede ignorar el mensaje de error en la página.</span><span class="sxs-lookup"><span data-stu-id="eb39b-112">You can ignore the error message on the page.</span></span> <span data-ttu-id="eb39b-113">Es inofensivo e indica que se concede el consentimiento.</span><span class="sxs-lookup"><span data-stu-id="eb39b-113">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="eb39b-114">(Estamos trabajando en una página más sencilla para esta dirección URL.</span><span class="sxs-lookup"><span data-stu-id="eb39b-114">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="eb39b-115">¡ Mantente atento!)</span><span class="sxs-lookup"><span data-stu-id="eb39b-115">Stay tuned!)</span></span>

    ![Captura de pantalla de solicitud de permiso de la aplicación para pacientes](../../media/patients-app-permissions-request-granted.png)
2. <span data-ttu-id="eb39b-117">Inicie sesión en el [portal de Azure](https://portal.azure.com) con sus credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="eb39b-117">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>
3. <span data-ttu-id="eb39b-118">En el navegación izquierdo, seleccione **Azure Active Directory**y, a continuación, seleccione **aplicaciones empresariales**.</span><span class="sxs-lookup"><span data-stu-id="eb39b-118">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>
    <span data-ttu-id="eb39b-119">Busque una fila denominada **patients (dev)** y, a continuación, copie el valor de la columna **Object ID** en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="eb39b-119">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>
    <span data-ttu-id="eb39b-120">![Captura de pantalla de la fila pacientes (dev) en Azure portal](../../media/patients-app-azure-portal-object-id.png)</span><span class="sxs-lookup"><span data-stu-id="eb39b-120">![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)</span></span>
4. <span data-ttu-id="eb39b-121">Vaya a la instancia de recursos de la API de Azure para FHIR a la que desea conectar la aplicación de pacientes (ya sea buscándola o desplazándose por los recursos) y, a continuación, abra la configuración de esa instancia.</span><span class="sxs-lookup"><span data-stu-id="eb39b-121">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Captura de pantalla de la configuración de la instancia de Azure API para FHIR en Azure portal](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="eb39b-123">Haga clic en **autenticación**y, a continuación, pegue el identificador de objeto que ha copiado en el paso 3 en el cuadro **identificadores de objeto permitidos** .</span><span class="sxs-lookup"><span data-stu-id="eb39b-123">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="eb39b-124">Esto permite a la aplicación de pacientes acceder al servidor de FHIR.</span><span class="sxs-lookup"><span data-stu-id="eb39b-124">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="eb39b-125">Después de pegar el identificador de objeto, Azure Active Directory lo valida y aparece una marca de verificación verde al lado.</span><span class="sxs-lookup"><span data-stu-id="eb39b-125">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Captura de pantalla de la configuración de autenticación en Azure portal](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="eb39b-127">Haga clic en \*\*Guardar \*\*.</span><span class="sxs-lookup"><span data-stu-id="eb39b-127">Click **Save**.</span></span> <span data-ttu-id="eb39b-128">Esto vuelve a implementar la instancia, lo que puede demorar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="eb39b-128">This redeploys the instance, which can take a few minutes.</span></span>
7. <span data-ttu-id="eb39b-129">Haga clic en **información general**y copie la dirección URL del **extremo de metadatos de FHIR**.</span><span class="sxs-lookup"><span data-stu-id="eb39b-129">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="eb39b-130">Quite la etiqueta metadata para obtener la dirección URL del servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="eb39b-130">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="eb39b-131">Por ejemplo, https://test02-teamshealth.azurehealthcareapis.com/.</span><span class="sxs-lookup"><span data-stu-id="eb39b-131">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Captura de pantalla del punto de conexión de metadatos en Azure portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="eb39b-133">En Teams, vaya a la instancia de la aplicación patients cargada en el equipo, haga clic en **configuración**y, a continuación, en el cuadro **vínculo** , escriba la dirección URL del extremo del servidor de FHIR.</span><span class="sxs-lookup"><span data-stu-id="eb39b-133">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="eb39b-134">Después, haga clic en **conectar** para establecer una conexión y buscar y agregar pacientes a la lista.</span><span class="sxs-lookup"><span data-stu-id="eb39b-134">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Captura de pantalla de la configuración de la aplicación pacientes en Teams](../../media/patients-app-teams.png)
    
    <span data-ttu-id="eb39b-136">Si recibe un error al conectar con Teams durante este paso, envíe una captura de pantalla detallada del error, los registros de [Fiddler](https://www.telerik.com/download/fiddler) y cualquier otro paso de reproducción en un correo electrónico con la línea de asunto "aplicación de pacientes – modo de EMR de solución de problemas" a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="eb39b-136">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="eb39b-137">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="eb39b-137">Related topics</span></span>

- [<span data-ttu-id="eb39b-138">Información general de la aplicación Pacientes</span><span class="sxs-lookup"><span data-stu-id="eb39b-138">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="eb39b-139">Integración de registros sanitarios electrónicos en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eb39b-139">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
