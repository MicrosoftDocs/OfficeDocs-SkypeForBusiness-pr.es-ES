---
title: Problemas al recibir mensajes y llamadas en sistemas heredados de Teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Solucionar problemas relacionados con la recepción de mensajes y llamadas en sistemas heredados
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af7845b5fd6d50d63be6cd21749cbfedc7669fcf
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085156"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problemas al recibir mensajes y llamadas en sistemas heredados
==============================================================

Es posible que los usuarios tengan problemas para recibir mensajes o llamadas si usan versiones anteriores de Teams o iniciaron sesión con otras aplicaciones.

## <a name="legacy-adu-setups"></a>Configuraciones de ADU heredadas

 Si los usuarios han iniciado sesión en un equipo unido a un dominio y **no quieren que su nombre de usuario se rellene previamente en la pantalla de inicio de sesión de Teams**, los administradores pueden configurar el registro de Windows siguiente para desactivar el rellenado previo del nombre de usuario (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> La opción para omitir o ignorar el rellenado previo para los nombres de usuario que terminan en ".local" o ".corp" está activada de forma predeterminada, por lo que no es necesario establecer una clave del registro para desactivarlos.

Para obtener más información, vea [iniciar sesión en Microsoft Teams mediante la autenticación moderna](sign-in-teams.md) .

## <a name="skype-token-revocation"></a>Revocación de tokens de Skype

Al cambiar o restablecer una contraseña, los clientes antiguos no recibirán mensajes ni llamarán hasta una hora. Para resolver este problema, reinicie la aplicación o desplácese a clientes más recientes.


## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)