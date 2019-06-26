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
f1keywords: None
ms.custom:
- Setup
description: En Skype empresarial online, tiene la capacidad de controlar las transferencias de archivos punto a punto (P2P) como parte de la configuración de directivas de conferencia existentes. Sin embargo, esto permite o bloquea las transferencias de archivos para los usuarios, ya sea que transfieran archivos a un usuario que está dentro de la misma organización o a un usuario federado de otra organización. Siguiendo los pasos que se indican a continuación, puede bloquear las transferencias de archivos P2P con organizaciones o socios federados.
ms.openlocfilehash: 248b541a4d57c3b51a48694d3194432cc207db06
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221193"
---
# <a name="block-point-to-point-file-transfers"></a>Bloquear las transferencias de archivos punto a punto

En Skype empresarial online, tiene la capacidad de controlar las transferencias de archivos punto a punto (P2P) como parte de la configuración de directivas de conferencia existentes. Sin embargo, esto permite o bloquea las transferencias de archivos para los usuarios, ya sea que transfieran archivos a un usuario que está dentro de la misma organización o a un usuario federado de otra organización. Siguiendo los pasos que se indican a continuación, puede bloquear las transferencias de archivos P2P con organizaciones o socios federados.
  
 Un escenario muy común es cuando desea permitir que los usuarios internos utilicen la transferencia de archivos P2P pero bloquean la transferencia de archivos con socios federados. Para este escenario, debe hacer lo siguiente:
  
- Asignar una directiva de conferencia con la transferencia de archivos P2P habilitada (_EnableP2PFileTransfer_ establecida en _true_) a los usuarios de su organización.
    
- Crear una directiva de comunicación de usuario externa global establecida para bloquear las transferencias de archivos P2P externos (_EnableP2PFileTransfer_ establecido en _falso_) y asignarlo a un usuario de su organización. 
    
Puede obtener más información sobre esa configuración [aquí](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Si un usuario federado fuera de la organización intenta enviar un archivo a un usuario en el que se ha aplicado la Directiva, recibirá un error de **transferencia fallida** . Y si un usuario intenta enviar un archivo, recibirá un error al **transferir un archivo** .
  
Para que esto funcione, el usuario debe estar usando una versión compatible de una 2016 una aplicación de Skype empresarial de hacer clic y ejecutar que la admita. Se necesita la siguiente versión mínima de Skype empresarial 2016 cliente de hacer clic y ejecutar:
  
|**Tipo**|**Fecha de lanzamiento**|**Versión**|**Versión**|
|:-----|:-----|:-----|:-----|
|First Release para el canal actual  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |Versión 1611 (compilación 7571,2006)  <br/> |
|Canal actual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versión 1611 (compilación 7571,2072)  <br/> |
|Canal diferido  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Versión 1609 (compilación 7369,2118)  <br/> |
   
> [!CAUTION]
> Los usuarios que usen versiones anteriores de las aplicaciones de Windows de Skype para empresas o clientes de Mac seguirán pudiendo transferir archivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Para comprobar la versión, escriba _Get-host_ en la ventana de **Windows PowerShell** .
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4,0. Reinicie el equipo cuando se le solicite.
    
4. También necesitará instalar el módulo Windows PowerShell para Skype Empresarial Online que le permite crear una sesión remota de Windows PowerShell que se conecta a Skype Empresarial Online. Este módulo, que solo se admite en equipos de 64 bits, puede descargarse desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Reinicie el equipo cuando se le solicite.
    
    Si necesita más información, consulte [Conectarse a todos los servicios de Office 365 en una única ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Iniciar una sesión de Windows PowerShell**
    
1. En el **menú Inicio** > **Windows PowerShell**.
    
2. En la ventana **Windows PowerShell**, puede conectarse a su organización de Office 365 ejecutando:
    
    > [!NOTE]
    > Solo tiene que ejecutar el comando **Import-Module** la primera vez que use el módulo Windows PowerShell de Skype Empresarial Online.

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   Si desea obtener más información sobre cómo iniciar Windows PowerShell, vea [conectarse a todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [configurar su equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Deshabilitar las transferencias de archivos P2P para su organización

De forma predeterminada, _EnableP2PFileTransfer_ está habilitado en la directiva global de la organización. Cuando se creó, a los usuarios se les asignó la directiva _BposSAllModality_ .
  
Para permitir las transferencias P2P para dentro de su organización pero bloquear las transferencias de archivos externos a otra organización, solo tiene que cambiarla a nivel global. Para ello, ejecute:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Deshabilitar las transferencias de archivos P2P para un usuario

Puede aplicar esta función a un usuario creando una nueva Directiva y concediendo a ese usuario. Para ello, ejecute: 
> 
>   ```
>   New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
>   ```
> 
>   ```
>   Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Establecer directivas de cliente en su organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de conferencia en su organización](set-up-conferencing-policies-for-your-organization.md)

  
 
