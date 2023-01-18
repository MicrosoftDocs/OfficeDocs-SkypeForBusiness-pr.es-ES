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
ms.openlocfilehash: 60d9bf64233db3f5e615c0904c6eb376f187266c
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812847"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Autenticación basada en aplicaciones en el módulo de PowerShell de Teams

La autenticación basada en aplicaciones ahora es compatible con el módulo PowerShell de Teams con las versiones 4.7.1-preview o posteriores. Actualmente este modo de autenticación solo es compatible con entornos comerciales.


## <a name="cmdlets-supported"></a>Cmdlets admitidos

Ahora se admiten todos los cmdlets, excepto los cmdlets que se mencionan a continuación. 

  - New-Team
  - [Obtener| Conjunto| Nuevo| Sync]-CsOnlineApplicationInstance
  - \*-CsUserCallingSettings
  - \*-CsUserCallingDelegate
  - \*PolicyPackage\*
  - \*-CsTeamsShiftsConnection\*
  - \*-CsBatchTeamsDeployment\*


## <a name="examples"></a>Ejemplos

En los ejemplos siguientes se muestra cómo usar el módulo PowerShell de Teams con la autenticación basada en la aplicación de Azure AD: 

- Conectar mediante una huella digital del certificado:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Al usar el parámetro CertificateThumbprint, el certificado debe instalarse en el equipo en el que se ejecuta el comando. El certificado debe instalarse en el almacén de certificados del usuario.
  
- Conectarse mediante un objeto de certificado:

  ```powershell
  Connect-MicrosoftTeams -Certificate <%X509Certificate2 object%> -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Al usar el parámetro Certificate, no es necesario que el certificado esté instalado en el equipo donde se ejecuta el comando. El certificado se puede almacenar de forma remota & se captura cuando se ejecuta el script. El parámetro Certificate está disponible en Teams PowerShell Module versión 4.9.2-preview o posterior.
  
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

Los pasos de ejemplo para crear aplicaciones en Azure Ad se mencionan a continuación, para conocer los pasos detallados, consulte este [artículo](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Registrar la aplicación en Azure AD
2. Asignar permisos de API a la aplicación
   - Para \*cmdlets -Cs: el permiso de Microsoft Graph API necesario es `Organization.Read.All`.
   - Para cmdlets que no \*son de Cs: los permisos de Microsoft Graph API necesarios son `Organization.Read.All`, , `Group.ReadWrite.All``User.Read.All`, `AppCatalog.ReadWrite.All`, `TeamSettings.ReadWrite.All`, `Channel.Delete.All``ChannelSettings.ReadWrite.All``ChannelMember.ReadWrite.All`.  
3. Generar un certificado autofirmado
4. Adjuntar el certificado a la aplicación de Azure AD
5. Asignar [roles de Azure AD](/microsoftteams/using-admin-roles#teams-roles-and-capabilities) a la aplicación

La aplicación debe tener asignados los roles RBAC adecuados. Como las aplicaciones se aprovisionan en Azure AD, puede usar cualquiera de los roles integrados admitidos.
 
