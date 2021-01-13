---
title: Personalizar la experiencia de cliente mac en Skype Empresarial
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: PhillipGarding
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: En este artículo se describen las preferencias de cliente y los valores predeterminados disponibles para el cliente de Skype Empresarial en Mac y cómo editarlos desde fuera de la aplicación.
ms.openlocfilehash: cdbd1c109fffddf6d922657285f60d9b4f06924a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805760"
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a>Personalizar la experiencia de cliente mac en Skype Empresarial
 
En este artículo se describen las preferencias de cliente y los valores predeterminados disponibles para el cliente de Skype Empresarial en Mac y cómo editarlos desde fuera de la aplicación.
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a>Configuración de preferencias de cliente de Skype Empresarial en Mac

Determinadas características y comportamientos que están disponibles para los clientes de Skype Empresarial en Mac están determinados por la configuración de preferencias en el cliente. Las preferencias de Skype Empresarial en Mac se encuentran en un archivo ubicado en mac que han instalado el cliente de Skype Empresarial ubicado en la siguiente ruta: 
  
 **~/Library/Containers/com.microsoft.SkypeForBusiness/Data/Library/Preferences/com.microsoft.SkypeForBusiness.plist**
  
Para establecer estas preferencias, llegue a un mensaje de terminal en el Mac del cliente y, según sea necesario, escriba los comandos de teclas com.microsoft.SkypeForBusiness con las teclas de preferencia que se describen en la tabla siguiente.
  
**Claves de preferencias de cliente**


| Key  | Tipo | Valor | Descripción |
|:-----|:-----|:-----|:-----|
|autoDetectAutoDicoveryURLs    |Bool    |0 = configuración manual del servidor  <br/> 1 = detección automática de servidores (valor predeterminado)    |Especifique cómo Skype Empresarial identifica el transporte y el servidor que se usarán durante el inicio de sesión. Si habilita esta configuración de directiva, debe especificar **internalAutoDiscoveryURL** y **externalAutoDiscoveryURL**.   |
|internalAutoDiscoveryURL    |String    |Dirección URL de detección automática completa    |Url de detección automática interna    |
|externalAutoDiscoveryURL    |String    |Dirección URL de detección automática completa    |Url de detección automática externa    |
|httpProxyDomain    |String    ||Dominio proxy HTTP    |
|httpProxyUserName    |String    ||Nombre de usuario de proxy HTTP    |
|httpProxyPassword    |String    ||Contraseña de proxy HTTP    |
|trustedDomainList    |Matriz    ||Lista de dominios de confianza para redireccionamientos HTTP.    |
|autoAcceptTimeout    |Número    |300 (valor predeterminado)    |Tiempo de espera de aceptación automática para usuarios sin historial de conversaciones del lado servidor.    |
|warnWhenUnknownLocationForE911    |Bool    |0 = deshabilitado  <br/> 1 = habilitado    |Advierte al usuario al marcar un número de emergencia desde una ubicación desconocida.    |
|sipAddress    |String    ||La dirección SIP (correo electrónico) usada para iniciar sesión en Skype Empresarial.    |
|userName    |Cadena    ||UPN (UserName) usado para iniciar sesión en Skype Empresarial.    |
|userNameInAdvancedOnly    |Bool    |0 = mostrar el campo Nombre de usuario en la pantalla de inicio de sesión principal y en el cuadro de diálogo Propiedades avanzadas  <br/> 1 = mostrar el campo Nombre de usuario solo en el cuadro de diálogo Propiedades avanzadas (valor predeterminado)    |Especifique dónde se muestra el campo Nombre de usuario durante el inicio de sesión.    |
   
### <a name="usage-examples"></a>Ejemplos de uso

Para agregar un único dominio (Contoso.com) a la lista de dominios de confianza, usaría la clave trustedDomainList como se muestra:
  
los valores predeterminados escriben com.microsoft.SkypeForBusiness trustedDomainList -array-add "Contoso.com"
  
Para agregar varios dominios a la lista de dominios de confianza, use la clave trustedDomainList como se muestra:
  
defaults write com.microsoft.SkypeForBusiness trustedDomainList -array-add "sfb.com" "abc.com" "test.org"
  
### <a name="sample-unedited-settings"></a>Configuración sin editar de ejemplo

