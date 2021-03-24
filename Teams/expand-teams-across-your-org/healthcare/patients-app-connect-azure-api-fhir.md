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
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Conectar la aplicación Pacientes a la API de Azure para FHIR

> [!NOTE]
> Desde el 30 de octubre de 2020, la aplicación Pacientes se retiró y se reemplazó por la aplicación [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de correo del grupo de Office 365 que respalda al equipo. Todos los datos asociados con la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas mediante la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Listas, los equipos del cuidado de la salud de su organización sanitaria pueden crear listas de pacientes para escenarios que van desde guardias y reuniones interdisciplinarias de equipo, hasta el seguimiento general de pacientes. Consulte la plantilla Pacientes en Listas para comenzar. Para obtener más información sobre cómo administrar la aplicación Listas en su organización, consulte [Administrar la aplicación Listas](../../manage-lists-app.md).

Siga estos pasos para permitir que la aplicación Pacientes de Microsoft Teams acceda a una instancia de API de Azure para FHIR. En este artículo se presupone que tiene una instancia de API de [Azure para FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada y configurada en el espacio empresarial.  Si aún no ha creado una instancia de API de Azure para FHIR en su inquilino, vea Inicio rápido: Implementar la API de Azure para [FHIR con Azure Portal.](/azure/healthcare-apis/fhir-paas-portal-quickstart)

1. Haga [clic aquí](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) para conceder el consentimiento de administrador para la aplicación Pacientes. Cuando se le solicite, inicie sesión con sus credenciales de administrador de inquilinos o de administrador global y, a continuación, haga clic en Aceptar **para** conceder los permisos necesarios.

    ![Captura de pantalla de la solicitud de permiso para la aplicación Pacientes](../../media/patients-app-permissions-request.png)

    Después de aceptar, cierre la ventana. Verá una página que puede tener este aspecto. Puede ignorar el mensaje de error de la página. Es inofensivo e indica que se concede el consentimiento. (Estamos trabajando en una página más fácil de usar para esta dirección URL. ¡Manténgase atento!)

    ![Captura de pantalla de la solicitud de permiso para la aplicación Pacientes](../../media/patients-app-permissions-request-granted.png)

2. Inicie sesión en [Azure Portal con](https://portal.azure.com) sus credenciales de administrador.

3. En el panel de navegación izquierdo, **seleccione Azure Active Directory** y, a continuación, seleccione Aplicaciones **empresariales.**

    Busque una fila denominada **Pacientes (dev)** y, después, copie el valor de la columna **Id.** de objeto en el Portapapeles.

    ![Captura de pantalla de la fila Pacientes (dev) en Azure Portal](../../media/patients-app-azure-portal-object-id.png)

4. Vaya a la instancia de recursos de la API de Azure para FHIR a la que desea conectar la aplicación Pacientes (ya sea buscándolo o explorando sus recursos) y, a continuación, abra la configuración de esa instancia.

    ![Captura de pantalla de la configuración de instancia de La API de Azure para FHIR en Azure Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. Haga **clic en** Autenticación y, a continuación, pegue el id. de objeto que copió en el paso 3 en el cuadro Identificadores de objeto **permitidos.** Esto permite que la aplicación Pacientes acceda al servidor FHIR. Después de pegar el id. de objeto, Azure Active Directory lo valida y aparece una marca de verificación verde junto a él.

    ![Captura de pantalla de la configuración de autenticación en Azure Portal](../../media/patients-app-azure-portal-authentication.png)

6. Haga clic en **Guardar**. Esto vuelve a implementar la instancia, que puede tardar unos minutos.

7. Haga clic **en Información** general y, a continuación, copie la dirección URL del punto de conexión **de metadatos FHIR.** Quite la etiqueta de metadatos para obtener la dirección URL del servidor FHIR. Por ejemplo, `https://test02-teamshealth.azurehealthcareapis.com/` .

    ![el punto de conexión de metadatos en Azure Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. En Teams, vaya a la instancia de la aplicación Pacientes que se  carga en su equipo, haga clic en Configuración y, a continuación, en el cuadro Vínculo, escriba la dirección URL del punto de conexión del servidor FHIR. A continuación, **haga clic en Conectar** para establecer una conexión y buscar y agregar pacientes a la lista.  

    ![ Configuración de la aplicación Pacientes en Teams](../../media/patients-app-teams.png)

    Si recibe un error al conectarse a Teams durante este paso, envíe una captura de pantalla detallada del error, los registros de [Fiddler](https://www.telerik.com/download/fiddler) y cualquier otro paso de reprobación en un correo electrónico con una línea de asunto de "Aplicación para pacientes: solución de problemas del modo DER" a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).

## <a name="related-topics"></a>Temas relacionados

- [Información general de la aplicación Pacientes](patients-app-overview.md)
- [Integración de los registros sanitarios electrónicos en Microsoft Teams](patients-app.md)