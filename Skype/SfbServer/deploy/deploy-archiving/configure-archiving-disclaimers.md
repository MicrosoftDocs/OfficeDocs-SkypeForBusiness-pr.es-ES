---
title: Configuración de declinación de responsabilidades de archivado para los usuarios externos en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar una renuncia de archivado para Skype para Business Server.'
ms.openlocfilehash: 9511dacb23773a4cd411844abd1d38216026019e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881754"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configuración de declinación de responsabilidades de archivado para los usuarios externos en Skype para Business Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar una renuncia de archivado para Skype para Business Server.
  
Si su organización se comunica con socios externos, necesita informarles que las comunicaciones con ellos se archivan. Al implementar un servidor perimetral y habilitar la federación para su organización, se le pregunte si desea enviar automáticamente una renuncia de archivado a socios externos. 
  
Si necesita cambiar esta configuración, puede usar el Skype para el Panel de Control de servidor empresarial o el cmdlet **Set-CsAccessEdgeConfiguration** de Windows PowerShell. Cmdlets de se puede ejecutar desde la Skype para shell de administración de Business Server o desde una sesión remota de Windows PowerShell.
  
Para permitir que los usuarios externos colaborar con los usuarios de su Skype para la implementación de Business Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios externos. Para obtener más información, vea a Manage XMPP Federated Partners for Your Organization. Para más detalles sobre el control de acceso para dominios federados específicos, consulte Controlar el acceso por medio de los dominios federados individuales.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar o deshabilitar la renuncia de archivado mediante el Panel de control

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 
    
3. En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, luego, en **Configuración perimetral de acceso**.
    
4. En la ficha **Configuración perimetral de acceso**, haga clic en **Global**, en **Editar** y, luego, en **Mostrar detalles**.
    
5. En **Editar configuración perimetral de acceso**, en **Habilitar federación y conectividad pública de mensajería instantánea**, active o desactive la casilla **Enviar declinación de responsabilidades de archivado a los socios federados** para habilitar o deshabilitar el envío automático de declinaciones de responsabilidades de archivado.
    
6. Haga clic en **Confirmar**.
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>Habilitar o deshabilitar la renuncia de archivado mediante Windows PowerShell

Para habilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en True ($True):
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

Para deshabilitar la declinación de responsabilidades de archivado, establezca el valor de la propiedad **EnableArchivingDisclaimer** en False ($False):
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


