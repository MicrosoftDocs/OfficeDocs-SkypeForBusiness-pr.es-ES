---
title: Problemas al recibir mensajes y llamadas en sistemas heredados en Teams
ms.reviewer: ''
author: cichur
ms.author: v-mahoffman
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
ms.openlocfilehash: fb36f4be70b174a324f017b1e52529f457e83f36
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768308"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problemas al recibir mensajes y llamadas en sistemas heredados

Los usuarios pueden tener problemas para recibir mensajes o llamadas si usan versiones anteriores de Teams o han iniciado sesión con otras aplicaciones.

## <a name="legacy-adu-setups"></a>Configuraciones de ADU heredadas

 Si los usuarios han iniciado sesión en un equipo unido a un dominio y **no quieren que su nombre de usuario se rellene previamente en la pantalla de inicio de sesión de Teams**, los administradores pueden configurar el registro de Windows siguiente para desactivar el rellenado previo del nombre de usuario (UPN):

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> La opción para omitir o ignorar el rellenado previo para los nombres de usuario que terminan en ".local" o ".corp" está activada de forma predeterminada, por lo que no es necesario establecer una clave del registro para desactivarlos.

Vea [Iniciar sesión para Microsoft Teams la autenticación moderna](sign-in-teams.md) para obtener más información.

## <a name="skype-token-revocation"></a>Skype revocación de tokens

Al cambiar o restablecer una contraseña, los clientes antiguos no recibirán mensajes y llamadas durante un máximo de una hora. Para resolver este problema, reinicie la aplicación o pase a clientes más recientes.


## <a name="related-topics"></a>Temas relacionados

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)