---
title: Transferencias de archivos punto a punto de bloque
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "En Skype para los negocios en línea, tiene capacidad para controlar a las transferencias de archivos punto a punto (P2P) como parte de la configuración de directivas de conferencia existente. Sin embargo, esto permite o bloquea las transferencias para los usuarios si están transfiriendo archivos a un usuario que pertenezca a la misma organización o a un usuario federado de otra organización de archivos. Siguiendo los pasos siguientes, puede bloquear a las transferencias de archivos P2P con organizaciones federadas o asociados."
ms.openlocfilehash: 1e19c6d6976caaee1ed482935d1853e177f65ea5
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="block-point-to-point-file-transfers"></a>Transferencias de archivos punto a punto de bloque

En Skype para los negocios en línea, tiene capacidad para controlar a las transferencias de archivos punto a punto (P2P) como parte de la configuración de directivas de conferencia existente. Sin embargo, esto permite o bloquea las transferencias para los usuarios si están transfiriendo archivos a un usuario que pertenezca a la misma organización o a un usuario federado de otra organización de archivos. Siguiendo los pasos siguientes, puede bloquear a las transferencias de archivos P2P con organizaciones federadas o asociados.
  
 Un escenario muy común es cuando desea permitir a los usuarios internos para transferencia de archivos P2P de uso pero el bloque de transferencia de archivos con socios federados. En este escenario, tendría que hacer:
  
- Asignar una directiva de conferencia con ha habilitado la transferencia de archivos P2P (_EnableP2PFileTransfer_ establecido en _True_) para los usuarios de su organización.
    
- Crear una directiva de comunicación de usuario externo global establecida para bloquear las transferencias de archivos P2P externas (_EnableP2PFileTransfer_ establecida en _False_) y asignarlo a un usuario de la organización. 
    
Puede encontrar más información acerca de las opciones [aquí](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Si un usuario federado fuera de su organización intenta enviar un archivo a un usuario donde se ha aplicado la directiva, recibirá un error de **Transferencia fallida** . Y si un usuario intenta enviar un archivo, recibirá un error de **transferencia de archivos está desactivada** .
  
Para que esto funcione, el usuario debe utilizar una versión compatible de un Skype hacer clic y ejecutar de 2016 para el negocio de la aplicación que lo admite. Se requiere la siguiente versión mínima de Skype para cliente de negocios 2016 clic y ejecutar:
  
|**Tipo**|**Fecha de lanzamiento**|**Versión**|**Versión**|
|:-----|:-----|:-----|:-----|
|Primera versión para el canal actual  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Versión 1611 (compilación 7571.2006)  <br/> |
|Canal actual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versión 1611 (compilación 7571.2072)  <br/> |
|Canal diferido  <br/> |22/2/2017  <br/> |16.0.7369.2118  <br/> |Versión 1609 (compilación 7369.2118)  <br/> |
   
> [!CAUTION]
> Los usuarios que utilizan versiones anteriores de Skype para clientes de Mac o Windows Business apps podrán transferir archivos. 
  
## <a name="verify-and-start-windows-powershell"></a>Verificar e iniciar Windows PowerShell

- **Comprobar que está ejecutando Windows PowerShell versión 3.0 o superior**
    
1. Para comprobar que se está ejecutando la versión 3.0 o superior: **Menú Inicio** > **Windows PowerShell**.
    
2. Comprobar la versión, escriba _Get-Host_ en la ventana **De Windows PowerShell** .
    
3. Si no tiene la versión 3.0 o superior, deberá descargar e instalar las actualizaciones de Windows PowerShell. Vea [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para descargar y actualizar Windows PowerShell a la versión 4.0. Reinicie el equipo cuando se le solicite.
    
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

  Si desea obtener más información acerca de cómo iniciar Windows PowerShell, vea [Conectar con todos los servicios de Office 365 en una sola ventana de Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) o [conectarse a Skype para los negocios en línea mediante el uso de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>Deshabilitar a las transferencias de archivos P2P para su organización

De forma predeterminada, _EnableP2PFileTransfer_ está habilitada en la directiva global de la organización. Cuando se creó, los usuarios se asignaron la directiva de _BposSAllModality_ .
  
Para permitir a las transferencias P2P para dentro de la organización pero bloque externo las transferencias de archivos a otra organización, sólo necesita cambiarla a nivel global. Para ello, ejecute:
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>Deshabilitar a las transferencias de archivos P2P para un usuario

Puede aplicar a un usuario mediante la creación de una nueva directiva y concederle a ese usuario. Para ello, ejecute: 
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```
> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados
[Crear directivas personalizadas de acceso externo](create-custom-external-access-policies.md)

[Configurar directivas de cliente para la organización](set-up-client-policies-for-your-organization.md)

[Configurar directivas de la conferencia de la organización](set-up-conferencing-policies-for-your-organization.md)

