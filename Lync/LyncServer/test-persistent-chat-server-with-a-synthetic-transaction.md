---
title: "Test du chat du serv. de conv. Perm. avec une transaction synthétique"
TOCTitle: "Test du chat du serv. de conv. Perm. avec une transaction synthétique"
ms:assetid: 414e43f3-0074-4ecf-a232-398de972cb24
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204837(v=OCS.15)
ms:contentKeyID: 48275086
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Probar servidor de chat persistente con una transacción sintética

 

_**Última modificación del tema:** 2012-09-21_

Para probar Servidor de chat persistente para enviar y recibir mensajes en un salón de chat entre dos usuarios

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-ReceiverSipAddress <String>] [-RegistrarPort <Int32>] [-SenderSipAddress <String>] -TargetFqdn <String> [-Force <SwitchParameter>] [-OutLoggerVariable <String>] 
        [-OutVerboseVariable <String>] [<CommonParameters>]

o

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] -ReceiverCredential <PSCredential> -ReceiverSipAddress <String> [-RegistrarPort 
        <Int32>] -SenderCredential <PSCredential> -SenderSipAddress <String> [-TargetFqdn <String>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable <String>] [<CommonParameters>]

o

    Test-CsPersistentChatMessage [-Authentication <TrustedServer | Negotiate | ClientCertificate | 
        LiveID>] [-Force <SwitchParameter>] [-OutLoggerVariable <String>] [-OutVerboseVariable 
        <String>] [<CommonParameters>]

