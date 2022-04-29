---
title: Administrar Microsoft 365 y conectores personalizados
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Los conectores mantienen su equipo al día haciendo llegar contenido y actualizaciones de servicios que se usan con frecuencia directamente en un canal.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 100db95adf900a48898515b9bb9a3a753b47de4f
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125445"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Administrar Microsoft 365 y conectores personalizados

Para mantener su equipo actualizado, los conectores ofrecen actualizaciones de contenido y servicio que se usan con frecuencia directamente en un canal de Teams. Con los conectores, los usuarios de Teams pueden recibir actualizaciones de servicios populares como Trello, Wunderlist, GitHub y Azure DevOps Services. Las actualizaciones se publican directamente en la secuencia de chat de su equipo.

Microsoft 365 conectores se usan con grupos de Microsoft Teams y Microsoft 365, lo que facilita que todos los miembros se sincronicen y reciban rápidamente información relevante. Tanto Microsoft Teams como Exchange utilizan el mismo modelo de conector, lo que le permite utilizar los mismos conectores en ambas plataformas. Sin embargo, si deshabilita los conectores configurados para un grupo de Microsoft 365, también se deshabilita la posibilidad de que el grupo de Microsoft 365 cree conectores.

Cualquier miembro de un equipo puede conectar su equipo a servicios en la nube populares con los conectores si los permisos del equipo lo permiten y todos los miembros del equipo reciben una notificación de las actividades de ese servicio. Los conectores siguen funcionando después de que el miembro que configuró inicialmente el conector se haya ido. Cualquier miembro del equipo con los permisos para agregar o quitar puede modificar la configuración de los conectores por otros miembros.

## <a name="enable-or-disable-connectors-in-teams"></a>Habilitar o deshabilitar conectores en Teams

El módulo Exchange Online PowerShell V2 usa la autenticación moderna y funciona con la autenticación multifactor, denominada MFA para conectarse a todos los Exchange entornos de PowerShell relacionados en Microsoft 365. Los administradores pueden usar Exchange Online PowerShell para deshabilitar los conectores para todo un espacio empresarial o un buzón de grupo específico, lo que afecta a todos los usuarios de ese espacio empresarial o buzón. No es posible deshabilitar para algunos usuarios específicos. Además, los conectores están deshabilitados de forma predeterminada para Government Community Cloud, denominados inquilinos de GCC.

La configuración del inquilino reemplaza la configuración del grupo. Por ejemplo, si un administrador habilita los conectores para el grupo y los deshabilita en el espacio empresarial, los conectores del grupo se deshabilitan. Para habilitar un conector en Teams, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) mediante la autenticación moderna con o sin MFA.

### <a name="commands-to-enable-or-disable-connectors"></a>Comandos para habilitar o deshabilitar conectores

Ejecute los siguientes comandos en Exchange Online PowerShell:

* Para deshabilitar los conectores para el espacio empresarial: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Para deshabilitar los mensajes accionables para el espacio empresarial: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Para habilitar los conectores para Teams, ejecute los siguientes comandos:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Para obtener más información sobre el intercambio de módulos de PowerShell, consulte [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Para habilitar o deshabilitar los conectores de Outlook, [conecte aplicaciones a los grupos de Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!---TBD: Delete this section after customer migration to new Webhook URL is complete --->

#### <a name="connector-url-update-notification"></a>Notificación de actualización de la dirección URL del conector

Los conectores Teams están cambiando a una nueva dirección URL para mejorar la seguridad. Durante la transición, recibirá una notificación para actualizar el conector configurado. Actualice el conector lo antes posible para evitar interrupciones en los servicios del conector. Para actualizar el conector:

1. En la página de configuración de conectores, busque el mensaje **Atención requerida** junto al conector configurado.

   ![Captura de pantalla del mensaje Atención requerida.](media/Teams_Attention_Required_message.png)

1. Para volver a crear la conexión de los conectores webhook entrantes, seleccione **Actualizar DIRECCIÓN URL** y use la dirección URL generada del webhook.

   ![Captura de pantalla del botón Actualizar dirección URL.](media/Teams_update_URL_button.png)

1. Para otros tipos de conector, quite el conector y vuelva a crear la configuración del conector. Aparece un mensaje **con la dirección URL actualizada** .

   ![Captura de pantalla del mensaje "La dirección URL está actualizada".](media/Teams_URL_up_to_date.png)

## <a name="see-also"></a>Vea también

* [Información general sobre conectores personalizados y webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Crear conectores Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)