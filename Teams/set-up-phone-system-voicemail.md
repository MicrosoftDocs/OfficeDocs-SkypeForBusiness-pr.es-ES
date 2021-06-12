---
title: Configurar el Correo de voz en la nube
author: dstrome
ms.author: dstrome
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Obtenga información sobre cómo configurar Correo de voz en la nube para los usuarios. '
ms.openlocfilehash: c6fbd02e30c5be0280b05088a1cec281c2534039
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901917"
---
# <a name="set-up-cloud-voicemail"></a>Configurar el Correo de voz en la nube

Este artículo es para el administrador Microsoft 365 o Office 365 como se describe en Acerca de los [roles](/microsoft-365/admin/add-users/about-admin-roles) de administrador que desea configurar la característica Correo de voz en la nube para todos los usuarios de la empresa.

> [!NOTE]
> Correo de voz en la nube permite depositar mensajes de correo de voz solo en un buzón de correo Exchange y no es compatible con ningún sistema de correo electrónico de terceros. 

> [!NOTE]
> Cuando un delegado responde a una llamada en nombre de un delegado, las notificaciones no están disponibles en Correo de voz en la nube. Los usuarios pueden recibir notificaciones de llamadas perdidas.

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a>Entornos solo en la nube: Configurar Correo de voz en la nube para usuarios Sistema telefónico en línea

Para los usuarios Sistema telefónico online, Correo de voz en la nube se configura y aprovisiona automáticamente para los usuarios después de asignar una **Sistema telefónico** a los usuarios. 

> [!NOTE]
> Para usuarios Skype Empresarial Sistema telefónico en línea con números de teléfono proporcionados localmente, es posible que tenga que habilitar el correo de voz hospedado con [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps). 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar Correo de voz en la nube usuarios Exchange Server buzón de correo

La siguiente información es sobre cómo configurar Correo de voz en la nube para trabajar con usuarios que están en línea para Sistema telefónico pero tienen su buzón en Exchange Server. 
  
1. Los mensajes de correo de voz se entregan a los buzones Exchange los usuarios a través de SMTP enrutados a través de Exchange Online Protection. Para habilitar la entrega correcta de estos mensajes, asegúrese de que los conectores Exchange están configurados correctamente entre los servidores Exchange y Exchange Online Protection; [Usar conectores para configurar el correo Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow). 

2. Para habilitar características de correo de voz como personalizar saludos y correo de voz visual en clientes Skype Empresarial, se requiere conectividad de Microsoft 365 o Office 365 al buzón de servidor de Exchange a través de Exchange Servicios web. Para habilitar esta conectividad, debe configurar el nuevo protocolo de autenticación de Oauth de Exchange descrito en Configurar autenticación [de OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)entre organizaciones de Exchange y Exchange Online, o ejecutar el Asistente híbrido de Exchange desde Exchange 2013 CU5 o posterior. Además, debe configurar la integración y Oauth entre Skype Empresarial Online y un servidor Exchange descrito en Configurar integración y [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)entre Skype Empresarial Online y Exchange Server . 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a>Configurar Correo de voz en la nube usuarios Skype Empresarial Server usuarios

Para configurar Skype Empresarial de servidor para Correo de voz en la nube, consulte Planear Correo de voz en la nube para usuarios [locales.](/skypeforbusiness/hybrid/plan-cloud-voicemail)

## <a name="enabling-protected-voicemail-in-your-organization"></a>Habilitar el correo de voz protegido en su organización

Cuando alguien deja un mensaje de correo de voz para un usuario de su organización, el correo de voz se entrega al buzón del usuario como datos adjuntos de un mensaje de correo electrónico. Si usa reglas de flujo de correo para aplicar el cifrado de mensajes, puede evitar que esos mensajes de correo de voz se reenván a otros destinatarios. Al habilitar el correo de voz protegido, los usuarios pueden escuchar mensajes de correo de voz protegidos llamando a su buzón de voz o abriendo el mensaje en Outlook, Outlook en la web o en Outlook para Android o iOS. Los mensajes de correo de voz protegidos no se pueden abrir en Skype Empresarial o Microsoft Teams.

Para obtener más información sobre el cifrado de mensajes, vea [Cifrado de correo electrónico.](/microsoft-365/compliance/email-encryption?view=o365-worldwide)

Para configurar el correo de voz protegido, haga lo siguiente:

1. Vaya a https://admin.microsoft.com e inicie sesión con una cuenta con permisos de administrador global.
2. Seleccione **Mostrar todo y,** a continuación, vaya a Centros **de**  >  **administración Exchange**.
3. En el Centro Exchange administración, seleccione **Reglas de flujo de**  >  **correo.**
4. Seleccione **+** **Agregar** y, a continuación, seleccione **Aplicar Cifrado de mensajes de Office 365 protección de derechos y derechos a los mensajes.**
5. Proporcione un nombre para la nueva regla de flujo de correo y, a continuación, en Aplicar **esta** regla si , seleccione Las propiedades del mensaje Incluya el tipo  >  **de mensaje Correo** de  >  **voz.** Seleccione **Aceptar**.
6. En **Hacer lo siguiente,** seleccione **Aplicar Cifrado de mensajes de Office 365 protección** de derechos y derechos al mensaje con y, a continuación, seleccione **Seleccionar uno**. En **Plantilla RMS,** seleccione **No reenviar**. Seleccione **Aceptar** y, a **continuación, Guardar**.
    > [!NOTE]
    > Si la **lista de plantillas rms** está vacía, debe configurar el cifrado de mensajes. Para obtener más información sobre cómo configurar el cifrado de mensajes, vea los siguientes artículos:
    > - [Configurar nuevas funcionalidades de cifrado de mensajes](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [Configurar y administrar plantillas para Azure Information Protection](/information-protection/deploy-use/configure-policy-templates)
    > - [Opción No reenviar para correos electrónicos](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="help-your-users-learn-teams-voicemail-features"></a>Ayudar a los usuarios a aprender Teams de correo de voz

Tenemos la siguiente información para los usuarios sobre cómo administrar la configuración del correo de voz, así como otras características de llamadas en Teams:

- [Administre la configuración de la llamada en Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f). En este artículo se explica cómo administrar todas las características de llamadas de Teams usuario final. 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a>Ayudar a los usuarios a aprender acerca de las características del correo de voz de Skype Empresarial

Tenemos información de aprendizaje y artículos para ayudar a los usuarios a tener éxito con Skype Empresarial correo de voz. Pídales que consulten los siguientes artículos:

- [Comprobar Skype Empresarial](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8)correo de voz y opciones: en este artículo se explica cómo escuchar el correo de voz en Skype Empresarial, cambiar el saludo de correo de voz, cambiar la configuración del correo de voz y escuchar el correo de voz a diferentes velocidades.

- [Aprendizaje de Skype Empresarial 2016](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a>Temas relacionados
[Configurar Skype Empresarial Online](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[Esto es lo obtiene con el Sistema telefónico](here-s-what-you-get-with-phone-system.md)

[Planificar la migración de Skype Empresarial Server y Exchange Server](/SkypeForBusiness/hybrid/plan-um-migration)
