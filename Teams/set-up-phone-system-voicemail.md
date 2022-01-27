---
title: Configurar el Correo de voz en la nube
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
description: Obtenga información sobre cómo configurar Correo de voz en la nube para los usuarios.
ms.openlocfilehash: cb0a8b6ad8a82ef44ace21dceb9adbbfc7c04139
ms.sourcegitcommit: cd9fbda4ea85a83cb22e241a94d0825ff8186cca
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2022
ms.locfileid: "62228948"
---
# <a name="set-up-cloud-voicemail"></a>Configurar el Correo de voz en la nube

Este artículo es para el administrador Microsoft 365 o Office 365 como se describe en Acerca de los [roles](/microsoft-365/admin/add-users/about-admin-roles) de administrador que desea configurar la característica Correo de voz en la nube para todos los usuarios de la empresa. Correo de voz en la nube requiere Exchange buzones de correo de voz para los usuarios en los que deposita mensajes de correo de voz. No es compatible con sistemas de correo electrónico de terceros. Para Exchange Online requisitos de licencia, [consulte Exchange Online descripción del servicio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans).

## <a name="cloud-voicemail-for-teams-users"></a>Correo de voz en la nube para Teams usuarios

Para Teams usuarios, Correo de voz en la nube se configura y aprovisiona automáticamente. No Microsoft Teams Teléfono una licencia de Correo de voz en la nube.

## <a name="help-your-users-learn-teams-voicemail-features"></a>Ayudar a los usuarios a aprender Teams de correo de voz

Tenemos la siguiente información para los usuarios sobre el uso y administración del correo de voz en Teams:

- [Compruebe el correo de voz en Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Administrar la configuración de la llamada en Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)

## <a name="setting-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurar Correo de voz en la nube para trabajar con usuarios locales

Puede usar Correo de voz en la nube para proporcionar funcionalidad de correo de voz a los usuarios que tienen buzones en los servidores Exchange o para los usuarios que usan Skype Empresarial Server. Esta sección proporciona información para estos escenarios. 

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar Correo de voz en la nube usuarios Exchange Server buzón de correo

La siguiente información es sobre cómo configurar Correo de voz en la nube trabajar con Microsoft Teams Teléfono usuarios que tienen su buzón en Exchange Server.

1. Los mensajes de correo de voz se entregan a los buzones Exchange los usuarios a través de SMTP enrutados a través de Exchange Online Protection. Para habilitar la entrega correcta de estos mensajes, asegúrese de que Exchange conectores están configurados correctamente entre los servidores Exchange y Exchange Online Protection; [Usar conectores para configurar el correo Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Para habilitar características de correo de voz como personalizar saludos y correo de voz visual en clientes Skype Empresarial, se requiere conectividad de Microsoft 365 o Office 365 al buzón de servidor de Exchange a través de Exchange Servicios web. Para habilitar esta conectividad, debe configurar el nuevo protocolo de autenticación de Oauth de Exchange descrito en Configurar autenticación [de OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre organizaciones de Exchange y Exchange Online, o ejecutar el Asistente híbrido de Exchange desde Exchange 2013 CU5 o posterior. Además, debe configurar la integración y Oauth entre Skype Empresarial Online y un servidor Exchange descrito en Configurar integración y [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)entre Skype Empresarial Online y Exchange Server .

### <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurar Correo de voz en la nube usuarios Skype Empresarial Server usuarios

Para configurar Skype Empresarial de servidor para Correo de voz en la nube, vea [Planear Correo de voz en la nube para usuarios locales.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Habilitar el correo de voz protegido en su organización

Cuando alguien deja un mensaje de correo de voz para un usuario de su organización, el correo de voz se entrega al buzón del usuario como datos adjuntos de un mensaje de correo electrónico. Si usa reglas de flujo de correo para aplicar el cifrado de mensajes, puede evitar que esos mensajes de correo de voz se reenván a otros destinatarios. Al habilitar el correo de voz protegido, los usuarios pueden escuchar mensajes de correo de voz protegidos llamando a su buzón de voz o abriendo el mensaje en Outlook, Outlook en la Web o en Outlook para Android o iOS. Los mensajes de correo de voz protegidos no se pueden abrir en Skype Empresarial o Microsoft Teams.

Para obtener más información sobre el cifrado de mensajes, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico.](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)
