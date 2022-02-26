---
title: Configurar el Correo de voz en la nube
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
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
ms.openlocfilehash: f1645ec9a14a5b201809cbe12219d7b1e437d355
ms.sourcegitcommit: edf68b7ac4f1861259a0990157ee6ae84f68ca42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2022
ms.locfileid: "62974477"
---
# <a name="set-up-cloud-voicemail"></a>Configurar el Correo de voz en la nube

Este artículo es para Microsoft 365 administradores que quieren configurar Correo de voz en la nube para sus usuarios. 

Correo de voz en la nube mensajes de correo de voz en el buzón de correo de Exchange usuario. Correo de voz en la nube no es compatible con sistemas de correo electrónico de terceros. Para Exchange Online requisitos de licencia, [vea Exchange Online descripción del servicio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Para obtener más información sobre los roles de administrador, vea [Acerca de los roles de administrador](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>Correo de voz en la nube aprovisionamiento

Para Teams usuarios, Correo de voz en la nube se configura y aprovisiona automáticamente. *No Microsoft Teams Teléfono una licencia de Correo de voz en la nube.*

El aprovisionamiento Teams usuarios no es el mismo que para Skype Empresarial en línea. Para Skype Empresarial en línea, Correo de voz en la nube se configuraba y aprovisionaba automáticamente cuando a los usuarios se les asignó una licencia de Sistema telefónico y el sistema de aprovisionamiento Telefonía IP empresarial habilitado.

Para Skype Empresarial Server locales, Correo de voz en la nube se configura y aprovisiona automáticamente. Sin embargo, debe configurar el entorno Skype Empresarial Server para enrutar las llamadas a Correo de voz en la nube. Para obtener más información, vea [Planear Correo de voz en la nube para usuarios locales](/skypeforbusiness/hybrid/plan-cloud-voicemail.md). 

## <a name="cloud-voicemail-storage"></a>Correo de voz en la nube almacenamiento

Los mensajes de correo de voz generados por Correo de voz en la nube se entregan y se almacenan en el buzón de correo Exchange del usuario, ya sea en Exchange Online o en Exchange Server. No hay almacenamiento específico o adicional para el correo de voz. Los clientes que tienen acceso al correo de voz (por ejemplo, Microsoft Outlook, Microsoft Teams o Skype Empresarial) lo hacen a través del buzón Exchange y las API proporcionadas. 

Un mensaje de correo de voz contiene un archivo de audio adjunto con los mensajes de voz y la transcripción del correo de voz (si está habilitado). 

El Exchange de un usuario almacena los saludos grabados personalizados. Estos saludos se recuperan Correo de voz en la nube necesarios durante una llamada entrante. 

## <a name="cloud-voicemail-processing"></a>Correo de voz en la nube procesamiento 

La grabación y transcripción de Correo de voz en la nube se inicia en Microsoft 365 en el origen de la llamada que se enruta a Correo de voz en la nube. A continuación, el mensaje se entrega al buzón de correo Exchange usuario. 

Por ejemplo, si una llamada llega a un usuario de Enrutamiento directo no disponible a través de un controlador de borde de sesión (SBC) en Europa, la grabación y transcripción del correo de voz se realizan en Europa. A continuación, el mensaje se entrega al buzón de correo Exchange usuario. Por otro ejemplo, supongamos que un Teams en Norteamérica llama a un usuario Teams disponible en Europa. En este caso, la llamada comienza en Norteamérica, el procesamiento se produce en Norteamérica y, a continuación, el correo de voz se entrega al buzón de correo de correo Exchange usuario en Europa. 

La entrega de un correo de voz a un buzón de Exchange se realiza con el Protocolo simple de transporte de correo electrónico (SMTP) como cualquier otro correo electrónico. 

## <a name="manage-cloud-voicemail-for-users"></a>Administrar Correo de voz en la nube usuarios 

Para administrar Correo de voz en la nube características para los usuarios, use el Teams PowerShell de la siguiente manera. 

Para administrar Correo de voz en la nube para grupos de usuarios, use el cmdlet [New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy). Puede configurar y asignar directivas de correo de voz existentes o nuevas para características como las reglas de respuesta a llamadas, la transcripción del correo de voz, el enmascaramiento de la opacidad de la transcripción, la traducción de transcripción y el idioma del sistema. Para obtener más información, [vea New-CsOnlineVoicemailPolicy](/powershell/module/skype/new-csonlinevoicemailpolicy).

Para administrar Correo de voz en la nube configuración para usuarios individuales, use el cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings). Correo de voz en la nube que puede aplicar a usuarios individuales incluyen reglas de respuesta a llamadas, idioma rápido, texto a voz predeterminado y saludos de vacaciones. Para obtener más información, [vea Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings).
(Tenga en cuenta que los usuarios finales  ->  también pueden configurar estas opciones en el Teams de correo de voz Configuración **CallsConfigure** ->  **Voicemail**).

También puede deshabilitar Correo de voz en la nube para un usuario mediante el cmdlet [Set-CsOnlineVoicemailUserSettings](/powershell/module/skype/set-csonlinevoicemailusersettings) y estableciendo el parámetro VoicemailEnabled en $false. Esta configuración garantizará que Correo de voz en la nube ya no puede grabar un correo de voz para el usuario.



## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Controlar el enrutamiento de llamadas a Correo de voz en la nube 

La configuración predeterminada para todos los usuarios aprovisionados para Correo de voz en la nube es permitir el enrutamiento de llamadas a Correo de voz en la nube y permitir que los usuarios reenván llamadas a Correo de voz en la nube. 

Puede controlar si el enrutamiento de llamadas a Correo de voz en la nube está permitido para Teams usuarios mediante el cmdlet Set-CsTeamsCallingPolicy con el parámetro AllowVoicemail. Para obtener más información,  [veaSet-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy.md). 

- Si establece AllowVoicemail en AlwaysDisabled, las llamadas nunca se enrutan al correo de voz, independientemente de la configuración de reenvío de llamadas o sin respuesta de un usuario. El correo de voz no está disponible como una configuración de reenvío de llamadas o sin respuesta en Teams.  

- Si establece AllowVoicemail en AlwaysEnabled, las llamadas siempre se reenvía al correo de voz sin responder después de llamar durante treinta segundos, independientemente de la configuración de reenvío de llamadas sin responder para un usuario.  

- Si establece AllowVoicemail en UserOverride, las llamadas se reenvía al correo de voz en función de la configuración de reenvío de llamadas y/o sin respuesta de un usuario. 



## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurar Correo de voz en la nube para trabajar con usuarios locales

Puede usar Correo de voz en la nube de correo de voz para los usuarios que tienen buzones en los servidores Exchange o para los usuarios que usan Skype Empresarial Server. 

En esta sección se describe cómo configurar Correo de voz en la nube usuarios Exchange Server buzón de correo. Para obtener información sobre cómo configurar Correo de voz en la nube usuarios Skype Empresarial Server, vea Planear Correo de voz en la nube para usuarios [locales](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar Correo de voz en la nube usuarios Exchange Server buzón de correo

La siguiente información es sobre cómo configurar Correo de voz en la nube trabajar con Teams usuarios que tienen su buzón en Exchange Server.

1. Los mensajes de correo de voz se entregan al buzón de correo Exchange usuario a través de SMTP enrutados a través de Exchange Online Protection. Para habilitar la entrega correcta de estos mensajes, asegúrese de que los conectores Exchange están configurados correctamente entre los servidores Exchange y Exchange Online Protection. Para obtener más información, vea [Usar conectores para configurar el correo Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Para habilitar características de correo de voz como personalizar saludos y correo de voz visual en clientes Teams, debe configurar la conectividad entre Microsoft 365 y el buzón Exchange Server correo. Para habilitar esta conectividad, debe configurar el nuevo protocolo de autenticación de Oauth de Exchange descrito en Configurar autenticación [de OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help) entre organizaciones de Exchange y Exchange Online, o ejecutar el Asistente híbrido de Exchange desde Exchange 2013 CU5 o posterior. También debe configurar la integración y Oauth entre Teams y Exchange Server se describe en Configurar integración y [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises) entre Teams y Exchange Server.


## <a name="enable-protected-voicemail-in-your-organization"></a>Habilitar el correo de voz protegido en su organización

Cuando alguien deja un mensaje de correo de voz para un usuario de su organización, el correo de voz se entrega al buzón del usuario como datos adjuntos de un mensaje de correo electrónico. Si usa reglas de flujo de correo para aplicar el cifrado de mensajes, puede evitar que esos mensajes de correo de voz se reenván a otros destinatarios. Al habilitar el correo de voz protegido, los usuarios pueden escuchar mensajes de correo de voz protegidos llamando a su buzón de voz o abriendo el mensaje en Outlook, Outlook en la Web o en Outlook para Android o iOS. Los mensajes de correo de voz protegidos no se pueden abrir en Skype Empresarial o Microsoft Teams.

Para obtener más información sobre el cifrado de mensajes, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).



## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Ayudar a los usuarios a obtener información sobre Correo de voz en la nube características

Para ayudar a los usuarios a obtener información sobre cómo usar y administrar Correo de voz en la nube características, puede recomendar los siguientes artículos: 

- [Compruebe el correo de voz en Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Administrar la configuración de la llamada en Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
