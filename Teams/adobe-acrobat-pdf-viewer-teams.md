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
ms.openlocfilehash: 6a2e6c7ef80258ba07b3450ee983818f0b6ea6e1
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738776"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Adobe Acrobat como visor de PDF predeterminado en Microsoft Teams

> [!NOTE]
> Adobe Acrobat como experiencia de PDF predeterminada en Microsoft Teams solo está disponible actualmente en versión preliminar pública. Para usar esta funcionalidad, los administradores deben [habilitar la versión preliminar pública](public-preview-doc-updates.md#enable-public-preview) para su inquilino y asegurarse de que los usuarios finales cambien la versión de cliente de Teams a la versión preliminar pública.

Como administrador, puede establecer Adobe Acrobat como la aplicación predeterminada para ver y editar archivos PDF en Microsoft Teams. Los usuarios finales pueden ver, buscar, comentar y anotar archivos PDF sin una suscripción a Adobe Acrobat o un id. de Adobe.

Para configurar la aplicación Adobe Acrobat como el controlador predeterminado para los archivos PDF en el inquilino, complete los pasos siguientes como requisitos previos:

* [Permita la aplicación Adobe Acrobat](#allow-adobe-acrobat-app-in-your-tenant).
* [Instale la aplicación Adobe Acrobat](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>Permita la aplicación Adobe Acrobat en el inquilino

Antes de configurar la aplicación, asegúrese de que permite que las aplicaciones se usen en el inquilino, que ha permitido específicamente la aplicación Adobe Acrobat y que las directivas de permisos de la aplicación lo permiten. Para configurar Adobe Acrobat como la aplicación predeterminada para archivos PDF, siga estos pasos:

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

Si quieres permitir selectivamente la aplicación Adobe Acrobat para algunas personas o para un grupo, puedes asignar una [directiva personalizada para los permisos de las aplicaciones](teams-app-permission-policies.md).

## <a name="considerations-and-limitations"></a>Consideraciones y limitaciones

Conozca la siguiente información sobre esta funcionalidad:

* Una vez configurada la directiva, normalmente la aplicación [tarda unas horas](teams-app-setup-policies.md#considerations-and-limitations) en estar disponible para los usuarios.
* La visualización de archivos PDF anclados en canales como una pestaña y la visualización de archivos PDF en la aplicación Tareas sigue funcionando con la experiencia nativa de Teams.
* Adobe Acrobat como visor de PDF predeterminado en Teams solo funciona en clientes de escritorio y web. No se admite en el cliente móvil.
* Los usuarios necesitan un plan de Adobe Acrobat para usar las herramientas premium, como Exportar PDF, Organizar páginas, Combinar archivos, Comprimir PDF y Proteger PDF.
* Para desinstalar la aplicación, los usuarios finales pueden quitar la aplicación del cliente de Teams. El administrador puede quitar la aplicación Adobe Acrobat mediante la directiva de configuración.
* Si bloqueas la aplicación Adobe Acrobat, quita la aplicación de la directiva de configuración. Garantiza que la experiencia del usuario final revierta al uso del visor de archivos PDF nativo.
* Si tiene algún problema al iniciar sesión en la aplicación Adobe Acrobat en el cliente de escritorio de Teams, use [Teams en el explorador](https://teams.microsoft.com/) para iniciar sesión.
