---
title: Bloquear el acceso a SharePoint para usuarios específicos
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
description: Obtener información sobre cómo bloquear el acceso a SharePoint para usuarios específicos
ms.openlocfilehash: 959de8c06e26d2d12c3a3698375b11d373392447
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956041"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>Bloquear el acceso a SharePoint para usuarios específicos

Aplicar cualquier directiva de acceso condicional en SharePoint Online (SPO) también se aplica a teams. Sin embargo, algunas organizaciones desean bloquear el acceso a los archivos de SharePoint (cargar, descargar, ver, editar, crear) y permitir que sus empleados usen equipos de escritorio, dispositivos móviles y clientes Web en dispositivos no administrados. En las reglas de directiva de la entidad emisora, el bloqueo de SPO también provocaría el bloqueo de Teams. En este artículo se explica cómo puede eludir esta limitación y permitir que los empleados sigan usando Teams mientras bloquean completamente el acceso a los archivos almacenados en SPO.

> [!Note]
> Bloquear o limitar el acceso a dispositivos no administrados depende de las directivas de acceso condicional de Azure AD. Más información sobre las [licencias de Azure ad](https://azure.microsoft.com/pricing/details/active-directory/). Para obtener información general sobre el acceso condicional en Azure AD, consulte [acceso condicional en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Para obtener información sobre las directivas de acceso de SharePoint recomendadas, consulte [recomendaciones de directiva para proteger los sitios y archivos de SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies). Si limita el acceso a los dispositivos no administrados, los usuarios de los dispositivos administrados deben usar una de las [combinaciones de sistema operativo y explorador compatibles](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), o bien también tendrán acceso limitado.

Puede bloquear o limitar el acceso a:

- Usuarios de la organización o solo algunos usuarios o grupos de seguridad.

- Todos los sitios de la organización o solo algunos sitios.

Cuando se bloquea el acceso, los usuarios verán un mensaje de error. Bloquear el acceso ayuda a proporcionar seguridad y protege los datos seguros. Cuando se bloquea el acceso, los usuarios verán un mensaje de error.

1. Abra el [centro de administración](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true)de SharePoint.

2. Expanda directivas de acceso de **directivas**  >  **Access Policies**.

3. En la sección **dispositivos no gestionados** , seleccione **Bloquear acceso** y seleccione **Guardar**.

   ![la sección de dispositivos no administrados para las directivas](media/no-sharepoint-access1.png)

4. Abra el portal de [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) y vaya a **directivas de acceso condicional**.

    Verá que SharePoint ha creado una nueva Directiva similar a este ejemplo:

    ![una nueva directiva que se denomina usar restricciones de aplicación de acceso para el explorador](media/no-sharepoint-access2.png)

5. Actualice la Directiva para destinar solo a usuarios específicos o a un grupo.

    ![el centro de administración de SharePoint con la sección seleccionar usuario resaltada.](media/no-sharepoint-access2b.png)

  > [!Note]
> Al configurar esta Directiva, se cortará el acceso al portal de administración de SharePoint. Le recomendamos que configure la Directiva de exclusión y seleccione los administradores globales y de SharePoint.

6. Comprobar que solo se selecciona SharePoint Online como aplicación de nube de destino

    ![SharePoint Online está seleccionado como la aplicación de destino.](media/no-sharepoint-access3.png)

7. Actualice **las condiciones** para incluir también los clientes de escritorio.

    ![aplicaciones móviles y de escritorio resaltadas.](media/no-sharepoint-access4.png)

8. Asegurarse de que **conceder acceso** está habilitado

    ![conceder acceso está habilitado.](media/no-sharepoint-access5.png)

9. Asegúrese de que está habilitada la opción **usar restricciones de aplicación** .

10. Habilite la Directiva y seleccione **Guardar**.

    ![Está habilitada la aplicación de restricciones obligatorias.](media/no-sharepoint-access6.png)

Para probar su Directiva, debe cerrar sesión en cualquier cliente, como la aplicación de escritorio de Teams o el cliente de sincronización de OneDrive, e iniciar sesión de nuevo para ver cómo funciona la Directiva. Si su acceso ha sido bloqueado, verá un mensaje en teams que indica que el elemento podría no existir.

 ![El mensaje de elemento no encontrado.](media/access-denied-sharepoint.png)

En SharePoint, recibirá un mensaje de acceso denegado. 

![El mensaje de acceso denegado.](media/blocked-access-warning.png)

## <a name="related-topics"></a>Temas relacionados

[Controlar el acceso a los dispositivos no administrados en SharePoint](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
