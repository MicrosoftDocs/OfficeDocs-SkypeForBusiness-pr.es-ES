---
title: Configurar descargos de responsabilidad de archivado para usuarios externos en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar una renuncia de archivado para Skype empresarial Server.'
ms.openlocfilehash: 86430ac80d85ed166ae091119f4261cdc5e1ff9b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278986"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>Configurar descargos de responsabilidad de archivado para usuarios externos en Skype empresarial Server
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar una renuncia de archivado para Skype empresarial Server.
  
Si su organización se comunica con socios externos, necesita informarles que las comunicaciones con ellos se archivan. Al implementar un servidor perimetral y habilitar la Federación de su organización, se le preguntará si desea enviar automáticamente una renuncia de archivado a los socios externos. 
  
Si necesita cambiar esta configuración, puede usar el panel de control de Skype empresarial Server o el cmdlet **set-CsAccessEdgeConfiguration de** Windows PowerShell. Los cmdlets se pueden ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell.
  
Para permitir que los usuarios externos colaboren con los usuarios de su implementación de Skype empresarial Server, también debe configurar al menos una directiva de acceso externo para que admita el acceso de usuarios externos. Para obtener más información, vea administrar los socios de XMPP federados de su organización. Para más detalles sobre el control de acceso para dominios federados específicos, consulte Controlar el acceso por medio de los dominios federados individuales.
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>Habilitar o deshabilitar la renuncia de archivado mediante el Panel de control

1. Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 
    
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


