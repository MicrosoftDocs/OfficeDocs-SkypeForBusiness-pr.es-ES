---
title: Adobe Acrobat como visor de PDF predeterminado en Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.subservice: teams-apps
ms.date: 09/25/2022
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Obtenga información sobre cómo establecer Adobe Acrobat como un visor de PDF predeterminado para ver y editar archivos PDF en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 44e96a11d2915c047c547f530b8f06afb45bd6bb
ms.sourcegitcommit: d95a3408e31d3dec37c534c110b09a8847bec724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2022
ms.locfileid: "69156906"
---
# <a name="set-adobe-acrobat-as-the-default-pdf-viewer-in-microsoft-teams"></a>Establecer Adobe Acrobat como visor de PDF predeterminado en Microsoft Teams

> [!NOTE]
> Adobe Acrobat como experiencia de PDF predeterminada en Microsoft Teams solo está disponible actualmente en versión preliminar pública. Para usar esta funcionalidad, los administradores deben [habilitar la versión preliminar pública](public-preview-doc-updates.md) para su inquilino y asegurarse de que los usuarios finales cambien la versión de cliente de Teams a la versión preliminar pública.

Como administrador, puede establecer Adobe Acrobat como la aplicación predeterminada para ver y editar archivos PDF en Microsoft Teams. Los usuarios finales pueden ver, buscar, comentar y anotar archivos PDF sin una suscripción a Adobe Acrobat o un id. de Adobe.

Para configurar la aplicación Adobe Acrobat como el controlador predeterminado para los archivos PDF en el inquilino, complete los pasos siguientes como requisitos previos:

* [Permita la aplicación Adobe Acrobat](#allow-adobe-acrobat-app-in-your-tenant).
* [Instale la aplicación Adobe Acrobat](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>Permita la aplicación Adobe Acrobat en el inquilino

Para configurar la aplicación como visor de PDF predeterminado, asegúrese de permitir que [se use la aplicación de terceros](manage-apps.md#manage-org-wide-app-settings) en su inquilino. A continuación, sigue las instrucciones siguientes para configurar Adobe Acrobat como la aplicación predeterminada para archivos PDF.

1. Inicie sesión en el Centro de administración de Teams y acceda a la aplicación  > **de Teams****[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Busque la aplicación Adobe Acrobat y selecciónela. Se abrirá la página de detalles de la aplicación.

1. Seleccione la pestaña **Permisos** y, a continuación, seleccione **Permiso de revisión**.

   :::image type="content" source="media/permission-policy.png" alt-text="Captura de pantalla del permiso de aplicación en el Centro de administración de Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Seleccione **Aceptar**.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Instale la aplicación Adobe Acrobat para todos los usuarios

Para asignar y hacer que la aplicación Adobe Acrobat esté disponible para todos los usuarios, siga estos pasos:

1. En el Centro de administración de Teams, vaya a **Aplicación de Teams** > [**Configurar directivas**](https://admin.teams.microsoft.com/policies/app-setup).

1. En la pestaña **Administrar directivas**, seleccione **Global (valor predeterminado para toda la organización)** y seleccione **Editar**.

   :::image type="content" source="media/setup-policies.png" alt-text="Captura de pantalla de las directivas de configuración de la aplicación Adobe Acrobat en el Centro de administración de Teams.":::

1. En la sección Aplicaciones instaladas, seleccione **Agregar aplicaciones**.

1. Busque **Adobe Acrobat**, seleccione **Agregar** junto al nombre de la aplicación y seleccione **Agregar**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Captura de pantalla que muestra cómo agregar la aplicación Adobe Acrobat para todos los usuarios." lightbox="media/add-adobe-acrobat-app.png":::

1. Seleccione **Guardar**.

Después de seleccionar Guardar, Teams usa la aplicación Adobe Acrobat como controlador de archivos predeterminado para los archivos PDF.

Si quieres permitir selectivamente la aplicación Adobe Acrobat para algunas personas o para un grupo, usas [directivas de permisos de aplicaciones](teams-app-permission-policies.md).

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones

Conozca la siguiente información sobre esta funcionalidad:

* Una vez configurada la directiva, normalmente la aplicación [tarda unas horas](teams-app-setup-policies.md#considerations-and-limitations) en estar disponible para los usuarios.
* La experiencia nativa en PDF de la aplicación Teams está disponible para ver los archivos PDF que están anclados en canales como una pestaña y están disponibles en la aplicación Tareas.
* Adobe Acrobat como visor de PDF predeterminado en Teams solo funciona en clientes de escritorio y web. No se admite en el cliente móvil.
* Los usuarios necesitan un plan de Adobe Acrobat para usar las herramientas premium, como Exportar PDF, Organizar páginas, Combinar archivos, Comprimir PDF y Proteger PDF.
* Para desinstalar la aplicación, los usuarios finales pueden quitar la aplicación de su cliente de Teams. Administración puede quitar la aplicación Adobe Acrobat mediante la directiva de configuración.
* Si bloqueas la aplicación Adobe Acrobat, quita la aplicación de la directiva de configuración. Garantiza que la experiencia del usuario final revierta al uso del visor de archivos PDF nativo.
* Si tiene problemas para iniciar sesión en la aplicación Adobe Acrobat en el cliente de escritorio de Teams, use [Teams en el explorador](https://teams.microsoft.com/) para iniciar sesión.
* Es necesario iniciar sesión en una [cuenta](https://acrobat.adobe.com/us/en/) gratuita de Adobe para comentar o realizar anotaciones en archivos PDF.
