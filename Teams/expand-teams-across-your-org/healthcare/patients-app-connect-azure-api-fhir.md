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
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Conectar la aplicación de pacientes a la API de Azure para FHIR

Siga estos pasos para permitir que la aplicación de pacientes de Microsoft Teams acceda a una API de Azure para FHIR instancia. En este artículo se da por hecho que tiene una [API de Azure para la instancia de FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada en su espacio empresarial.  Si todavía no ha creado una API de Azure para FHIR instancia de su inquilino, consulte [Inicio rápido: implementar la API de Azure para FHIR con Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).


1. Haga clic [aquí](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) para conceder consentimiento de administrador a la aplicación pacientes. Cuando se le solicite, inicie sesión con el administrador de inquilinos o las credenciales de administrador global y, a continuación, haga clic en **Aceptar** para conceder los permisos necesarios.

    ![Captura de pantalla de solicitud de permiso de la aplicación para pacientes](../../media/patients-app-permissions-request.png)

    Después de aceptar, cierre la ventana. Verá una página que puede tener el siguiente aspecto. Puede ignorar el mensaje de error en la página. Es inofensivo e indica que se concede el consentimiento. (Estamos trabajando en una página más sencilla para esta dirección URL. ¡ Mantente atento!)

    ![Captura de pantalla de solicitud de permiso de la aplicación para pacientes](../../media/patients-app-permissions-request-granted.png)
2. Inicie sesión en el [portal de Azure](https://portal.azure.com) con sus credenciales de administrador.
3. En el navegación izquierdo, seleccione **Azure Active Directory**y, a continuación, seleccione **aplicaciones empresariales**.
    Busque una fila denominada **patients (dev)** y, a continuación, copie el valor de la columna **Object ID** en el portapapeles.
    ![Captura de pantalla de la fila pacientes (dev) en Azure portal](../../media/patients-app-azure-portal-object-id.png)
4. Vaya a la instancia de recursos de la API de Azure para FHIR a la que desea conectar la aplicación de pacientes (ya sea buscándola o desplazándose por los recursos) y, a continuación, abra la configuración de esa instancia.

    ![Captura de pantalla de la configuración de la instancia de Azure API para FHIR en Azure portal](../../media/patients-app-azure-portal-instance-settings.png)

5. Haga clic en **autenticación**y, a continuación, pegue el identificador de objeto que ha copiado en el paso 3 en el cuadro **identificadores de objeto permitidos** . Esto permite a la aplicación de pacientes acceder al servidor de FHIR. Después de pegar el identificador de objeto, Azure Active Directory lo valida y aparece una marca de verificación verde al lado.

    ![Captura de pantalla de la configuración de autenticación en Azure portal](../../media/patients-app-azure-portal-authentication.png)

6. Haga clic en **Guardar **. Esto vuelve a implementar la instancia, lo que puede demorar unos minutos.
7. Haga clic en **información general**y copie la dirección URL del **extremo de metadatos de FHIR**. Quite la etiqueta metadata para obtener la dirección URL del servidor FHIR. Por ejemplo, https://test02-teamshealth.azurehealthcareapis.com/. 

    ![Captura de pantalla del punto de conexión de metadatos en Azure portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. En Teams, vaya a la instancia de la aplicación patients cargada en el equipo, haga clic en **configuración**y, a continuación, en el cuadro **vínculo** , escriba la dirección URL del extremo del servidor de FHIR. Después, haga clic en **conectar** para establecer una conexión y buscar y agregar pacientes a la lista.  

    ![Captura de pantalla de la configuración de la aplicación pacientes en Teams](../../media/patients-app-teams.png)
    
    Si recibe un error al conectar con Teams durante este paso, envíe una captura de pantalla detallada del error, los registros de [Fiddler](https://www.telerik.com/download/fiddler) y cualquier otro paso de reproducción en un correo electrónico con la línea de asunto "aplicación de pacientes – modo de EMR de solución de problemas" a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).

## <a name="related-topics"></a>Temas relacionados

- [Información general de la aplicación Pacientes](patients-app-overview.md)
- [Integración de registros sanitarios electrónicos en Microsoft Teams](patients-app.md)
