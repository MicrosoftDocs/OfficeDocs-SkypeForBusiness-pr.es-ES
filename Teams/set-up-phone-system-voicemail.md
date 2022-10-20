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
- highpri
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
ms.openlocfilehash: f73587fe2fe9a9449d938d9eac3d6193bbd7aa47
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614473"
---
# <a name="set-up-cloud-voicemail"></a>Configurar el Correo de voz en la nube

Este artículo es para administradores de Microsoft 365 que quieran configurar Correo de voz en la nube para sus usuarios.

Correo de voz en la nube deposita mensajes de correo de voz en el buzón de exchange de un usuario. Correo de voz en la nube no admite sistemas de correo electrónico de terceros. Para obtener Exchange Online requisitos de licencia, consulte [Exchange Online descripción del servicio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description#features-available-to-all-plans). Para obtener más información sobre los roles de administrador, vea [Acerca de los roles de administrador](/microsoft-365/admin/add-users/about-admin-roles).

## <a name="cloud-voicemail-provisioning"></a>aprovisionamiento de Correo de voz en la nube

Para los usuarios de Teams, Correo de voz en la nube se configura y aprovisiona automáticamente. *No es necesaria una licencia de Teléfono Microsoft Teams para Correo de voz en la nube.*

El aprovisionamiento para usuarios de Teams no es lo mismo que para los usuarios de Skype Empresarial En línea. Para los usuarios de Skype Empresarial Online, Correo de voz en la nube se configuró y aprovisionó automáticamente cuando se asignó una licencia de Sistema telefónico a los usuarios y el sistema de aprovisionamiento Telefonía IP empresarial habilitado.

Para Skype Empresarial Server usuarios locales, Correo de voz en la nube se configura y aprovisiona automáticamente. Sin embargo, debe configurar el entorno Skype Empresarial Server para redirigir las llamadas a Correo de voz en la nube. Para obtener más información, vea [Planear el servicio de Correo de voz en la nube para usuarios locales](/skypeforbusiness/hybrid/plan-cloud-voicemail).

## <a name="cloud-voicemail-storage"></a>almacenamiento de Correo de voz en la nube

Los mensajes de correo de voz generados por Correo de voz en la nube se entregan y se almacenan en el buzón de Exchange del usuario, ya sea en Exchange Online o en Exchange Server. No hay almacenamiento específico o adicional para el correo de voz. Los clientes que tienen acceso al correo de voz (por ejemplo, Microsoft Outlook, Microsoft Teams o Skype Empresarial) lo hacen a través del buzón de Exchange y de las API proporcionadas.

Un mensaje de correo de voz contiene un archivo de audio adjunto con los mensajes de voz y la transcripción del correo de voz (si está habilitado).

El buzón de Exchange de un usuario almacena los saludos grabados personalizados. Correo de voz en la nube recupera estos saludos según sea necesario durante una llamada entrante.

## <a name="cloud-voicemail-processing"></a>procesamiento de Correo de voz en la nube

La grabación y transcripción de Correo de voz en la nube comienza en Microsoft 365 en el origen de la llamada que se dirige a Correo de voz en la nube. A continuación, el mensaje se entrega al buzón de Exchange del usuario.

Por ejemplo, si una llamada llega a un usuario de enrutamiento directo no disponible a través de un controlador de borde de sesión (SBC) en Europa, la grabación y la transcripción del correo de voz se realizan en Europa. A continuación, el mensaje se entrega al buzón de Exchange del usuario. Por otro ejemplo, supongamos que un usuario de Teams en Norteamérica llama a un usuario de Teams que no está disponible en Europa. En este caso, la llamada se inicia en Norteamérica, el procesamiento se produce en Norteamérica y, a continuación, el correo de voz se entrega al buzón de Exchange del usuario en Europa.

La entrega de un correo de voz a un buzón de Exchange se realiza mediante el protocolo simple de transporte de correo (SMTP) como cualquier otro correo electrónico.

## <a name="manage-cloud-voicemail-for-users"></a>Administrar Correo de voz en la nube para usuarios

Puede administrar Correo de voz en la nube para los usuarios especificando las directivas del correo de voz y configurando las opciones del correo de voz.  

- **Las directivas de correo de voz** le permiten administrar características para grupos de usuarios. Puede configurar y asignar directivas de correo de voz nuevas o existentes para características como reglas de respuesta de llamadas, transcripción del correo de voz, enmascaramiento de lenguaje profanado de transcripción, traducción de transcripción e idioma de mensaje del sistema. Para obtener información sobre cómo administrar directivas de correo de voz, vea [Administrar directivas de correo de voz](manage-voicemail-policies.md).

- **La configuración del correo de voz** le permite configurar opciones para usuarios individuales. Puede configurar opciones como las reglas de respuesta de llamadas, el idioma del mensaje, el texto a voz predeterminado y los saludos de vacaciones. Para obtener información sobre cómo configurar las opciones para usuarios individuales, consulte [Administrar la configuración del correo de voz](manage-voicemail-settings.md). Tenga en cuenta que los usuarios finales también pueden configurar estas opciones en el cliente de Teams yendo a **Configuración -> Llamadas -> Configurar correo de voz**.

## <a name="control-routing-of-calls-to-cloud-voicemail"></a>Controlar el enrutamiento de llamadas a Correo de voz en la nube

La configuración predeterminada para todos los usuarios aprovisionados para Correo de voz en la nube es permitir el enrutamiento de llamadas a Correo de voz en la nube y permitir que los usuarios desvíen llamadas a Correo de voz en la nube.

Puede controlar si se permite el enrutamiento de llamadas a Correo de voz en la nube para los usuarios de Teams mediante el Centro de administración de Teams o mediante PowerShell. 

- Para usar el Centro de administración de Teams, vaya a **Directivas de llamadas** de **voz** ->  > agregar una directiva nueva o editar una directiva existente > **correo de voz está disponible para enrutar llamadas entrantes**.  

- En PowerShell, use el cmdlet de Set-CsTeamsCallingPolicy con el parámetro AllowVoicemail. Para obtener más información, consulte [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

  - Si establece AllowVoicemail en AlwaysDisabled, las llamadas nunca se enrutan al correo de voz, independientemente de la configuración de desvío de llamadas o de la configuración no respondida de un usuario. El correo de voz no está disponible como opción de desvío de llamadas o no respondida en Teams.

  - Si establece AllowVoicemail en AlwaysEnabled, las llamadas siempre se desván al correo de voz en una respuesta después de llamar durante treinta segundos, independientemente de la configuración de desvío de llamadas no respondidas de un usuario.

  - Si establece AllowVoicemail en UserOverride, las llamadas se desvian al correo de voz en función de la configuración de desvío de llamadas y/o sin responder de un usuario.

## <a name="set-up-cloud-voicemail-to-work-with-on-premises-users"></a>Configurar Correo de voz en la nube para trabajar con usuarios locales

Puede usar Correo de voz en la nube para proporcionar funcionalidad de correo de voz para los usuarios que tienen buzones en los servidores de Exchange o para los usuarios que usan Skype Empresarial Server.

En esta sección se describe cómo configurar Correo de voz en la nube para los usuarios del buzón de Exchange Server. Para obtener información sobre cómo configurar Correo de voz en la nube para usuarios de Skype Empresarial Server, vea [Planear el servicio de Correo de voz en la nube para usuarios locales](/skypeforbusiness/hybrid/plan-cloud-voicemail).

### <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a>Configurar Correo de voz en la nube para usuarios de buzones de Exchange Server

La siguiente información es sobre cómo configurar Correo de voz en la nube para trabajar con los usuarios de Teams que tienen su buzón en Exchange Server.

1. Los mensajes de correo de voz se entregan al buzón de Exchange de un usuario a través de SMTP enrutados a través de Exchange Online Protection. Para habilitar la entrega correcta de estos mensajes, asegúrese de que los conectores de Exchange están configurados correctamente entre los servidores de Exchange y Exchange Online Protection. Para obtener más información, vea [Usar conectores para configurar el flujo de correo](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

2. Para habilitar las características del correo de voz, como la personalización de saludos y el correo de voz visual en los clientes de Teams, debe configurar la conectividad entre Microsoft 365 y el buzón de Exchange Server. Para habilitar esta conectividad, debe configurar el nuevo protocolo de autenticación de Oauth de Exchange que se describe en [Configurar la autenticación de OAuth entre Exchange y Exchange Online organizaciones](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), o ejecutar el Asistente para la implementación híbrida de Exchange desde la CU5 de Exchange 2013 o superior. También debe configurar la integración y Oauth entre Teams y Exchange Server que se describen en [Configurar integración y OAuth entre Teams y Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).

## <a name="enable-protected-voicemail-in-your-organization"></a>Habilitar el correo de voz protegido en su organización

Cuando alguien deja un mensaje de correo de voz de un usuario de su organización, el correo de voz se entrega al buzón del usuario como datos adjuntos de un mensaje de correo electrónico.

Con Microsoft Purview Information Protection, puede cifrar los mensajes de correo de voz que dejan los autores de llamadas internos y externos. También puede impedir que el usuario reenvíe estos mensajes. Esta característica es compatible con los usuarios con buzones de Exchange Online.

Para cifrar el mensaje de correo de voz, puede crear una etiqueta de confidencialidad. Con la característica de etiquetado automático, puede asegurarse de que la etiqueta se aplicará automáticamente a los mensajes de correo de voz entrantes.

Al habilitar el correo de voz protegido, los usuarios pueden escuchar los mensajes de correo de voz protegido abriendo el mensaje en Outlook, Outlook en la Web o Outlook para Android o iOS. Los mensajes de correo de voz protegidos no se pueden abrir en Microsoft Teams ni Skype Empresarial.

Para crear una etiqueta de confidencialidad para el correo de voz, vea [Usar etiquetas de confidencialidad](/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions). En la sección **Cifrado** , elija **Permitir que los usuarios asignen permisos al aplicar la etiqueta**. Seleccione **En Outlook, aplique una de las siguientes restricciones** y, a continuación, seleccione la opción **No reenviar** .

Para crear la directiva de etiquetado automático para aplicar una etiqueta de confidencialidad al correo de voz, consulte [Cómo configurar directivas de etiquetado automático](/microsoft-365/compliance/apply-sensitivity-label-automatically#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange) y especifique las siguientes opciones específicas:

- En **Elegir la información a la que desea aplicar esta etiqueta**, seleccione **Directiva personalizada**.

- En **Elegir las ubicaciones donde desea aplicar la etiqueta**, seleccione **Ubicaciones: Exchange para todos los usuarios**.

- Para  **Configurar reglas comunes o avanzadas**, selecciona **Reglas avanzadas**.

- Reglas de Exchange:
  - Condiciones:
    - **Patrón de coincidencias de encabezado**: Content-Class = Voice-CA
    - **La dirección IP del remitente es**: 13.107.64.0/18, 52.112.0.0/14, 52.120.0.0/14, 52.238.119.141/32, 52.244.160.207/32

- Para **Elegir una etiqueta para aplicar automáticamente**, seleccione la etiqueta de confidencialidad que creó para el correo de voz en el paso anterior.

- Para obtener **más opciones de configuración para el correo electrónico**, seleccione **Aplicar cifrado al correo electrónico recibido de fuera de la organización** y especifique el propietario de Rights Management.

Los intervalos IP V4 especificados en Dirección IP del remitente se basan en la lista id. 12 de [Office 365 direcciones URL e intervalos de direcciones IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

Para obtener más información sobre el cifrado de mensajes, vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico](/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

## <a name="help-your-users-learn-about-cloud-voicemail-features"></a>Ayudar a los usuarios a obtener información sobre las características de Correo de voz en la nube

Para ayudar a los usuarios a obtener información sobre cómo usar y administrar características de Correo de voz en la nube, puede recomendar los siguientes artículos:

- [Comprobar el correo de voz en Teams](https://support.microsoft.com/office/check-your-voicemail-in-teams-f8d568ce-7329-4fe2-a6a2-325ec2e2b419)
- [Administrar la configuración de llamadas en Teams](https://support.microsoft.com/office/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)
