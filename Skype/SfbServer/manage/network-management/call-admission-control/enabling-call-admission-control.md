---
title: Habilitar el control de admisión de llamadas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " Después de configurar la red de control de admisión de llamadas (CAC), debe habilitar CAC para exigir las limitaciones de ancho de banda."
ms.openlocfilehash: 4f9f3f09f943b417ec589f26dc5c6505d30831f9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817539"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Habilitar el control de admisión de llamadas en Skype Empresarial Server

El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Después de configurar la red CAC, debe habilitar CAC para exigir las limitaciones de ancho de banda. Puede usar el panel de control de Skype empresarial Server para hacerlo.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Para habilitar CAC desde el panel de control de Skype empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **configuración de red**y, a continuación, en **global**.

4.  En la página **global** , haga clic en la configuración **global** .
   
    > [!NOTE]  
    > Solo se puede configurar una red para cualquier implementación de Skype empresarial Server, por lo que nunca habrá más de una configuración de red en la lista. No puede cambiar el nombre de la configuración global.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar configuración global** , active la casilla **Habilitar control de admisión de llamadas** y, a continuación, haga clic en **confirmar**.

Al hacer clic en **confirmar**, se ejecuta una prueba de la configuración. Se cerrará el cuadro de diálogo **Editar configuración global** y volverá a la página **global** . Recibirá una advertencia si se detectan errores o incoherencias en la configuración de red que le impedirán que funcione correctamente (por ejemplo, si cada región no está conectada a ninguna otra región a través de una ruta interregion).

Si realiza cambios en la configuración de red, puede volver a ejecutar la comprobación de validación abriendo la configuración global y haciendo clic en **confirmar**. No es necesario deshabilitar CAC en primer lugar: deje la casilla activada y haga clic en **confirmar**. Puede hacerlo en cualquier momento sin realizar cambios en la configuración.

## <a name="see-also"></a>Vea también

[Planificar el servicio de control de admisión de llamadas](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Implementar el control de admisión de llamadas](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
