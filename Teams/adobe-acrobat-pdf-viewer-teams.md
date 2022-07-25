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
ms.openlocfilehash: fd74ece7ba59b437fcd8b47bd184cdcfd150438d
ms.sourcegitcommit: 4708fc1c2b8523e1074aed06b1dd6950c039f200
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2022
ms.locfileid: "67002347"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-teams"></a>Adobe Acrobat como visor de PDF predeterminado en Teams

> [!NOTE]
> Adobe Acrobat como experiencia de PDF predeterminada en Teams solo está disponible actualmente en la versión preliminar pública. [Habilite la versión preliminar pública](public-preview-doc-updates.md#enable-public-preview) para su inquilino antes de usar esta característica. Asegúrese de que los usuarios finales cambien la versión del cliente de Teams a la versión preliminar pública para experimentar Adobe Acrobat como visor de PDF en Teams.

Como administrador, puede establecer Adobe Acrobat como la aplicación predeterminada para ver y editar archivos PDF en Microsoft Teams. Los usuarios finales no necesitan una suscripción a Adobe Acrobat ni un Adobe ID para ver, buscar, comentar y anotar archivos PDF.

## <a name="set-up-adobe-acrobat-app"></a>Configurar la aplicación Adobe Acrobat

Para configurar Adobe Acrobat como la aplicación predeterminada para ver archivos PDF, siga estos pasos:

1. Inicie sesión en el Centro de administración de Teams y vaya a **La aplicación** >  de Teams **[Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. Busca la aplicación Adobe Acrobat y selecciona **Aplicación Adobe Acrobat** .

   > [!NOTE]
   >
   > * Asegúrate de que el estado de la aplicación Adobe Acrobat esté establecido en **Permitido**. En caso contrario, habilite el botón de alternancia **Permitido** .
   > * Si existe alguna configuración de administrador en la directiva de permisos de la aplicación o en la configuración de la aplicación para toda la organización que ha bloqueado la aplicación, asegúrese de permitir la aplicación en la directiva de permisos de la [aplicación](teams-app-permission-policies.md) o en la configuración de la [aplicación para toda](teams-app-permission-policies.md) la organización.

1. En la pestaña **Permisos** , seleccione **Revisar permiso**.

1. Seleccione **Aceptar**.

   :::image type="content" source="media/permission-policy.png" alt-text="Captura de pantalla de permisos de aplicaciones en el Centro de administración de Teams." lightbox="media/teams-app-adobe-acrobat-permission.png":::

## <a name="install-adobe-acrobat-app-for-all-users"></a>Instalar la aplicación Adobe Acrobat para todos los usuarios

Puede usar la directiva Global (predeterminada para toda la organización) para asignar y hacer que la aplicación Adobe Acrobat esté disponible para todos los usuarios. Este paso desencadena una señal en Teams para establecer la aplicación como el controlador de archivos predeterminado para archivos PDF. Para asignar la aplicación Adobe Acrobat a todos los usuarios, siga estos pasos:

1. En el Centro de administración de Teams, vaya a **Directivas**[**de configuración de aplicaciones**](https://admin.teams.microsoft.com/policies/app-setup) de Teams > .

1. En **la pestaña Administrar directivas**, selecciona **Global (predeterminado para toda la organización)** y, a continuación **, editar.**

   :::image type="content" source="media/setup-policies.png" alt-text="Captura de pantalla de las directivas de configuración de la aplicación Adobe Acrobat en el Centro de administración de Teams.":::

1. En Aplicaciones instaladas, selecciona **Agregar aplicaciones**.

1. Busca **Adobe Acrobat**, selecciona **Agregar** junto al nombre de la aplicación y, a continuación, selecciona **Agregar**.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="Captura de pantalla que muestra cómo agregar la aplicación Adobe Acrobat para todos los usuarios." lightbox="media/add-adobe-acrobat-app.png":::

1. Seleccione **Guardar**.

Después de seleccionar Guardar, la aplicación Adobe Acrobat se configura con Teams para abrir cualquier archivo PDF en la aplicación Adobe Acrobat desde el chat, el canal o la aplicación de archivos.

Si quieres permitir selectivamente la aplicación Adobe Acrobat para algunas personas o para un grupo, puedes asignar una [directiva de permisos de aplicación personalizada](teams-app-permission-policies.md).

Conozca la siguiente información sobre esta funcionalidad:

* Una vez configurada la directiva, normalmente la aplicación tarda [unas horas](teams-app-setup-policies.md) en estar disponible para los usuarios.
Una vez configurada la directiva, la aplicación instalada estará disponible para los usuarios después de unas pocas horas.
* La visualización de archivos PDF anclados en canales como una pestaña y la visualización de archivos PDF en la aplicación de tareas siguen funcionando con la experiencia nativa de Teams.
* Adobe Acrobat como visor de PDF predeterminado en Teams solo funciona en clientes web y de escritorio. No es compatible con el cliente móvil.
* Los usuarios necesitan un plan Adobe Acrobat para usar herramientas premium como Exportar PDF, Organizar páginas, Combinar archivos, Comprimir PDF y Proteger PDF.

> [!NOTE]
> Desde el cliente de escritorio de Teams, si tiene problemas al iniciar sesión en la aplicación Adobe Acrobat, puede abrir Teams en el explorador e iniciar sesión. Este es un problema conocido y se resolverá en septiembre de 2022.

## <a name="faqs"></a>Preguntas frecuentes

* ¿Cómo quitar la aplicación Adobe Acrobat del cliente de Teams?
  
  Los usuarios finales pueden desinstalar la aplicación del cliente de Teams y el administrador puede quitar la aplicación Adobe Acrobat de la directiva de configuración.

* ¿Los administradores pueden bloquear la aplicación Adobe Acrobat una vez establecida como controlador predeterminado?
  
  Sí, pero antes de que el administrador bloquee la aplicación, quite la directiva de configuración para asegurarse de que los usuarios finales vuelvan a la experiencia predeterminada de Teams de forma segura.
