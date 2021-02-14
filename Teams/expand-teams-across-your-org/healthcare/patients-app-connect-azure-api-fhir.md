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
description: Obtenga información sobre cómo conectar la aplicación Pacientes en Microsoft Teams a la API de Azure para FLC (Fast Healthcare Interoperability Resources).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e41b071ef1724043f45c3783b062108d29a5190
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731158"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Conectar la aplicación Pacientes a la API de Azure para FHIR

> [!NOTE]
> A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y reemplazado por la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de grupo del grupo de Office 365 que copia de seguridad del equipo. Todos los datos asociados a la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas con la [aplicación Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Listas, los equipos de cuidado de su organización sanitaria pueden crear listas de pacientes para situaciones que van desde rounds y reuniones de equipo interdisciplinarias hasta la supervisión general del paciente. Consulte la plantilla Pacientes en Listas para empezar. Para obtener más información sobre cómo administrar la aplicación Listas de su organización, vea [Administrar la aplicación Listas.](../../manage-lists-app.md)

Siga estos pasos para permitir que la aplicación Pacientes de Microsoft Teams acceda a una instancia de la API de Azure para FLC. En este artículo se presupone que tiene una instancia de LA API de [Azure para F ALEXA](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada y configurada en su inquilino.  Si aún no ha creado una instancia de LA API de Azure para F HAVEN en su inquilino, consulte Inicio rápido: Implementar la API de Azure para [F EXPERIMENTAL con Azure Portal.](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)

1. Haga [clic aquí](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) para conceder el consentimiento del administrador para la aplicación Pacientes. Cuando se le solicite, inicie sesión con sus credenciales de administrador de inquilinos o de administrador global y, a continuación, haga clic en Aceptar **para** conceder los permisos necesarios.

    ![Captura de pantalla de la solicitud de permiso para la aplicación Pacientes](../../media/patients-app-permissions-request.png)

    Después de aceptar, cierre la ventana. Verá una página que puede tener este aspecto. Puede ignorar el mensaje de error en la página. Es inofensivo e indica que se concede consentimiento. (Estamos trabajando en una página más fácil de usar para esta dirección URL. ¡Permanezca atento!)

    ![Captura de pantalla de solicitud de permiso para la aplicación Pacientes](../../media/patients-app-permissions-request-granted.png)

2. Inicia sesión en [Azure Portal con](https://portal.azure.com) tus credenciales de administrador.

3. En el panel de navegación izquierdo, **seleccione Azure Active Directory** y, a continuación, seleccione Aplicaciones **empresariales.**

    Busque una fila denominada **Pacientes (desv)** y, a continuación, copie el valor de la columna **Id. de** objeto en el Portapapeles.

    ![Captura de pantalla de la fila Pacientes (desarrollo) en Azure Portal](../../media/patients-app-azure-portal-object-id.png)

4. Vaya a la instancia de recursos de la API de Azure para FCONTR a la que desea conectar la aplicación Pacientes (buscándolo o explorando sus recursos) y, a continuación, abra la configuración de esa instancia.

    ![Captura de pantalla de la configuración de instancias de API de Azure para FLC en Azure Portal](../../media/patients-app-azure-portal-instance-settings.png)

5. Haga **clic en** Autenticación y pegue el id. de objeto que copió en el paso 3 en el cuadro Id. de objeto **permitido.** Esto permite que la aplicación Pacientes acceda al servidor FCONTR. Después de pegar el id. de objeto, Azure Active Directory lo valida y aparece una marca de verificación verde junto a él.

    ![Captura de pantalla de la configuración de autenticación en Azure Portal](../../media/patients-app-azure-portal-authentication.png)

6. Haga clic en **Guardar**. Esto vuelve a implementar la instancia, que puede tardar unos minutos.

7. Haga clic **en Información** general y, a continuación, copie la dirección URL del extremo **de metadatos F EXTREMO.** Quite la etiqueta de metadatos para obtener la dirección URL del servidor FCONTR. Por ejemplo, `https://test02-teamshealth.azurehealthcareapis.com/` .

    ![el extremo de metadatos en Azure Portal](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. En Teams, vaya a la instancia de la aplicación Pacientes cargada en  su equipo, haga clic en Configuración **y,** a continuación, en el cuadro Vínculo, escriba la DIRECCIÓN URL del extremo del servidor F LDAP. A continuación, **haga clic en** Conectar para establecer una conexión y realizar búsquedas y agregar pacientes a la lista.  

    ![ Configuración de la aplicación Pacientes en Teams](../../media/patients-app-teams.png)

    Si recibe un error al conectarse a Teams durante este paso, envíe una captura de pantalla detallada del error, registros de [Fiddler](https://www.telerik.com/download/fiddler) y cualquier otro paso de reproducción en un correo electrónico con una línea de asunto de "Aplicación pacientes - Solución de problemas del modo TEAMSFORHEALTHCARE@SERVICE.MICROSOFT.COM" a [teamsforhealthcare@service.microsoft.com.](mailto:teamsforhealthcare@service.microsoft.com)

## <a name="related-topics"></a>Temas relacionados

- [Información general de la aplicación Pacientes](patients-app-overview.md)
- [Integración de registros sanitarios electrónicos en Microsoft Teams](patients-app.md)
