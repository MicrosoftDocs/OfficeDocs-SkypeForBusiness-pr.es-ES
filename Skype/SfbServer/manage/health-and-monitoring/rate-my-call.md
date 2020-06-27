---
title: Valorar mi llamada en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Resumen: Obtenga información sobre la característica valorar mi llamada en Skype empresarial Server.'
ms.openlocfilehash: 15f2bcbcf75690baaa350541f5f1da134fb32025
ms.sourcegitcommit: a73df97a06ea860bfaf5387e0acbf3c724697e14
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "44902225"
---
# <a name="rate-my-call-in-skype-for-business-server"></a>Valorar mi llamada en Skype empresarial Server

**Resumen:** Obtenga información sobre la característica valorar mi llamada en Skype empresarial Server.

Valorar mi llamada fue una nueva característica de clientes de Skype empresarial 2015 y 2016 en Windows que ofrece a las empresas una forma de obtener comentarios de sus usuarios finales.

La ventana valorar mi llamada ofrece un sistema de clasificación de "estrella" y tokens predefinidos para las llamadas de audio y vídeo. Además, los administradores pueden habilitar un campo personalizado para proporcionar comentarios.

Tasa recopilada mis datos de llamada no están incluidos en el informe de supervisión existente, pero tiene un informe de supervisión independiente. Los datos se recopilan en tablas de SQL a las que se puede tener acceso mediante la ejecución de consultas SQL.

## <a name="rate-my-call-prerequisites"></a>Requisitos previos de valorar mi llamada

Antes de que los usuarios de su implementación de Skype empresarial Server puedan tener acceso a la funcionalidad valorar mi llamada, se debe implementar y configurar el siguiente conjunto de componentes:

-  Debe tener instalado Skype empresarial Server (versión 9160 o posterior).

- Solicite a los usuarios que instalen y actualicen a la versión más reciente de Skype empresarial y pídales que usen la interfaz de usuario de Skype empresarial.

- Los usuarios deben estar hospedados en el grupo de servidores front-end de Skype empresarial Server.

- Debe tener una base de datos de supervisión de Skype empresarial Server implementada y asociada a sus grupos de servidores de Skype empresarial.

- Le recomendamos que implemente el panel de calidad de llamadas (CQD).

## <a name="configure-rate-my-call"></a>Configurar la velocidad de mi llamada

La característica valorar mi llamada está habilitada de forma predeterminada en la Directiva de cliente con la siguiente configuración:

- Valorar el porcentaje de visualización de la llamada en porcentaje-10%

- Valorar mi llamada permitir comentarios personalizados de los usuarios: deshabilitado

Sin embargo, no se requiere ninguna acción para habilitar la característica básica, pero si desea comentarios personalizados tendrá que habilitarla por separado. El siguiente cmdlet de Windows PowerShell es un ejemplo de cómo habilitar los comentarios personalizados del usuario final y cambiar el intervalo de 10% a 80%.

```PowerShell
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 -RateMyCallAllowCustomUserFeedback $true 
```

## <a name="accessing-rate-my-call-data"></a>Obtener acceso a los datos de la tasa de llamada

