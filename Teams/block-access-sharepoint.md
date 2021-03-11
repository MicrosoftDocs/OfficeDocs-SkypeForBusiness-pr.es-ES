---
title: Bloquear el acceso a SharePoint para determinados usuarios
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga más información sobre cómo bloquear el acceso a SharePoint para determinados usuarios
ms.openlocfilehash: e3cda9d6443c41abc7dfa736be03555690a3b0f1
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615086"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>Bloquear el acceso a SharePoint para determinados usuarios

Aplicar cualquier directiva de acceso condicional (CA) en SharePoint en Microsoft 365 también se aplica a Teams. Sin embargo, algunas organizaciones desean bloquear el acceso a los archivos de SharePoint (cargar, descargar, ver, editar, crear), pero permiten a sus empleados utilizar los clientes de escritorio, móviles y web de Teams en dispositivos no administrados. Bajo las reglas de la directiva de la CA, bloquear a SharePoint implicaría bloquear también a Teams. Este artículo explica cómo puede solucionar esta limitación y permitir que sus empleados sigan utilizando Teams mientras bloquean completamente el acceso a los archivos almacenados en SharePoint.

> [!Note]
> Bloquear o limitar el acceso a dispositivos no administrados se basa en directivas de acceso condicional de Azure AD. Obtenga información acerca de la [licencia Azure AD](https://azure.microsoft.com/pricing/details/active-directory/). Para una visión general del acceso condicional en Azure AD, vea [Acceso condicional en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Para obtener información sobre las directivas de acceso de SharePoint Online recomendadas, vea [recomendaciones de directiva para proteger los archivos y los sitios de SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies). Si limita el acceso a dispositivos no administrados, los usuarios de los dispositivos administrados deben usar uno de las [combinaciones compatibles de SO y navegadores](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition) o bien también tendrán acceso limitado.

Puede bloquear o limitar el acceso para:

- Usuarios de la organización o solo algunos usuarios o grupos de seguridad.

- Todos los sitios de la organización o solo algunos.

Cuando se bloquea el acceso, los usuarios verán un mensaje de error. Bloquear el acceso ayuda a proporcionar seguridad y protege los datos seguros. Cuando se bloquea el acceso, los usuarios verán un mensaje de error.

1. Abra el centro de administración de SharePoint.

2. Expanda **Directivas** > **Directivas de acceso**.

3. En la sección **Dispositivos sin administrar**, seleccione **Bloquear el acceso** y haga clic en **Guardar**.

   ![la sección de dispositivos sin administrar para directivas](media/no-sharepoint-access1.png)

4. Abra el portal de [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) y vaya a **Directivas de acceso condicional**.

    Verá que se ha creado una nueva directiva en SharePoint que es similar a la de este ejemplo:

    ![una nueva directiva que se denomina usar las restricciones de acceso de la aplicación para el explorador](media/no-sharepoint-access2.png)

5. Actualizar la directiva para que se destine unicamente a usuarios específicos o a un grupo.

    ![el centro de administración de SharePoint con la sección de selección de usuario resaltada.](media/no-sharepoint-access2b.png)

  > [!Note]
> Establecer esta directiva cortará su acceso al portal de administración de SharePoint. Recomendamos que configure la directiva de exclusión y seleccione los administradores globales y de SharePoint.

6. Comprobar que solo SharePoint está seleccionado como aplicación de nube de destino

    ![SharePoint se ha seleccionado como aplicación de destino.](media/no-sharepoint-access3.png)

7. Actualice las **Condiciones** para incluir también los clientes de escritorio.

    ![aplicaciones móviles y de escritorio resaltadas.](media/no-sharepoint-access4.png)

8. Asegúrese de que **Conceder acceso** está habilitado

    ![conceder acceso está habilitado.](media/no-sharepoint-access5.png)

9. Asegúrese de **Usar las restricciones que exige la aplicación** está habilitada.

10. Habilite la directiva y seleccione **Guardar**.

    ![Restricciones que exige la aplicación está habilitado.](media/no-sharepoint-access6.png)

Para probar su directiva, debe cerrar la sesión de cualquier cliente, como la aplicación de escritorio de Teams o el cliente de sincronización de OneDrive para la empresa e iniciar sesión de nuevo para ver cómo funciona la directiva. Si su acceso ha sido bloqueado, verá un mensaje en Teams que dice que el artículo podría no existir.

 ![Mensaje de articulo no encontrado.](media/access-denied-sharepoint.png)

En SharePoint, recibirá un mensaje de acceso denegado.

![Mensaje de error de acceso denegado](media/blocked-access-warning.png)

## <a name="related-topics"></a>Temas relacionados

[Controlar el acceso de los dispositivos no administrados en SharePoint](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
