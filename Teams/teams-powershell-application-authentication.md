---
title: Autenticación basada en aplicaciones en el módulo de PowerShell de Teams
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Obtenga más información sobre la autenticación basada en aplicaciones en el Módulo de PowerShell de Teams, usado para la administración de Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea836225658292c312490704305261210ba0991c
ms.sourcegitcommit: 44d9f15f7f7c00b3651a11ff1e8b37dda1716a52
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67732791"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Autenticación basada en aplicaciones en el módulo de PowerShell de Teams

La autenticación basada en aplicaciones ahora se admite en el módulo PowerShell de Teams para un conjunto limitado de cmdlets en versión preliminar con las versiones 4.7.1-preview o posteriores. Actualmente este modo de autenticación solo es compatible con entornos comerciales. No es compatible con los clientes que están o se han habilitado anteriormente para reuniones hospedadas regionalmente en Skype Empresarial en línea.


## <a name="cmdlets-supported"></a>Cmdlets admitidos

Todos los cmdlets que no \*sean de Cs (por ejemplo, Get-Team), Get-CsTenant Get-CsOnlineUser & Get-CsOnlineVoiceUser ya son compatibles. Se implementarán gradualmente otros cmdlets. 


## <a name="examples"></a>Ejemplos

En los ejemplos siguientes se muestra cómo usar el módulo PowerShell de Teams con la autenticación basada en la aplicación de Azure AD: 

- Conectar mediante una huella digital del certificado:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Al usar el parámetro CertificateThumbprint, el certificado debe instalarse en el equipo en el que se ejecuta el comando. El certificado debe instalarse en el almacén de certificados del usuario.
  
- Conectarse mediante tokens de acceso:
  
  Los tokens de acceso se pueden recuperar a través del punto de conexión de login.microsoftonline.com. Se necesitan dos tokens de acceso: "MS Graph" y recursos de "API de Administración de inquilino de Skype y Teams".

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>¿Cómo funciona?

El módulo PowerShell de Teams captura el token basado en la aplicación con el id. de aplicación, el id. de inquilino y la huella digital del certificado. El objeto de aplicación aprovisionado dentro de Azure AD tiene asignado un rol de directorio, que se devuelve en el token de acceso. El control de acceso basado en roles (RBAC) de la sesión se configura con la información de rol de directorio que está disponible en el token.


## <a name="setup-application-based-authentication"></a>Configurar autenticación basada en aplicaciones

Se requiere una incorporación inicial para la autenticación con objetos de aplicación. La entidad de servicio y la aplicación se usan indistintamente, pero una aplicación es como un objeto de clase mientras que una entidad de servicio es como una instancia de la clase. Puede obtener más información sobre estos objetos en [Objetos de entidad de servicio y aplicación en Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).

Los pasos de alto nivel para crear aplicaciones en Azure Ad se mencionan a continuación, para conocer los pasos detallados, consulte este [artículo](/azure/active-directory/develop/howto-create-service-principal-portal).
  1. Registrar la aplicación en Azure AD
  2. Generar un certificado autofirmado
  3. Adjuntar el certificado a la aplicación de Azure AD
  4. Asignar roles de Azure AD a la aplicación

La aplicación debe tener asignados los roles RBAC adecuados. Como las aplicaciones se aprovisionan en Azure AD, puede usar cualquiera de los roles integrados admitidos.
 