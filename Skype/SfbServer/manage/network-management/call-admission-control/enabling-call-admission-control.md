---
title: Habilitar el control de admisión de llamadas
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: " Después de configurar la red de control de admisión de llamadas (CAC), debe habilitar el CAC para aplicar las limitaciones de ancho de banda."
ms.openlocfilehash: 090b19282ce85289b0e79e09d58646c5bf5e81e2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118579"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a>Habilitar el control de admisión de llamadas en Skype Empresarial Server

El control de admisión de llamadas (CAC) consiste en una red de regiones, sitios y subredes que permiten aplicar restricciones en las transmisiones de audio y vídeo según el ancho de banda disponible. Una vez configurada la red CAC, debe habilitar el CAC para aplicar las limitaciones de ancho de banda. Para ello, puede usar el Panel de control de Skype Empresarial Server.


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a>Para habilitar el CAC desde el Panel de control de Skype Empresarial Server

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o tenga derechos de usuario equivalentes), o esté asignada al rol CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server. 

3.  En la barra de navegación izquierda, haga clic en **Configuración de** red y, a continuación, haga clic **en Global**.

4.  En la página **Global**, haga clic en la configuración **Global**.
   
    > [!NOTE]  
    > Solo se puede configurar una red para cualquier implementación de Skype Empresarial Server, por lo que nunca habrá más de una configuración de red en la lista. No podrá cambiar el nombre de la configuración Global.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  En la página **Editar configuración global**, active la casilla **Habilitar control de admisión de llamadas** y, a continuación, haga clic en **Confirmar**.

Al hacer clic en **Confirmar**, realizará una prueba de la configuración. Se cerrará el cuadro de diálogo **Editar configuración global** y el programa le devolverá a la página **Global**. Recibirá una advertencia si se descubren errores o incoherencias en la configuración de red que pudieran impedir el buen funcionamiento de la red (por ejemplo, si cada región no está conectada a otra región en una ruta interregional).

Si hace cambios en la configuración de red, puede volver a ejecutar la comprobación de validación abriendo la configuración Global y haciendo clic en **Confirmar**. No es necesario deshabilitar previamente el CAC: deje activada la casilla y haga clic en **Confirmar**. Puede hacerlo en cualquier momento aunque no haga cambios en la configuración.

## <a name="see-also"></a>Consulta también

[Planear el control de admisión de llamadas](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[Implementar el control de admisión de llamadas](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[Get-CsNetworkConfiguration](/powershell/module/skype/Get-CsNetworkConfiguration)  

[Set-CsNetworkConfiguration](/powershell/module/skype/Set-CsNetworkConfiguration)  

[Remove-CsNetworkConfiguration](/powershell/module/skype/Remove-CsNetworkConfiguration)