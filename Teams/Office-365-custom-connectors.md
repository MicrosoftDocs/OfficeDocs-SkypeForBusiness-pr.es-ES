---
title: Administrar Microsoft 365 y los conectores personalizados
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo los Conectores mantienen actualizado a su equipo entregando con frecuencia contenido y actualizaciones directamente en un canal de Teams para los servicios que usa.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5e61a6705f470ee93c7169effdd56f35ca0dd6f4
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837360"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Administrar Microsoft 365 y los conectores personalizados

Para mantener actualizado su equipo, los conectores entregan contenido y actualizaciones de servicio usados con frecuencia directamente en un canal de Teams. Con los conectores, los usuarios de Teams pueden recibir actualizaciones de servicios populares como Trello, Wunderlist, GitHub y Azure DevOps Services. Las actualizaciones se publican directamente en el flujo de chat de su equipo.

Los conectores de Microsoft 365 se usan tanto con Microsoft Teams como con grupos de Microsoft 365. Facilitan que todos los miembros permanezcan sincronizados y reciban rápidamente la información pertinente. Puede usar los mismos conectores en Microsoft Teams y Microsoft Exchange. Sin embargo, si deshabilita los conectores configurados para un grupo de Microsoft 365, también se deshabilita la posibilidad de que el grupo de Microsoft 365 cree conectores.

Cualquier miembro de un equipo puede conectar su equipo a servicios en la nube populares con los conectores si los permisos del equipo lo permiten, y se notifica a todos los miembros del equipo de las actividades de ese servicio. Los conectores siguen funcionando después de que el miembro que inicialmente configuró el conector se vaya. Cualquier miembro del equipo con los permisos para agregar o quitar puede modificar la configuración de conectores por parte de otros miembros.

## <a name="enable-or-disable-connectors-in-teams"></a>Habilitar o deshabilitar conectores en Teams

El módulo Exchange Online PowerShell V2 usa la autenticación moderna y funciona con la autenticación multifactor (MFA) para conectarse a todos los entornos de PowerShell relacionados con Exchange en Microsoft 365. Los administradores pueden usar Exchange Online PowerShell para deshabilitar conectores para todo un espacio empresarial o un buzón de grupo específico, lo que afecta a todos los usuarios de ese espacio empresarial o buzón. No es posible deshabilitarlos para algunos usuarios específicos. Además, los conectores están deshabilitados de forma predeterminada para entornos de Government Community Cloud, (GCC).

> [!NOTE]
> Los Conectores están deshabilitados de forma predeterminada en los entornos de Government Cloud Community (GCC). Para habilitarlos, establezca los parámetros `ConnectorsEnabled` o `ConnectorsEnabledForTeams` en `$true` con el cmdlet `SetOrganizationConfig`. Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

La configuración del espacio empresarial invalida la configuración del grupo. Por ejemplo, si un administrador habilita los conectores para el grupo y los deshabilita en el espacio empresarial, los conectores del grupo se deshabilitan. Para habilitar un conector en Teams, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) mediante la autenticación moderna con o sin MFA.

Para habilitar o deshabilitar un conector, ejecute los siguientes comandos en Exchange Online PowerShell:

* Para deshabilitar los conectores para el espacio empresarial: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Para deshabilitar los mensajes accionables para el espacio empresarial: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Para habilitar conectores para Teams, ejecute los siguientes comandos:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Para obtener más información sobre el intercambio de módulos de PowerShell, vea [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Para habilitar o deshabilitar los conectores de Outlook, [conecte aplicaciones a los grupos en Microsoft Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

## <a name="publish-connectors-for-your-organization"></a>Publicar conectores para la organización

Para que un conector personalizado esté disponible para los usuarios de su organización, cargue una aplicación de conector personalizado en el catálogo de aplicaciones de su organización. Los usuarios finales de la organización pueden instalar, configurar y usar el conector en un equipo.

> [!IMPORTANT]
> Los conectores personalizados no están disponibles en entornos de Government Community Cloud (GCC), Government Community Cloud-High (GCCH) y Department of Defense (DOD).

Para usar conectores en un equipo o un canal, abra el menú Más opciones en la esquina superior derecha de un canal. En el menú, seleccione **Conectores** y localice o busque el conector necesario. Configure el conector seleccionado si es necesario.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Agregar conectores a su canal en Teams desde Más opciones en la esquina superior derecha del canal.":::

## <a name="update-url-of-a-connector"></a>Actualizar la dirección URL de un conector

Los conectores de Teams están realizando la transición a una nueva dirección URL para mejorar la seguridad. Durante la transición, recibirá una notificación para actualizar el conector configurado. Actualice el conector lo antes posible para evitar cualquier interrupción en los servicios del conector. Para actualizar el conector:

1. En la página de configuración de conectores, busque el mensaje **Requiere atención** junto al conector configurado.

   :::image type="content" source="media/teams-attention-required-message.png" alt-text="Captura de pantalla del mensaje Requiere atención.":::

1. Para volver a crear la conexión para los conectores de webhook entrantes, seleccione **Actualizar dirección URL** y use la dirección URL de webhook generada.

   :::image type="content" source="media/teams-update-url-option.png" alt-text="Captura de pantalla del botón Actualizar dirección URL.":::

1. Para otros tipos de conector, quite el conector y vuelva a crear la configuración del conector. Aparece un mensaje que indica que la **dirección URL está actualizada**.

   :::image type="content" source="media/teams-url-updated.png" alt-text="Captura de pantalla del mensaje la dirección URL está actualizada.":::

## <a name="related-articles"></a>Artículos relacionados

* [Introducción a los conectores y webhooks personalizados](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Crear conectores de Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
