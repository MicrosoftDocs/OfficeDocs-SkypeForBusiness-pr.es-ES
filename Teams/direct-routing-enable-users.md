---
title: Habilitar a los usuarios para el enrutamiento directo
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
description: Aprenda a habilitar el enrutamiento directo de los usuarios de Microsoft Phone.
ms.openlocfilehash: f89133b5205dc77f8045c484b97d3049773c28e2
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814549"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a>Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz

En este artículo se describe cómo habilitar a los usuarios para el enrutamiento directo del sistema telefónico.  Este es el paso 2 de los siguientes pasos para configurar el enrutamiento directo:

- Paso 1. [Conectar el SBC con Microsoft Phone System y validar la conexión](direct-routing-connect-the-sbc.md) 
- **Paso 2. Habilitar a los usuarios para el enrutamiento directo, la voz y el buzón de voz**   (este artículo)
- Paso 3. [Configurar el enrutamiento de voz](direct-routing-voice-routing.md)
- Paso 4. [Traducir números a un formato alternativo](direct-routing-translate-numbers.md) 


Para obtener información sobre todos los pasos necesarios para configurar el enrutamiento directo, consulte [configurar el enrutamiento directo](direct-routing-configure.md).

Cuando esté listo para habilitar a los usuarios para el enrutamiento directo, siga estos pasos: 

1. Cree un usuario en Microsoft 365 u Office 365 y asigne una licencia de sistema telefónico. 
2. Asegúrese de que el usuario se ha alojado en Skype empresarial online. 
3. Configure el número de teléfono y habilite la telefonía IP empresarial y el buzón de voz. 
4. Asigne el modo solo de Teams a los usuarios.

## <a name="create-a-user-and-assign-the-license"></a>Crear un usuario y asignar la licencia 

Existen dos opciones para crear un nuevo usuario en Microsoft 365 u Office 365. Sin embargo, Microsoft recomienda que su organización elija una opción para evitar problemas de enrutamiento: 

- Crear el usuario en Active Directory local y sincronizar el usuario con la nube. Consulte [integrar los directorios locales con Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
- Cree directamente el usuario en el centro de administración de Microsoft 365. Consulte [Agregar usuarios individualmente o de forma masiva a Microsoft 365 u Office 365: ayuda de administración](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec). 

Si su implementación de Skype empresarial online coexiste con Skype empresarial 2015 o Lync 2010 o 2013 local, la única opción admitida es crear el usuario en Active Directory local y sincronizar el usuario con la nube (opción 1). 

Para obtener información sobre los requisitos de licencia, consulte [licencias y otros requisitos](direct-routing-plan.md#licensing-and-other-requirements) en [planificar enrutamiento directo](direct-routing-plan.md).

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a>Asegúrese de que el usuario está conectado y el número de teléfono no se sincroniza desde local (aplicable para Skype empresarial Server Enterprise Voice habilitado los usuarios que se migran a un enrutamiento directo de Teams)

El enrutamiento directo requiere que el usuario se conecte en línea. Puede consultar el parámetro RegistrarPool, que necesita tener un valor en el dominio de infra.lync.com. El parámetro OnPremLineUriManuallySet debe establecerse también en true. Esto se logra configurando el número de teléfono y habilitando la telefonía IP empresarial y el buzón de voz con Skype empresarial online PowerShell.

1. Conectar una sesión de PowerShell de Skype empresarial online.

2. Emita el comando: 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    En caso de que OnPremLineUriManuallySet se haya establecido en false y LineUri se haya rellenado con un <E. 164 número de teléfono>, limpie los parámetros con el shell local de administración de Skype empresarial antes de configurar el número de teléfono con Skype empresarial online PowerShell. 

1. Desde el shell de administración de Skype empresarial, ejecute el comando: 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   Una vez que los cambios se han sincronizado con Office 365, el resultado esperado `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` es:

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>Configurar el número de teléfono y habilitar la telefonía IP empresarial y el buzón de voz 

Una vez que haya creado el usuario y haya asignado una licencia, el siguiente paso es configurar el número de teléfono del usuario y el buzón de voz. 

Para agregar el número de teléfono y habilitar el buzón de voz:
 
1. Conectar una sesión de PowerShell de Skype empresarial online. 

2. Emita el comando: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```
    
    Por ejemplo, para agregar un número de teléfono para el usuario "Spencer Low", escriba lo siguiente: 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    El número de teléfono usado debe configurarse como un número de teléfono E. 164 completo con prefijo internacional. 

    > [!NOTE]
    > Si el número de teléfono del usuario se administra localmente, use el shell local de administración de Skype empresarial o el panel de control para configurar el número de teléfono del usuario. 


## <a name="configuring-sending-calls-directly-to-voicemail"></a>Configurar el envío de llamadas directamente al buzón de voz

El enrutamiento directo le permite finalizar la llamada a un usuario y enviarlo directamente al buzón de voz del usuario. Si deseas enviar la llamada directamente al buzón de voz, adjunta Opaque = App: el buzón de voz al encabezado de URI de la solicitud. Por ejemplo, "SIP: user@yourdomain. com; Opaque = App: buzón de voz". En este caso, el usuario de Teams no recibirá la notificación de llamada, la llamada se conectará al buzón de voz del usuario directamente.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Asignar el modo solo de Teams a los usuarios para garantizar la superficie de llamadas en Microsoft Teams

El enrutamiento directo requiere que los usuarios estén en el modo solo de equipos para garantizar las llamadas entrantes en el cliente de Teams. Para poner los usuarios en modo de solo equipos, asígnelos a la instancia "UpgradeToTeams" de TeamsUpgradePolicy. Para obtener más información, consulte [Guía de actualización para administradores de ti](upgrade-to-teams-on-prem-overview.md). Si su organización usa Skype empresarial Server o Skype empresarial online, consulte el artículo siguiente para obtener información sobre la interoperabilidad entre Skype y Teams: [migración y interoperabilidad con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md).

## <a name="see-also"></a>Vea también

[Planear el enrutamiento directo](direct-routing-plan.md)

[Configurar el enrutamiento directo](direct-routing-configure.md)
