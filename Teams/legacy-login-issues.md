---
title: Problemas para recibir mensajes y llamadas en sistemas heredados en Teams
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: 56499af9534c3559cdfa3311a360caa60d06d3d7
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789525"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problemas al recibir mensajes y llamadas en sistemas heredados

Es posible que los usuarios tengan problemas para recibir mensajes o llamadas si usan versiones anteriores de Teams o han iniciado sesión con otras aplicaciones.

## <a name="legacy-adu-setups"></a>Configuraciones de ADU heredadas

 Si los usuarios han iniciado sesión en un equipo unido a un dominio y **no quieren que su nombre de usuario se rellene previamente en la pantalla de inicio de sesión de Teams**, los administradores pueden configurar el registro de Windows siguiente para desactivar el rellenado previo del nombre de usuario (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> La opción para omitir o ignorar el rellenado previo para los nombres de usuario que terminan en ".local" o ".corp" está activada de forma predeterminada, por lo que no es necesario establecer una clave del registro para desactivarlos.

Consulte [Iniciar sesión en Microsoft Teams con autenticación moderna](sign-in-teams.md) para obtener más información.

## <a name="skype-token-revocation"></a>Revocación de token de Skype

Al cambiar o restablecer una contraseña, los clientes antiguos no recibirán mensajes ni llamadas durante un máximo de una hora. Para resolver este problema, reinicie la aplicación o muévase a clientes más recientes.


## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)