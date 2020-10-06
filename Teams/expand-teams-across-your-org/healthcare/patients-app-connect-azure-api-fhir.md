---
title: Conectar la aplicación Pacientes a la API de Azure para FHIR
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 0a763c2d7bc37f8633d3fd9051d7f08cf15be5a8
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361490"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Conectar la aplicación Pacientes a la API de Azure para FHIR

> [!IMPORTANT]
> **A partir del 15 de octubre de 2020, la aplicación para pacientes quedará obsoleta y los usuarios ya no podrán instalarla desde la tienda de aplicaciones de Teams. Le recomendamos que empiece a usar la [aplicación lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams hoy.**
>
>Los datos de la aplicación patients se almacenan en el buzón de grupo del grupo Office 365 que respalda al equipo. Cuando se retira la aplicación de pacientes, todos los datos asociados con ella se conservarán en este grupo, pero ya no se podrá obtener acceso a ellas a través de la interfaz de usuario. Los usuarios actuales pueden volver a crear sus listas con la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>La [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) está preinstalada para todos los usuarios de Teams y está disponible como una pestaña en todos los equipos y canales. Con las listas, los equipos de cuidados pueden crear listas de pacientes con la plantilla de pacientes integrados, desde cero o importando datos a Excel. Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md).

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
7. Haga clic en **información general**y copie la dirección URL del **extremo de metadatos de FHIR**. Quite la etiqueta metadata para obtener la dirección URL del servidor FHIR. Por ejemplo, https://test02-teamshealth.azurehealthcareapis.com/ . 

    ![Captura de pantalla del punto de conexión de metadatos en Azure portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. En Teams, vaya a la instancia de la aplicación patients cargada en el equipo, haga clic en **configuración**y, a continuación, en el cuadro **vínculo** , escriba la dirección URL del extremo del servidor de FHIR. Después, haga clic en **conectar** para establecer una conexión y buscar y agregar pacientes a la lista.  

    ![Captura de pantalla de la configuración de la aplicación pacientes en Teams](../../media/patients-app-teams.png)
    
    Si recibe un error al conectar con Teams durante este paso, envíe una captura de pantalla detallada del error, los registros de [Fiddler](https://www.telerik.com/download/fiddler) y cualquier otro paso de reproducción en un correo electrónico con la línea de asunto "aplicación de pacientes – modo de EMR de solución de problemas" a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).

## <a name="related-topics"></a>Temas relacionados

- [Información general de la aplicación Pacientes](patients-app-overview.md)
- [Integración de registros sanitarios electrónicos en Microsoft Teams](patients-app.md)
