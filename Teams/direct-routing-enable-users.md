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
description: Obtenga información sobre cómo habilitar el enrutamiento directo de Microsoft Phone System para los usuarios.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655496"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Habilitar usuarios para enrutamiento directo, voz y correo de voz

En este artículo se describe cómo habilitar a los usuarios para el enrutamiento directo de sistema telefónico.  Este es el paso 2 de los siguientes pasos para configurar el enrutamiento directo:

- Paso 1. [Conectar el SBC con Microsoft Phone System y validar la conexión](direct-routing-connect-the-sbc.md) 
- **Paso 2. Habilitar a los usuarios para enrutamiento directo, voz y correo de**   voz (en este artículo)
- Paso 3. [Configurar el enrutamiento de voz](direct-routing-voice-routing.md)
- Paso 4. [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 


Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, vea [Configurar enrutamiento directo.](direct-routing-configure.md)

Cuando esté listo para habilitar a los usuarios para enrutamiento directo, siga estos pasos: 

1. Cree un usuario en Microsoft 365 u Office 365 y asigne una licencia de Sistema telefónico. 
2. Asegúrese de que el usuario está en Skype Empresarial Online. 
3. Configure el número de teléfono y habilite la voz de empresa y el correo de voz. 
4. Asignar el modo Solo equipos a los usuarios.

## <a name="create-a-user-and-assign-the-license"></a>Crear un usuario y asignar la licencia 

Hay dos opciones para crear un nuevo usuario en Microsoft 365 u Office 365. Sin embargo, Microsoft recomienda que su organización elija una opción para evitar problemas de enrutamiento: 

- Cree el usuario en Active Directory local y sincronice el usuario con la nube. Consulte [Integrar los directorios locales con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- Cree el usuario directamente en el Centro de administración de Microsoft 365. Vea [Agregar usuarios individualmente o de forma masiva a Microsoft 365 u Office 365: ayuda para administradores.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) 

Si su implementación de Skype Empresarial Online coexiste con Skype Empresarial 2015 o Lync 2010 o 2013 local, la única opción admitida es crear el usuario en la implementación local de Active Directory y sincronizar el usuario con la nube (opción 1). 

Para obtener información sobre los requisitos de licencia, vea [licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements) en [Plan de enrutamiento directo.](direct-routing-plan.md)

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Asegúrese de que el usuario está conectado y que el número de teléfono no se sincroniza desde la implementación local (aplicable a los usuarios con Skype Empresarial Server Telefonía IP empresarial que se están migrando a Enrutamiento directo de Teams)

El enrutamiento directo requiere que el usuario esté conectado. Para comprobarlo, consulte el parámetro RegistrarPool, que debe tener un valor en el dominio infra.lync.com registro. El parámetro OnPremLineUriManuallySet también debe establecerse en True. Para ello, configure el número de teléfono y habilite el correo de voz empresarial y el correo de voz con PowerShell de Skype Empresarial Online.

1. Conectar una sesión de PowerShell de Skype Empresarial Online.

2. Ejecute el comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    Si OnPremLineUriManuallySet se establece en False y LineUri se rellena con un número de teléfono> E.164 de <, limpie los parámetros con el Shell de administración local de Skype Empresarial antes de configurar el número de teléfono con PowerShell de Skype Empresarial Online. 

1. Desde el shell de administración de Skype Empresarial, ejecute el comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   Una vez que los cambios se han sincronizado con Office 365, el resultado esperado `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sería:

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

2. Ejecute el comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    Por ejemplo, para agregar un número de teléfono para el usuario "Entresa bajo", escriba lo siguiente: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    Si los usuarios "Low" y "Stacy Corp" comparten el mismo número base con extensiones únicas, escribe lo siguiente
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    Se recomienda, pero no es necesario, que el número de teléfono usado esté configurado como un número de teléfono E.164 completo con código de país. Es compatible con configurar números de teléfono con extensiones que se usarán para buscar usuarios cuando la búsqueda en el número base devuelva más de un resultado. Esto permite a las compañías configurar números de teléfono con el mismo número base y extensiones únicas. Para que la búsqueda se realice correctamente, la invitación debe incluir el número completo con extensión de la siguiente manera:
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > Si el número de teléfono del usuario se administra de forma local, use el Shell de administración local de Skype Empresarial o el Panel de control para configurar el número de teléfono del usuario. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurar el envío de llamadas directamente al correo de voz

El enrutamiento directo le permite finalizar la llamada a un usuario y enviarla directamente al correo de voz del usuario. Si quiere enviar la llamada directamente al correo de voz, adjunte opaque=app:voicemail al encabezado del URI de solicitud. Por ejemplo, "sip:user@yourdomain.com;opaque=app:voicemail". En este caso, el usuario de Teams no recibirá la notificación de llamada, la llamada se conectará al correo de voz del usuario directamente.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Asignar el modo Solo de Teams a los usuarios para garantizar que las llamadas se des fijos en Microsoft Teams

El enrutamiento directo requiere que los usuarios se ajusten al modo Solo en Teams para garantizar que las llamadas entrantes se agregó al cliente de Teams. Para poner a los usuarios en el modo solo de Teams, asígneles la instancia "UpgradeToTeams" de TeamsUpgradePolicy. Para obtener más información, vea [las instrucciones de actualización para administradores de TI.](upgrade-to-teams-on-prem-overview.md) Si su organización usa Skype Empresarial Server o Skype Empresarial Online, consulte el siguiente artículo para obtener información sobre interoperabilidad entre Skype y Teams: migración e interoperabilidad [con Skype Empresarial.](migration-interop-guidance-for-teams-with-skype.md)

## <a name="see-also"></a>Consulte también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