Los datos de los usuarios se recopilan en dos tablas de la base de datos de supervisión.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Esta tabla contiene los resultados del sondeo de tokens por parte de los usuarios finales.

 **[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Esta tabla contiene definiciones de tokens.

Las definiciones de token se codifican de la siguiente manera:

|||
|:-----|:-----|
|1   <br/> |DistortedSpeech  <br/> |
|2   <br/> | ElectronicFeedback <br/> |
|3   <br/> | BackgroundNoise <br/> |
|4   <br/> |MuffledSpeech  <br/> |
|5   <br/> |Echo  <br/> |
| 21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|veintitrés  <br/> | BlurryImage <br/> |
|apartado  <br/> | PoorColor <br/> |
|IVA  <br/> | DarkVideo <br/> |
|101  <br/> |Audio_SilentLocal  <br/> |
|102  <br/> |Audio_SilentRemote  <br/> |
|103  <br/> |Audio_Echo  <br/> |
|104  <br/> |Audio_BackgroundNoise  <br/> |
|105  <br/> |Audio_LowSound  <br/> |
|106  <br/> |Audio_Dropped  <br/> |
|107  <br/> |Audio_DistortedSpeech  <br/> |
|108  <br/> |Audio_Interrupted  <br/> |
|109  <br/> |Audio_Other  <br/> |
|201  <br/> |Video_NoLocalVideo  <br/> |
|202  <br/> |Video_NoRemoteVideo  <br/> |
|203  <br/> |Video_LowQuality  <br/> |
|204  <br/> |Video_FrozenVideo  <br/> |
|205  <br/> |Video_StoppedUnexpectedly  <br/> |
|206  <br/> |Video_DarkVideo  <br/> |
|207  <br/> |Video_NoAudioSync  <br/> |
|208  <br/> |Video_Other  <br/> |
|301  <br/> |Pstn_DialPad  <br/> |
|401  <br/> |SS_NoContentLocal  <br/> |
|402  <br/> |SS_NoContentRemote  <br/> |
|403  <br/> |SS_CantPresent  <br/> |
|404  <br/> |SS_LowQuality  <br/> |
|405  <br/> |SS_Freezing  <br/> |
|406  <br/> |SS_StoppedUnexpectedly  <br/> |
|407  <br/> |SS_LargeDelay  <br/> |
|408  <br/> |SS_Other  <br/> |
|501  <br/> |Reliabilty_Join  <br/> |
|502  <br/> |Reliabilty_Invite  <br/> |

 **[QoeMetrics]. [dbo]. [CallQualityFeedback]** Esta tabla contiene los resultados de sondeo de la votación "en estrella" y los comentarios de los clientes si están habilitados.

Se puede llamar a los datos de las tablas mediante una consulta **SELECT \* from [Table.Name]** o mediante Microsoft SQL Server Management Studio.

Se pueden usar las siguientes consultas SQL:

 **Audio**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [AudioStream] AS a WITH (NOLOCK) ON -- only look at Audio related feedback
            a.MediaLineLabel = m.MediaLineLabel    
            and a.ConferenceDateTime = m.ConferenceDateTime 
            and a.SessionSeq = m.SessionSeq
            and a.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
            (CallerCqfToken.TokenId < 20 or (CallerCqfToken.TokenId > 100 and CallerCqfToken.TokenId < 200)) -- only look at Audio related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

 **Video**

```SQL
SELECT
        s.ConferenceDateTime
        ,Caller.URI as Caller
        ,CallerCqf.FeedbackText 
        ,CallerCqf.Rating
        ,CallerCqfTokenDef.TokenDescription 
        ,CallerCqfToken.TokenValue
    FROM [Session] s WITH (NOLOCK)
        INNER JOIN [MediaLine] AS m WITH (NOLOCK) ON 
            m.ConferenceDateTime = s.ConferenceDateTime
            AND m.SessionSeq = s.SessionSeq                        
        INNER JOIN [VideoStream] AS v WITH (NOLOCK) ON -- only look at Video related feedback
            v.MediaLineLabel = m.MediaLineLabel    
            and v.ConferenceDateTime = m.ConferenceDateTime 
            and v.SessionSeq = m.SessionSeq
            and v.SenderIsCallerPAI = 1                
        INNER JOIN [CallQualityFeedback] AS CallerCqf WITH (NOLOCK) ON
            CallerCqf.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqf.SessionSeq = s.SessionSeq 
        INNER JOIN [CallQualityFeedbackToken] AS CallerCqfToken WITH (NOLOCK) ON
            CallerCqfToken.ConferenceDateTime  = s.ConferenceDateTime 
            and
            CallerCqfToken.SessionSeq = s.SessionSeq
            and
            CallerCqfToken.FromURI = CallerCqf.FromURI
        INNER JOIN [CallQualityFeedbackTokenDef] AS CallerCqfTokenDef WITH (NOLOCK) ON
            CallerCqfTokenDef.TokenId = CallerCqfToken.TokenId
            and
           ((CallerCqfToken.TokenId > 20 and CallerCqfToken.TokenId < 100) or (CallerCqfToken.TokenId > 200 and CallerCqfToken.TokenId < 300)) -- only look at Video related feedback
        INNER JOIN [User] AS Caller WITH (NOLOCK) ON
            Caller.UserKey = CallerCqf.FromURI
```

## <a name="updating-token-definitions"></a>Actualización de definiciones de tokens

Los clientes más recientes de Skype empresarial notifican nuevos identificadores de token de problema ( \> 100) que pueden no estar presentes en su [QoeMetrics]. [ DBO]. Tabla [CallQualityFeedbackTokenDef]. Para actualizar la tabla de base de datos con las definiciones de token más recientes, el siguiente comando SQL puede ejecutarse en la base de datos de supervisión con Microsoft SQL Server Management Studio. Este comando reemplazará todas las entradas de [QoeMetrics]. [dbo]. Tabla [CallQualityFeedbackTokenDef].

```SQL
DELETE FROM [CallQualityFeedbackTokenDef];
INSERT INTO [CallQualityFeedbackTokenDef] (TokenId, TokenDescription) VALUES
    (1,   N'DistortedSpeech'),
    (2,   N'ElectronicFeedback'),
    (3,   N'BackgroundNoise'),
    (4,   N'MuffledSpeech'),
    (5,   N'Echo'),
    (21,  N'FrozenVideo'),
    (22,  N'PixelatedVideo'),
    (23,  N'BlurryImage'),
    (24,  N'PoorColor'),
    (25,  N'DarkVideo'),
    (101, N'Audio_SilentLocal'),
    (102, N'Audio_SilentRemote'),
    (103, N'Audio_Echo'),
    (104, N'Audio_BackgroundNoise'),
    (105, N'Audio_LowSound'),
    (106, N'Audio_Dropped'),
    (107, N'Audio_DistortedSpeech'),
    (108, N'Audio_Interrupted'),
    (109, N'Audio_Other'),
    (201, N'Video_NoLocalVideo'),
    (202, N'Video_NoRemoteVideo'),
    (203, N'Video_LowQuality'),
    (204, N'Video_FrozenVideo'),
    (205, N'Video_StoppedUnexpectedly'),
    (206, N'Video_DarkVideo'),
    (207, N'Video_NoAudioSync'),
    (208, N'Video_Other'),
    (301, N'Pstn_DialPad'),
    (401, N'SS_NoContentLocal'),
    (402, N'SS_NoContentRemote'),
    (403, N'SS_CantPresent'),
    (404, N'SS_LowQuality'),
    (405, N'SS_Freezing'),
    (406, N'SS_StoppedUnexpectedly'),
    (407, N'SS_LargeDelay'),
    (408, N'SS_Other'),
    (501, N'Reliabilty_Join'),
    (502, N'Reliabilty_Invite');
```


