---
title: Configurar la declinación de responsabilidades del archivado para los usuarios externos en Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumen: Leer este tema para aprender a configurar una renuncia de archivado para Skype para Business Server 2015.'
ms.openlocfilehash: 3790160024010084c69df7d9865f17622fca4f0d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server-2015"></a>Configurar la declinación de responsabilidades del archivado para los usuarios externos en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a configurar una renuncia de archivado para Skype para Business Server 2015.
  
Si su organización se comunica con socios externos, necesita informarles que las comunicaciones con ellos se archivan. Cuando se implementa un servidor perimetral y habilitar la federación para su organización, le pregunta si desea enviar automáticamente una archiving renuncia a socios externos. 
  
Si necesita cambiar esta configuración, puede utilizar el Skype para el Panel de Control de servidor de negocios o el cmdlet de Windows PowerShell **Set-CsAccessEdgeConfiguration** . Los cmdlets se puede ejecutar desde el Skype para el shell de administración de Business Server o desde una sesión remota de Windows PowerShell.
  
Para permitir que los usuarios externos colaborar con los usuarios de su Skype para la implementación de Business Server, también debe configurar al menos una directiva de acceso externo para admitir el acceso de usuarios externos. Para obtener más información, vea a administrar socios federados de XMPP para su organización. Para más detalles sobre el control de acceso para dominios federados específicos, consulte Controlar el acceso por medio de los dominios federados individuales.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar o deshabilitar la renuncia de archivado mediante el Panel de control

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial. 
    
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