Como referencia, este es un archivo de configuración de ejemplo que solo usa la configuración predeterminada: 
  
```console
{
    BITApplicationDidEnterBackgroundTime = "1496164840.505589";
    BITApplicationWasLaunched = 1;
    CallHistorySelectedFilterIndex = 0;
    HockeySDKAutomaticallySendCrashReports = 0;
    HockeySDKCrashReportActivated = 1;
    "LastSignOut_me" = "2017-05-30 17:22:17 +0000";
    "NSSplitView Subview Frames CallHistoryListDetailSplit" =     (
        "0.000000, 0.000000, 291.500000, 473.000000, NO, NO",
        "292.500000, 0.000000, 408.500000, 473.000000, NO, NO"
    );
    "NSSplitView Subview Frames calendarListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
   "NSSplitView Subview Frames conversationListSplitView" =     (
        "0.000000, 0.000000, 320.000000, 473.000000, NO, NO",
        "321.000000, 0.000000, 380.000000, 473.000000, NO, NO"
    );
    "NSWindow Frame HomeWindow" = "511 134 769 473 0 0 1280 778 ";
    "NSWindow Frame SignInWindow" = "388 208 512 518 0 0 1280 778 ";
    RawCameraSupportVersion = 7030;
    appRunning = 1;
    buildTime = "May 22 2017 12:37:28";
    "user@contoso.com_userPreferences" =     {
        ContactsListState =         {
            expandedGroupState =             {
                "/me/pendingContacts" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/HR6ZQDk_JUI9WUR0Gq0TEAUYfYDk8OwzsPAuDxZfjxg=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/N-kLDW4VAs4O3PDv36MNyaYxhuqkRGD1eWpzDGdaHnw=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/RJk1X9SsFDq-MbvPe2eUyKTdPizt7-eMxij-ef1SGWQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/UulRAGZQL3JnSpYCDqy4KsZCboNF2pqmp-ru3sqiDPQ=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/Wsbhk9lfd8OUv_0aCtHmYPfm0Wal0mzoM5WFbkxaNjM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/afYHfnLUqTmnwac55OaqHUNqLLCqFTZuDezsBeSLOko=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/aok8RuCx35GbuVLMp-_Zi4gnBK_c5qO7mANf4Drf8Ak=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/hSrWaq6LWhzvT6sRxpyQimwfXzMgLyEc3O4FgSokesc=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/mDdgSHulTTkweoDbjXVp7Y308xM70eFDDZn2j7sAytM=" = 0;
                "/ucwa/v1/applications/414177012058/people/groups/nj3ApLemRK23ChI-K3x_RRGjlEeqTh6_9w6kYwKWldQ=" = 1;
                "/ucwa/v1/applications/414177012058/people/groups/oRX0pDJ2zEP-DQOfynLdvnTEFFNnsv95uvCmVfHjSik=" = 0;
            };
        };
    };
    defaultAudioPlaybackDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    defaultAudioRecordingDevice = <62706c69 73743030 d4010203 04050618 19582476 65727369 6f6e5824 6f626a65 63747359 24617263 68697665 72542474 6f701200 0186a0a5 07080f10 1155246e 756c6cd3 090a0b0c 0d0e5b64 6973706c 61794e61 6d655624 636c6173 735a6964 656e7469 66696572 80038004 80025f10 5a417070 6c655553 42417564 696f456e 67696e65 3a432d4d 65646961 20456c65 6374726f 6e696373 20496e63 2e202020 2020203a 4d696372 6f736f66 74204c69 66654368 6174204c 582d3330 30303a31 34313030 3030303a 322c315f 101a4d69 63726f73 6f667420 4c696665 43686174 204c582d 33303030 d2121314 155a2463 6c617373 6e616d65 5824636c 61737365 735f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365a216 175f1016 4d6f6465 6c2e4175 64696f56 6964656f 44657669 6365584e 534f626a 6563745f 100f4e53 4b657965 64417263 68697665 72d11a1b 54726f6f 74800100 08001100 1a002300 2d003200 37003d00 43004a00 56005d00 68006a00 6c006e00 cb00e800 ed00f801 01011a01 1d013601 3f015101 54015900 00000000 00020100 00000000 00001c00 00000000 00000000 00000000 00015b>;
    firstRun = 0;
    showEndCallDialog = 1;
}
```
