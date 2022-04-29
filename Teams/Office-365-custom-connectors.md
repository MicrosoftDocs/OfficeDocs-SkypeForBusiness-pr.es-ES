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
ms.openlocfilehash: 2dea5ee50d75ff8913bc88f2f3947d9f665cb4dd
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65137021"
---
# <a name="manage-microsoft-365-and-custom-connectors"></a>Administrar Microsoft 365 y conectores personalizados

Para mantener su equipo actualizado, los conectores ofrecen actualizaciones de contenido y servicio que se usan con frecuencia directamente en un canal de Teams. Con los conectores, los usuarios de Teams pueden recibir actualizaciones de servicios populares como Trello, Wunderlist, GitHub y Azure DevOps Services. Las actualizaciones se publican directamente en la secuencia de chat de su equipo.

Microsoft 365 conectores se usan con grupos de Microsoft Teams y Microsoft 365, lo que facilita que todos los miembros se sincronicen y reciban rápidamente información relevante. Tanto Microsoft Teams como Exchange utilizan el mismo modelo de conector, lo que le permite utilizar los mismos conectores en ambas plataformas. Sin embargo, si deshabilita los conectores configurados para un grupo de Microsoft 365, también se deshabilita la posibilidad de que el grupo de Microsoft 365 cree conectores.

Cualquier miembro de un equipo puede conectar su equipo a servicios en la nube populares con los conectores si los permisos del equipo lo permiten y todos los miembros del equipo reciben una notificación de las actividades de ese servicio. Los conectores siguen funcionando después de que el miembro que inicialmente configuró el conector deje de funcionar. Cualquier miembro del equipo con los permisos para agregar o quitar puede modificar la configuración de los conectores por otros miembros.

## <a name="enable-or-disable-connectors-in-teams"></a>Habilitar o deshabilitar conectores en Teams

El módulo Exchange Online PowerShell V2 usa la autenticación moderna y funciona con la autenticación multifactor, denominada MFA para conectarse a todos los Exchange entornos de PowerShell relacionados en Microsoft 365. Los administradores pueden usar Exchange Online PowerShell para deshabilitar los conectores para todo un espacio empresarial o un buzón de grupo específico, lo que afecta a todos los usuarios de ese espacio empresarial o buzón. No es posible deshabilitar para algunos usuarios específicos. Además, los conectores están deshabilitados de forma predeterminada para Government Community Cloud, denominados inquilinos de GCC.

La configuración del inquilino reemplaza la configuración del grupo. Por ejemplo, si un administrador habilita los conectores para el grupo y los deshabilita en el espacio empresarial, los conectores del grupo se deshabilitan. Para habilitar un conector en Teams, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps#connect-to-exchange-online-powershell-using-modern-authentication-with-or-without-mfa&preserve-view=true) mediante la autenticación moderna con o sin MFA.

Para habilitar o deshabilitar un conector, ejecute los siguientes comandos en Exchange Online PowerShell:

* Para deshabilitar los conectores para el espacio empresarial: `Set-OrganizationConfig -ConnectorsEnabled:$false`.
* Para deshabilitar los mensajes accionables para el espacio empresarial: `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$false`.
* Para habilitar los conectores para Teams, ejecute los siguientes comandos:
  * `Set-OrganizationConfig -ConnectorsEnabled:$true`
  * `Set-OrganizationConfig -ConnectorsEnabledForTeams:$true`
  * `Set-OrganizationConfig -ConnectorsActionableMessagesEnabled:$true`

Para obtener más información sobre el intercambio de módulos de PowerShell, consulte [Set-OrganizationConfig](/powershell/module/exchange/Set-OrganizationConfig?view=exchange-ps&preserve-view=true). Para habilitar o deshabilitar los conectores de Outlook, [conecte aplicaciones a los grupos de Outlook](https://support.microsoft.com/topic/connect-apps-to-your-groups-in-outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab).

<!--- TBD: Find out how can we get to know about completion of customer migration.
Delete this section after customer migration to new Webhook URL is complete.
--->

## <a name="publish-connectors-for-your-organization"></a>Publicar conectores para su organización

Si quiere que un conector personalizado esté disponible solo para los usuarios de la organización, puede cargar una aplicación de conector personalizada en el catálogo de aplicaciones de su organización. Después de cargar el paquete de la aplicación, los usuarios finales pueden instalar el conector desde el catálogo de aplicaciones de la organización y pueden configurar y usar el conector en un equipo.

<!---TBD: Check if these instructions are for admins or end-users. I cannot find these options either in Teams or in TAC.

To set up a connector:

1. Select **Apps** from the left navigation bar.
1. In the **Apps** section, select **Connectors**.
1. Select the connector that you want to add.
1. From the pop-up menu, select **Add to a team**.
1. In the search box, type a team or channel name.
1. Select **Set up a Connector** from the pop-up menu in the bottom right corner of the dialog window.
--->

> [!IMPORTANT]
> Los conectores personalizados no están disponibles en Government Community Cloud (GCC), GCC-High ni en el Departamento de Defensa (DOD).

Para usar conectores en un equipo o canal, abra el menú Más opciones en la esquina superior derecha de un canal. En el menú, seleccione **Conectores** y busque o busque la aplicación del conector necesaria. Configure el conector seleccionado si es necesario.

:::image type="content" source="media/connectors-selection-ui.png" alt-text="Agregue conectores al canal en Teams desde Más opciones en la esquina superior derecha del canal.":::

## <a name="update-url-of-a-connector"></a>Actualizar la dirección URL de un conector

Los conectores Teams están cambiando a una nueva dirección URL para mejorar la seguridad. Durante la transición, recibirá una notificación para actualizar el conector configurado. Actualice el conector lo antes posible para evitar interrupciones en los servicios del conector. Para actualizar el conector:

1. En la página de configuración de conectores, busque el mensaje **Atención requerida** junto al conector configurado.

   :::image type="content" source="media/Teams_Attention_Required_message.png" alt-text="Captura de pantalla del mensaje Atención requerida.":::

1. Para volver a crear la conexión de los conectores webhook entrantes, seleccione **Actualizar DIRECCIÓN URL** y use la dirección URL generada del webhook.

   :::image type="content" source="media/Teams_update_URL_button.png" alt-text="Captura de pantalla del botón Actualizar dirección URL.":::

1. Para otros tipos de conector, quite el conector y vuelva a crear la configuración del conector. Aparece un mensaje **con la dirección URL actualizada** .

   :::image type="content" source="media/Teams_URL_up_to_date.png" alt-text="Captura de pantalla del mensaje &quot;La dirección URL está actualizada&quot;.":::

## <a name="see-also"></a>Vea también

* [Información general sobre conectores personalizados y webhooks](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Crear conectores Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
