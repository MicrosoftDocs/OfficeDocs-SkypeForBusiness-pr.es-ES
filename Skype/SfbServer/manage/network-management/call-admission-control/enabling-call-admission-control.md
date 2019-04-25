---
title: Habilitar el control de admisión de llamadas
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " Después de configurar la red de (CAC) del control de admisión de llamadas, debe habilitar el CAC para exigir la aplicación de las limitaciones de ancho de banda."
ms.openlocfilehash: a683fe0f437fc1c3fa92784313135d094e43c8b1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32228410"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Habilitar el control de admisión de llamadas en Skype Empresarial Server

El control de admisión de llamadas (CAC) es una red de regiones, sitios y subredes que permiten colocar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Después de configurar la red CAC, debe habilitar el CAC para exigir la aplicación de las limitaciones de ancho de banda. Puede usar el Skype para el Panel de Control de servidor empresarial para ello.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Para habilitar el CAC desde el Skype para el Panel de Control de servidor empresarial

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de red**y, a continuación, haga clic en **Global**.

4.  En la página **Global** , haga clic en la configuración **Global** .
   
    > [!NOTE]  
    > Sólo una red se puede configurar para cualquier Skype para la implementación de servidor empresarial, por lo que nunca será más de una configuración de red en la lista. No se puede cambiar el nombre de la configuración Global.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar configuración Global** , active la casilla de verificación **Habilitar el control de admisión de llamadas** y, a continuación, haga clic en **Confirmar**.

Al hacer clic en **Confirmar**, se ejecuta una prueba de la configuración. Cierra el cuadro de diálogo **Editar configuración Global** , regresará a la página **Global** . Recibirá una advertencia si se detectan los errores o incoherencias en su configuración de red que impedirá que funciona correctamente (por ejemplo, si cada región no está conectado a todas las regiones a través de una ruta entre regiones).

Si realiza cambios en la configuración de red, puede ejecutar la comprobación de validación de nuevo abrir la configuración Global y haciendo clic en **Confirmar**. No es necesario deshabilitar el CAC en primer lugar: deje activada la casilla de verificación y haga clic en **Confirmar**. Puede hacerlo en cualquier momento, sin realizar ningún cambio de configuración.

## <a name="see-also"></a>Vea también

[Planificar el servicio de control de admisión de llamadas](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Implementar el control de admisión de llamadas](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
