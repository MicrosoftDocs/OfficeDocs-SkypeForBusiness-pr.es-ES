---
title: Administrar conectores de Microsoft 365 y conectores personalizados
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 01/24/2023
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo los conectores mantienen a su equipo actualizado proporcionando frecuentemente contenido y actualizaciones directamente en un canal de Teams para los servicios que usa.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: bf38711da0205e7c674e769942d00d340d51f66e
ms.sourcegitcommit: 1cb5f7129562eb2b228da23497c0e09e53da3872
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2023
ms.locfileid: "69983688"
---
# <a name="manage-microsoft-365-connectors-and-custom-connectors"></a>Administrar conectores de Microsoft 365 y conectores personalizados

Los conectores de Microsoft Teams ofrecen actualizaciones de contenido y servicio directamente desde servicios de terceros a un canal de Teams. Al usar conectores, los usuarios reciben actualizaciones de servicios populares como Trello, Wunderlist, GitHub y Azure DevOps Services. Las actualizaciones se publican directamente en la secuencia de chat. Esto facilita que todos los miembros se mantengan sincronizados y reciban rápidamente la información relevante.

Los conectores de Microsoft 365 se usan con los grupos de Teams y Microsoft 365. Puede usar los mismos conectores en Teams y Microsoft Exchange. 

<!--- However, if you disable any connectors configured for a Microsoft 365 group, it also disables the ability for the Microsoft 365 group to create connectors. --->

Si los permisos del equipo lo permiten, cualquier miembro del equipo puede agregar un conector en el equipo y todos los miembros del equipo reciben una notificación de las actividades de ese servicio. Cualquier miembro del equipo con los permisos para agregar o quitar puede modificar la configuración de conectores por parte de otros miembros.

## <a name="enable-or-disable-connectors-in-teams"></a>Habilitar o deshabilitar conectores en Teams

El módulo Exchange Online PowerShell v2 usa la autenticación moderna y funciona con la autenticación multifactor (MFA) para conectarse a todos los entornos de PowerShell relacionados con Exchange en Microsoft 365. Los administradores pueden usar Exchange Online PowerShell para deshabilitar conectores para todo un espacio empresarial o un buzón de grupo específico, lo que afecta a todos los usuarios de ese espacio empresarial o buzón. No es posible deshabilitar para algunos usuarios específicos.

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

## <a name="considerations-when-using-connectors-in-teams"></a>Consideraciones al usar conectores en Teams

* Los Conectores están deshabilitados de forma predeterminada en los entornos de Government Cloud Community (GCC). Para habilitarlos, establezca los parámetros `ConnectorsEnabled` o `ConnectorsEnabledForTeams` en `$true` con el cmdlet `SetOrganizationConfig`. Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps&preserve-view=true).

* Si el usuario que agregó un conector a un equipo deja el equipo, el conector sigue funcionando.

* Los siguientes conectores no están disponibles para su uso en enero de 2023 en adelante:

  * AHA
  * BRAKE DE AIRE
  * AIRCALL
  * VÍNCULOS DE APLICACIONES
  * APPSIGNAL
  * BEANSTALK
  * BIT.DESPLOTE
  * BITBUCKETSERVER
  * AMIGO
  * BUGSNAG
  * BUILDKITE
  * CATSONE
  * CHATRA
  * CÍRCULOCI
  * CODESHIP
  * IR A BUSCAR
  * FANTASMAINSPECTOR
  * RANURA
  * HEROKU
  * HONEYBADGER
  * INTERCOMUNICADOR
  * LOGENTRIES
  * NUEVORELIC
  * OPSGENIE
  * PAGERDUTY
  * PAPERTRAIL
  * PINGDOM
  * PIVOTALTRACKER
  * RAYGUN
  * ARCO
  * RUNSCOPE
  * SISMÓMETRO
  * SEMÁFORO
  * CENTINELA
  * SHAREPOINTNEWS
  * SIMPLEINOUT
  * STATUSPAGEIO
  * SUBVERSIÓN
  * TEAMFOUNDATIONSERVER
  * TESTFAIRY
  * TRAVISCI
  * UPDOWN
  * EN FORMA DE USUARIO
  * XPDEV

## <a name="related-articles"></a>Artículos relacionados

* [Información general sobre conectores y webhooks personalizados](/microsoftteams/platform/webhooks-and-connectors/what-are-webhooks-and-connectors)
* [Cómo crear conectores de Office 365](/microsoftteams/platform/webhooks-and-connectors/how-to/connectors-creating)
