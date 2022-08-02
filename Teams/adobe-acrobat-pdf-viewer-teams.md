---
title: Adobe Acrobat como visor de PDF predeterminado en Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Obtenga información sobre cómo configurar Adobe Acrobat como visor de PDF predeterminado para ver y editar archivos PDF en Microsoft Teams.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 913081ee0efc87d66ed304f3de5e9f00b69232fa
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156748"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-microsoft-teams"></a>Adobe Acrobat como visor de PDF predeterminado en Microsoft Teams

> [!NOTE]
> Adobe Acrobat como experiencia de PDF predeterminada en Microsoft Teams solo está disponible actualmente en la versión preliminar pública. Para usar esta funcionalidad, los administradores deben [habilitar la versión preliminar pública](public-preview-doc-updates.md#enable-public-preview) para su inquilino y asegurarse de que los usuarios finales cambien la versión del cliente de Teams a una versión preliminar pública.

Como administrador, puede establecer Adobe Acrobat como la aplicación predeterminada para ver y editar archivos PDF en Microsoft Teams. Los usuarios finales pueden ver, buscar, comentar y anotar archivos PDF sin una suscripción a Adobe Acrobat o un Adobe ID.

## <a name="set-up-adobe-acrobat-app"></a>Configurar la aplicación Adobe Acrobat

Antes de configurar la aplicación, asegúrate de permitir el uso de aplicaciones en tu espacio empresarial, de que has permitido específicamente la aplicación Adobe Acrobat y de que las directivas de permisos de las aplicaciones lo permitan. Para configurar Adobe Acrobat como la aplicación predeterminada para archivos PDF, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y vaya a **La aplicación** >  de Teams **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Busca la aplicación Adobe Acrobat y selecciónala.

1. En la pestaña **Permisos** , seleccione **Revisar permiso**.

   :::image type="content" source="media/permission-policy.png" alt-text="Captura de pantalla de permisos de aplicaciones en el Centro de administración de Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. Seleccione **Aceptar**.

## <a name="install-adobe-acrobat-app-for-all-users"></a>Instalar la aplicación Adobe Acrobat para todos los usuarios

Para asignar y hacer que la aplicación Adobe Acrobat esté disponible para todos los usuarios, siga estos pasos:

1. En el Centro de administración de Teams, vaya a **Directivas**[**de configuración de aplicaciones**](https://admin.teams.microsoft.com/policies/app-setup) de Teams > .

1. En **la pestaña Administrar directivas**, selecciona **Global (predeterminado para toda la organización)** y, a continuación **, editar.**

   :::image type="content" source="media/setup-policies.png" alt-text="Captura de pantalla de las directivas de configuración de la aplicación Adobe Acrobat en el Centro de administración de Teams.":::

1. En Aplicaciones instaladas, selecciona **Agregar aplicaciones**.

1. Busca **Adobe Acrobat**, selecciona **Agregar** junto al nombre de la aplicación y, a continuación, selecciona **Agregar**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Captura de pantalla que muestra cómo agregar la aplicación Adobe Acrobat para todos los usuarios." lightbox="media/add-adobe-acrobat-app.png":::

1. Seleccione **Guardar**.

Después de seleccionar Guardar, Teams usa la aplicación Adobe Acrobat como controlador de archivos predeterminado para archivos PDF.

Si desea permitir selectivamente la aplicación Adobe Acrobat para algunas personas o para un grupo, puede asignar una [directiva de permisos de aplicación personalizada](teams-app-permission-policies.md).

Conozca la siguiente información sobre esta funcionalidad:

* Una vez configurada la directiva, normalmente la aplicación tarda [unas horas](teams-app-setup-policies.md) en estar disponible para los usuarios.
* Una vez configurada la directiva, la aplicación instalada estará disponible para los usuarios después de unas pocas horas.
* La visualización de archivos PDF anclados en canales como una pestaña y la visualización de archivos PDF en la aplicación Tareas sigue funcionando con la experiencia nativa de Teams.
* Adobe Acrobat como visor de PDF predeterminado en Teams solo funciona en clientes web y de escritorio. No es compatible con el cliente móvil.
* Los usuarios necesitan un plan Adobe Acrobat para usar las herramientas premium como Exportar PDF, Organizar páginas, Combinar archivos, Comprimir PDF y Proteger PDF.
* Para desinstalar la aplicación, los usuarios finales pueden quitarla del cliente de Teams. Administración puede quitar la aplicación Adobe Acrobat mediante la directiva de configuración.
* Si bloqueas la aplicación Adobe Acrobat, quítalo de la directiva de configuración. Garantiza que la experiencia del usuario final vuelva a usar el visor de archivos PDF nativos.
* Desde el cliente de escritorio de Teams, si tiene problemas al iniciar sesión en la aplicación Adobe Acrobat, use Teams en el explorador para iniciar sesión.
