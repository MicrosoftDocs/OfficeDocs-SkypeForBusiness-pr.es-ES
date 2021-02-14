---
title: Bloquear las transferencias de archivos punto a punto
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: En Skype Empresarial Online, puede controlar las transferencias de archivos de punto a punto (P2P) como parte de la configuración de la directiva de conferencias existente. Sin embargo, esto permite o bloquea la transferencia de archivos para los usuarios, tanto si transfieren archivos a un usuario de la misma organización como a un usuario federado de otra organización. Siguiendo los pasos que se indican a continuación, puede bloquear las transferencias de archivos P2P con socios o organizaciones federadas.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814639"
---
# <a name="block-point-to-point-file-transfers"></a>Bloquear las transferencias de archivos punto a punto

En Skype Empresarial Online, puede controlar las transferencias de archivos de punto a punto (P2P) como parte de la configuración de la directiva de conferencias existente. Sin embargo, esto permite o bloquea la transferencia de archivos para los usuarios, tanto si transfieren archivos a un usuario de la misma organización como a un usuario federado de otra organización. Siguiendo los pasos que se indican a continuación, puede bloquear las transferencias de archivos P2P con socios o organizaciones federadas.
  
 Un escenario muy común es cuando quiere permitir que los usuarios internos usen la transferencia de archivos P2P, pero bloquee la transferencia de archivos con partners federados. Para este escenario, tendrá que hacer lo siguiente:
  
- Asigne una directiva de conferencia con la transferencia de archivos P2P habilitada _(EnableP2PFileTransfer_ establecido en _True)_ a los usuarios de su organización.
    
- Cree una directiva de comunicación de usuario externo global para bloquear las transferencias de archivos P2P externos _(enableP2PFileTransfer_ establecido en _False)_ y asígnela a un usuario de su organización. 
    
Puedes obtener más información sobre esta configuración [aquí.](https://technet.microsoft.com/library/mt228132.aspx)
  
Si un usuario federado externo a la organización intenta enviar un archivo a un usuario donde se ha aplicado la directiva, recibirá un error de error **en la transferencia.** Y si un usuario intenta enviar un archivo, recibirá un error **de transferencia** de archivo desactivado.
  
Para que esto funcione, el usuario debe estar usando una versión compatible de una aplicación de Skype Empresarial 2016 Hacer clic y ejecutar que sea compatible. Se requiere la siguiente versión mínima del cliente Hacer clic y ejecutar de Skype Empresarial 2016:
  
|**Tipo**|**Fecha de lanzamiento**|**Versión**|**Versión**|
|:-----|:-----|:-----|:-----|
|First Release para canal actual  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versión 1611 (compilación 7571.2006)  <br/> |
|Canal actual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versión 1611 (compilación 7571.2072)  <br/> |
|Canal diferido  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versión 1609 (compilación 7369.2118)  <br/> |
   
> [!CAUTION]
> Los usuarios que usan versiones anteriores de aplicaciones windows o clientes Mac de Skype Empresarial todavía podrán transferir archivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
    1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
        
    2. Compruebe la versión escribiendo _Get-Host_ en la **Windows PowerShell** ventana.
        
    3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
        
    4. También necesitará instalar el módulo Windows PowerShell para Teams que le permite crear una sesión de Windows PowerShell remota que se conecta a Skype Empresarial Online. 
    
    Si necesita más información, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx)en una única Windows PowerShell ventana.
    
- **Iniciar una sesión de Windows PowerShell**
    
    1. En el **menú Inicio** > **Windows PowerShell**.
        
    2. En la **Windows PowerShell** de correo electrónico, conéctese a Su Microsoft 365 u Office 365 ejecutando:
    
        > [!NOTE]
        > Skype Empresarial Online Connector forma actualmente parte del módulo de PowerShell de Teams más reciente.
        >
        > Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Si desea más información sobre cómo iniciar Windows PowerShell, consulte Conectarse a todos los servicios de [Microsoft 365 u Office 365](https://technet.microsoft.com/library/dn568015.aspx) en una única ventana de Windows PowerShell o Configurar el equipo para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Deshabilitar las transferencias de archivos P2P para su organización

De forma predeterminada, _EnableP2PFileTransfer_ está habilitado en la directiva global de la organización. Cuando se creó, a los usuarios se les asignó la _directiva BposSAllModality._
  
Para permitir las transferencias P2P para dentro de la organización pero bloquear las transferencias de archivos externos a otra organización, solo tiene que cambiarlo a nivel global. Para ello, ejecute:
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Deshabilitar la transferencia de archivos P2P para un usuario

Para aplicar esto a un usuario, cree una directiva y concédala a ese usuario. Para ello, ejecute: 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)

  
 
