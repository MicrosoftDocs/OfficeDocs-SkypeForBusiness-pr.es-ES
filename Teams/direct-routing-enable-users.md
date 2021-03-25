---
title: Habilitar usuarios para enrutamiento directo
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo habilitar el enrutamiento directo de Microsoft Phone System a los usuarios.
ms.openlocfilehash: 858b9073106945d414c2dbe56a16e6cecd104ee7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122224"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Habilitar usuarios para enrutamiento directo, voz y correo de voz

En este artículo se describe cómo habilitar los usuarios para el enrutamiento directo del sistema telefónico.  Este es el paso 2 de los pasos siguientes para configurar enrutamiento directo:

- Paso 1. [Conectar el SBC con Microsoft Phone System y validar la conexión](direct-routing-connect-the-sbc.md) 
- **Paso 2. Habilitar usuarios para enrutamiento directo, voz y correo de voz**   (este artículo)
- Paso 3. [Configurar el enrutamiento de voz](direct-routing-voice-routing.md)
- Paso 4. [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 


Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)

Cuando esté listo para habilitar usuarios para enrutamiento directo, siga estos pasos: 

1. Cree un usuario en Microsoft 365 u Office 365 y asigne una licencia de Sistema telefónico. 
2. Asegúrese de que el usuario se encuentra en Skype Empresarial Online. 
3. Configure el número de teléfono y habilite la voz empresarial y el correo de voz. 
4. Asignar el modo Solo teams a los usuarios.

## <a name="create-a-user-and-assign-the-license"></a>Crear un usuario y asignar la licencia 

Hay dos opciones para crear un nuevo usuario en Microsoft 365 u Office 365. Sin embargo, Microsoft recomienda que su organización elija una opción para evitar problemas de enrutamiento: 

- Cree el usuario en Active Directory local y sincronice el usuario con la nube. Vea [Integrar los directorios locales con Azure Active Directory.](/azure/active-directory/connect/active-directory-aadconnect)
- Cree el usuario directamente en el Centro de administración de Microsoft 365. Vea [Agregar usuarios individualmente o en masa a Microsoft 365 u Office 365: Ayuda para administradores.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) 

Si su implementación de Skype Empresarial Online coexiste con Skype Empresarial 2015 o Lync 2010 o 2013 local, la única opción compatible es crear el usuario en el Active Directory local y sincronizar el usuario con la nube (opción 1). 

Para obtener información sobre los requisitos de licencia, vea [Licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements) en [Plan de enrutamiento directo.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Asegúrese de que el usuario está conectado y que el número de teléfono no se sincroniza desde local (aplicable para Skype Empresarial Server Telefonía IP empresarial usuarios habilitados que se migran a Enrutamiento directo de Teams)

Enrutamiento directo requiere que el usuario esté conectado. Para comprobarlo, consulte el parámetro RegistrarPool, que debe tener un valor en el infra.lync.com usuario. El parámetro OnPremLineUriManuallySet también debe establecerse en True. Esto se consigue configurando el número de teléfono y habilitando la voz empresarial y el correo de voz con PowerShell de Skype Empresarial Online.

1. Conectar una sesión de PowerShell de Skype Empresarial Online.

2. Publique el comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    En caso de que OnPremLineUriManuallySet se establezca en False y LineUri se rellene con un número de teléfono <E.164>, limpie los parámetros con el Shell de administración de Skype Empresarial local, antes de configurar el número de teléfono con PowerShell de Skype Empresarial Online. 

1. Desde el Shell de administración de Skype Empresarial se emite el comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   Después de que los cambios se sincronicen con Office 365, el resultado esperado `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sería:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurar el número de teléfono y habilitar la voz y el correo de voz empresariales 

Después de crear el usuario y asignar una licencia, el siguiente paso es configurar el número de teléfono y el correo de voz del usuario. 

Para agregar el número de teléfono y habilitar el correo de voz:
 
1. Conectar una sesión de PowerShell de Skype Empresarial Online. 

2. Publique el comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Por ejemplo, para agregar un número de teléfono para el usuario "Spencer Low", escriba lo siguiente: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Si los usuarios "Spencer Low" y "Stacy Quinn" comparten el mismo número base con extensiones únicas, escriba lo siguiente
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Se recomienda, pero no necesario, que el número de teléfono usado esté configurado como un número de teléfono E.164 completo con código de país. Es compatible con configurar números de teléfono con extensiones que se usarán para buscar usuarios cuando la búsqueda en el número base devuelva más de un resultado. Esto permite a las empresas configurar números de teléfono con el mismo número base y extensiones únicas. Para que la búsqueda se realice correctamente, la invitación debe incluir el número completo con la extensión de la siguiente manera:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Si el número de teléfono del usuario se administra localmente, use el Shell de administración local de Skype Empresarial o el Panel de control para configurar el número de teléfono del usuario. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurar el envío de llamadas directamente al correo de voz

Enrutamiento directo le permite finalizar la llamada a un usuario y enviarla directamente al correo de voz del usuario. Si desea enviar la llamada directamente al correo de voz, adjunte opaque=app:voicemail al encabezado Solicitar URI. Por ejemplo, "sip:user@yourdomain.com;opaque=app:voicemail". En este caso, el usuario de Teams no recibirá la notificación de llamada, la llamada se conectará directamente al correo de voz del usuario.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Asignar el modo Solo teams a los usuarios para asegurarse de que las llamadas se aterrice en Microsoft Teams

Enrutamiento directo requiere que los usuarios se en modo solo de Teams para garantizar que las llamadas entrantes se aterrice en el cliente de Teams. Para poner a los usuarios en modo solo de Teams, asígneles la instancia "UpgradeToTeams" de TeamsUpgradePolicy. Para obtener más información, vea [Estrategias de actualización para administradores de TI.](upgrade-to-teams-on-prem-implement.md) Si su organización usa Skype Empresarial Server o Skype Empresarial Online, vea el siguiente artículo para obtener información sobre la interoperabilidad entre Skype y Teams: Migración e interoperabilidad con [Skype Empresarial.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)