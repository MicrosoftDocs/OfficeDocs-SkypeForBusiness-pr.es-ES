---
title: Configurar la administración para aplicaciones en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Aprenda a permitir y habilitar aplicaciones en Microsoft Teams, incluida la carga lateral de aplicaciones externas.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 82cd2de00fe053fb7255c7e4a692e1e85a8b1fe6
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "19106493"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a>Configurar la administración para aplicaciones en Microsoft Teams
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Aplicaciones son las fichas, conectores, bots o cualquier combinación de estos tres, proporcionada por un servicio de terceros. Existen las directivas de administración de los equipos que se pueden configurar en el centro de administración de Office 365 para controlar qué aplicaciones de otros fabricantes externos están permitidas. Estas directivas le permiten especificar qué aplicaciones están permitidos y no permitidos, nuevo comportamiento de la aplicación externa, y si se permite la carga de lado aplicaciones.

> [!NOTE]
> Para ajustar la configuración de la administración de aplicaciones en Microsoft Teams, vaya al Centro de administración de Office 365, abra **Configuración** > **Servicios y complementos**, y seleccione **Microsoft Teams**. Si ha iniciado sesión como administrador de Office 365, puede acceder con este vínculo:
> 
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns 

Si desea más información sobre la configuración de administrador para las aplicaciones, consulte el siguiente vídeo: 
 
|  |  |
|---------|---------|
| Administrar la experiencia de aplicaciones en Microsoft Teams   | <iframe width="350" height="200" src="https://www.youtube.com/embed/CHnpw1O7EgM" frameborder="0" allowfullscreen></iframe>     | 

## <a name="allow-external-apps-in-teams"></a>Permitir aplicaciones externas en Microsoft Teams

De manera predeterminada, la opción **Permitir aplicaciones externas en Microsoft Teams** está activada con todas las aplicaciones seleccionadas.  Si desactiva este conmutador, se desactivarán todas las aplicaciones externas de terceros. 

## <a name="enable-new-external-apps-by-default"></a>Habilitar nuevas aplicaciones externas de manera predeterminada

#### <a name="trophy-best-practice-manage-external-apps-individually"></a>:trophy: Procedimiento recomendado: Administrar las aplicaciones externas de forma individual 
 
Para activar algunas aplicaciones (y desactivar otras), desactive **Permitir la instalación de prueba de aplicaciones externas**. A continuación, desactive las aplicaciones que no quiera que usen los usuarios. Opcional: Desactive **Habilitar nuevas aplicaciones externas de manera predeterminada** (si desea controlar las nuevas aplicaciones). 

> [!NOTE]
> Aplicaciones predeterminadas, como los creados por Microsoft, no se ven afectadas por la configuración de **Habilitar las nuevas aplicaciones externas de forma predeterminada** . Nuevas aplicaciones están habilitadas de forma predeterminada cuando publicadas por Microsoft.

Cuando este conmutador está activado, los usuarios pueden activar nuevas aplicaciones en cuanto estas se agregan al catálogo de aplicaciones de Microsoft Teams. Para abrir el catálogo de aplicaciones de Microsoft Teams, haga clic en **Tienda** en la parte inferior de Microsoft Teams y después en **Aplicaciones**. Si desea controlar qué aplicaciones están disponibles, desactive este conmutador. Si lo desactiva, deberá recordar revisar periódicamente las nuevas incorporaciones para que su organización no se pierda las nuevas aplicaciones de interés. 

La instalación de prueba es la forma en que se agrega una aplicación a Microsoft Teams mediante la carga de un archivo zip directamente a un equipo. La instalación de prueba le permite probar una aplicación en fase de desarrollo. También le permite crear una aplicación solo para el uso interno y compartirla con su equipo sin enviarla al catálogo de aplicaciones de Microsoft Teams en la Tienda Office. 

La instalación de prueba de aplicaciones en Microsoft Teams la pueden realizar únicamente los propietarios del equipo o los miembros con los permisos adecuados.  

![Captura de pantalla de la sección aplicaciones expandida en configuración de todo el inquilino.](media/Admin_settings_for_apps_in_Microsoft_Teams_image2.png)

## <a name="creating-and-uploading-app-packages"></a>Crear y cargar paquetes de aplicaciones 

Para obtener más información acerca de las aplicaciones, vea [desarrollar aplicaciones para los equipos](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-overview). 



