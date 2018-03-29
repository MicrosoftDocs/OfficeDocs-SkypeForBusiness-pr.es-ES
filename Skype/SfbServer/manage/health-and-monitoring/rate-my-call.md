---
title: Valorar mi llamada en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/13/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c4e0c905-33a1-49d8-9276-1b338f94d085
description: 'Resumen: Conozca la función tasa mi llamar en Skype para Business Server 2015.'
ms.openlocfilehash: 1e0088c563f38be59bda0fad10dbd367ea0646e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="rate-my-call-in-skype-for-business-server-2015"></a>Valorar mi llamada en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre la función tasa mi llamar en Skype para Business Server 2015.
  
Llame a Mi velocidad es una nueva característica de Skype para negocios 2015 y 2016 clientes Windows que proporciona a las empresas una forma para obtener comentarios de los usuarios finales.
  
La ventana tasa Mis llamadas ofrece un sistema de clasificación "estrella" y símbolos predefinidos para llamadas de audio y vídeo. Además, los administradores pueden habilitar un campo personalizado proporcionar comentarios.
  
Actualmente, los datos recopilados de Valorar mi llamada no se incluyen en ningún informe de supervisión existente, aunque dispone de un informe de supervisión independiente. Se recopilan datos en tablas SQL que se pueden tener acceso mediante la ejecución de consultas SQL.
  
## <a name="rate-my-call-prerequisites"></a>Valorar mis requisitos previos de la llamada

Antes de que los usuarios de su Skype para la implementación de Business Server pueden obtener acceso a la funcionalidad de llame a Mi velocidad, se debe implementar y configurar el siguiente conjunto de componentes:
  
-  Debe tener Skype para Business Server instalado (versión 9160 o superior).
    
- Hacer que los usuarios instalar y actualizar a la versión más reciente de Skype para empresas y también les pedimos que utilice el Skype para la interfaz de usuario de negocio.
    
- Los usuarios deben estar alojados en el Skype para el grupo de negocio de servidor Front-End.
    
- Debe tener un Skype para base de datos supervisión Business Server implementado y asociado a su Skype para grupos de servidores empresariales.
    
- Le recomendamos que implemente el Panel de calidad de llamadas (CQD).
    
## <a name="configure-rate-my-call"></a>Configurar la velocidad de mi llamada

La función de tasa mi llamada está habilitada de forma predeterminada en la directiva de cliente con la configuración siguiente:
  
- Velocidad de mi llamada Mostrar porcentaje - 10%
    
- Velocidad de mi llamada permitir personalizar comentarios del usuario - deshabilitado
    
No hay ninguna acción necesaria para habilitar la característica base, sin embargo, pero si desea una respuesta personalizada debe habilitar por separado. El siguiente cmdlet de Windows PowerShell es un ejemplo de habilitar comentarios de usuario final personalizadas y cambiar el intervalo de 10% a 80%.
  
```
Set-CSClientPolicy -Identity <PolicyIdentity> -RateMyCallDisplayPercentage 80 - RateMyCallAllowCustomUserFeedback $true 

```

## <a name="accessing-rate-my-call-data"></a>Velocidad de acceso a Mis datos de llamada

Se recopilan datos de los usuarios en dos tablas de la base de datos de supervisión.
  
 **[QoeMetrics]. [dbo]. [CallQualityFeedbackToken]** -Esta tabla contiene los resultados de sondeo token por los usuarios finales.
  
 **[QoeMetrics]. [dbo]. [CallQualityFeedbackTokenDef]** -Esta tabla contiene las definiciones de símbolo (token).
  
Las definiciones de símbolo (token) se codifican como sigue:
  
|||
|:-----|:-----|
|1  <br/> |DistortedSpeech  <br/> |
|2  <br/> | ElectronicFeedback <br/> |
|3  <br/> | BackgroundNoise <br/> |
|4  <br/> |MuffledSpeech  <br/> |
|5  <br/> |Eco  <br/> |
|21  <br/> | FrozenVideo <br/> |
|22  <br/> | PixelatedVideo <br/> |
|23  <br/> | BlurryImage <br/> |
|24  <br/> | PoorColor <br/> |
|25  <br/> | DarkVideo <br/> |
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
   
 **[QoeMetrics]. [dbo]. [CallQualityFeedback]** Esta tabla contiene los resultados de sondeo de comentarios de voto y cliente "Estrella" si habilitado.
  
Datos de las tablas se pueden llamar utilizando un **seleccione \* de [Table.Name]** consulta o mediante Microsoft SQL Server Management Studio.
  
Pueden utilizarse las siguientes consultas SQL:
  
 **Audio**
  
```
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

 **Vídeo**
  
```
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

## <a name="updating-token-definitions"></a>Actualización de definiciones de símbolo (token)

La última Skype para clientes empresariales informe nuevo token problema IDs (\> 100) que no pueden estar presentes en la sección [QoeMetrics]. [dbo]. Tabla [CallQualityFeedbackTokenDef]. Para actualizar la tabla de base de datos con las últimas definiciones de símbolo (token), el comando debajo de SQL se puede ejecutar en la base de datos de supervisión mediante Microsoft SQL Server Management Studio. Este comando reemplazará todas las entradas de la sección [QoeMetrics]. [dbo]. Tabla [CallQualityFeedbackTokenDef].
  
```
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


