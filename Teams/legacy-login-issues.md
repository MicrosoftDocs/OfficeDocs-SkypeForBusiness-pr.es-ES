---
title: Problemas al recibir mensajes y llamadas en sistemas heredados en Teams
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
ms.openlocfilehash: 4626f7d675f5b6d5f4899f9b0f1cd6d8eb81776de383c3a0c573e2fd78967cb5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54348983"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problemas al recibir mensajes y llamadas en sistemas heredados
==============================================================

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