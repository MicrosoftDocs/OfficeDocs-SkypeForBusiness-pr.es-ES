---
title: Personalizar la experiencia del cliente de Mac en Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d1d9cfec-e923-4d02-a306-ee40a9114cb8
description: En este artículo se describen las preferencias de cliente y los valores predeterminados disponibles para el cliente de Skype Empresarial en Mac, y cómo se editan desde fuera de la aplicación.
ms.openlocfilehash: 8c779ad35d82b42bc8e162599265f6a25f7a65c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="customize-the-mac-client-experience-in-skype-for-business"></a>Personalizar la experiencia del cliente de Mac en Skype Empresarial
 
En este artículo se describen las preferencias de cliente y los valores predeterminados disponibles para el cliente de Skype Empresarial en Mac, y cómo se editan desde fuera de la aplicación.
  
## <a name="skype-for-business-on-mac-client-preference-settings"></a>Configuración de las preferencias del cliente de Skype Empresarial en Mac

Ciertas características y comportamientos que están disponibles para Skype para el negocio en los clientes de Mac se determinan mediante la configuración de las preferencias del cliente. El Skype para el negocio en las preferencias de Mac se encuentran en un archivo ubicado en equipos Mac que tiene instalado el Skype para Business client en la siguiente ruta: 
  
 **~/Library/Containers/com.Microsoft.SkypeForBusiness/Data/Library/Preferences/com.Microsoft.SkypeForBusiness.plist**
  
Para establecer estas preferencias, llegar a un mensaje de terminal en Mac del cliente y como sea necesario escribir comandos de clave valores predeterminados escritura com.microsoft.SkypeForBusiness utilizando las teclas de preferencia que se describe en la tabla siguiente.
  
**Claves de preferencia del cliente**


|**Clave**|**Tipo**|**Valor**|**Descripción**|
|:-----|:-----|:-----|:-----|
|AutoDetectAutoDicoveryURLs  <br/> |Booleano  <br/> |0 = configuración manual del servidor  <br/> 1 = detección automática de servidores (predeterminado)  <br/> |Especificar cómo Skype para empresas identifica el transporte y el servidor que se utilizará durante el inicio de sesión. Si habilita esta configuración de directiva, debe especificar **internalAutoDiscoveryURL** y **externalAutoDiscoveryURL**. <br/> |
|internalAutoDiscoveryURL  <br/> |Cadena  <br/> |URL de detección automática completa  <br/> |URL de detección automática interna  <br/> |
|externalAutoDiscoveryURL  <br/> |Cadena  <br/> |URL de detección automática completa  <br/> |URL de detección automática externa  <br/> |
|httpProxyDomain  <br/> |Cadena  <br/> ||Dominio de proxy HTTP  <br/> |
|httpProxyUserName  <br/> |Cadena  <br/> ||Nombre de usuario de proxy HTTP  <br/> |
|httpProxyPassword  <br/> |Cadena  <br/> ||Contraseña de proxy HTTP  <br/> |
|trustedDomainList  <br/> |Matriz  <br/> ||Lista de dominios de confianza para redireccionamientos HTTP.  <br/> |
|autoAcceptTimeout  <br/> |Número  <br/> |300 (predeterminado)  <br/> |Tiempo de espera de aceptación automática para usuarios sin historial de conversaciones del servidor.  <br/> |
|warnWhenUnknownLocationForE911  <br/> |Booleano  <br/> |0 = Deshabilitado  <br/> 1 = Habilitado  <br/> |Advierte al usuario cuando se marca un número de emergencia desde una ubicación desconocida.  <br/> |
|sipAddress  <br/> |Cadena  <br/> ||La dirección SIP (correo electrónico) se utiliza para iniciar sesión en Skype para el negocio.  <br/> |
|nombre de usuario  <br/> |Cadena  <br/> ||UPN (UserName) que se utiliza para iniciar sesión en Skype para el negocio.  <br/> |
|userNameInAdvancedOnly  <br/> |Booleano  <br/> |0 = Mostrar el campo de nombre de usuario en la pantalla de inicio de sesión principal y en el cuadro de diálogo Propiedades avanzadas  <br/> 1 = mostrar el campo de nombre de usuario sólo en el cuadro de diálogo Propiedades avanzadas (predeterminado)  <br/> |Especificar dónde se muestra el campo nombre de usuario durante el inicio de sesión.  <br/> |
   
### <a name="usage-examples"></a>Ejemplos de uso

Para agregar un solo dominio (Contoso.com) a la lista de dominios de confianza utilizaría la clave trustedDomainList como se muestra:
  
trustedDomainList de com.microsoft.SkypeForBusiness de escritura de valores predeterminados-matriz-agregar "Contoso.com"
  
Para agregar varios dominios a la lista de dominios de confianza, usaría la clave trustedDomainList del siguiente modo:
  
trustedDomainList de com.microsoft.SkypeForBusiness de escritura de valores predeterminados-matriz-agregar "abc.com" "test.org" "sfb.com"
  
Orientación sobre el uso del comando valores predeterminados se puede encontrar en la [biblioteca de referencia de Apple](https://developer.apple.com/legacy/library/documentation/Darwin/Reference/ManPages/man1/defaults.1.mdl). Aunque esta página es antigua y ya no se actualiza, la información que contiene sobre el comando de valores predeterminados no ha cambiado y sigue siendo aplicable.
  
### <a name="sample-unedited-settings"></a>Configuración sin editar de muestra

Para que le sirva de referencia, a continuación se muestra una configuración de ejemplo donde se utilizan únicamente los valores predeterminados:  
  
```
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


